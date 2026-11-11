# 03. Données, événements et « bus de données »

## 1. Stockage : PostgreSQL unique (proposition)

Une **seule base PostgreSQL** (dernière version majeure stable, à figer au démarrage) porte :

| Besoin | Mécanisme PostgreSQL | Pourquoi pas un composant dédié |
|---|---|---|
| Données relationnelles et historique | Tables, contraintes, transactions | — |
| Données semi-structurées (charge utile des faits) | Colonnes JSON typées + schémas validés côté application | Pas de base documentaire : on garde la **cohérence transactionnelle** |
| **Recherche texte intégral en français** | Recherche texte native, dictionnaire français, suppression des accents, trigrammes pour les noms approchants | Moteur de recherche dédié inutile à ce volume (X9) |
| **Recherche sémantique** (assistant) | Extension de vecteurs, index approximatif | Base vectorielle dédiée inutile ; **le filtre de droits se fait dans la même requête SQL** (X1) |
| **File de tâches** | Bibliothèque de file sur PostgreSQL (verrouillage de lignes) | Pas de courtier de messages à exploiter (K5, principe 1) |
| **Sécurité par ligne** | Politiques de sécurité par ligne (« RLS ») | Seconde ligne de défense (X1) |
| Journal immuable | Table en ajout seul, droits restreints, chaînage de condensats | Pas de base spécialisée |
| Notifications temps réel | Notification légère entre processus | Pas de bus externe |

**Pourquoi une seule base ?** Cohérence (un rapport, ses faits, ses droits et son journal changent **dans la même transaction**), sauvegarde simple, une seule technologie à exploiter. Le prix : la base devient le point sensible ; on la protège (sauvegardes testées, supervision, dimensionnement) plutôt que de la multiplier.

**Limites assumées** : si un jour le volume de recherche dépassait ce que PostgreSQL gère confortablement, on introduirait un moteur de recherche **derrière le module `search`**, sans toucher aux autres (ADR 013).

## 2. Organisation logique : un schéma par module

Chaque module **possède son schéma** et ses tables ; aucun autre module n'y accède directement. Les liens entre modules se font par **identifiants** (pas de jointures croisées dans le code applicatif).

| Schéma | Contenu principal (tables logiques) |
|---|---|
| `access` | `principals`, `roles`, `role_assignments` (rôle × périmètre), `perimeters`, `classification_levels`, `clearances` (habilitations), `grants` (droits calculés, voir §6), `delegations` |
| `referential` | `organizations_units`, `teams`, `persons` (annuaire minimal), `services`, `applications`, `initiatives`, `aliases`, `object_links` |
| `reports` | `reports`, `report_versions`, `documents` (empreinte, taille, type), `templates`, `drafts`, `report_states` |
| `facts` | `facts`, `fact_versions` (historique), `fact_evidence` (extraits sources vérifiés), `fact_links` (rattachements), `signals`, `clarifications`, `corrections_feedback` |
| `analysis` | `analysis_runs`, `analysis_steps`, `chunks` (texte découpé), `embeddings`, `detections` (données personnelles, injection, sensibilité) |
| `ai` | `prompt_versions`, `model_registry`, `ai_calls_log` (métadonnées, **pas** le contenu), `evaluation_runs`, `evaluation_cases` |
| `rules` | `parameter_sets` (versionnés), `health_results`, `indicator_values`, `snapshots` |
| `ingestion` | `sources`, `source_runs`, `staging_*` (zone d'accueil), `mappings`, `mapping_queue` |
| `notifications` | `notifications`, `preferences`, `tasks`, `reminders` |
| `audit` | `journal` (chaîné), `journal_checkpoints`, `ai_usage_registry` |
| `platform` | `outbox`, `job queue` (tables de la bibliothèque), `settings`, `blob_index` |

## 3. Modèle de faits : historisé et reproductible (X2, X4)

Le **fait** est l'objet central. Principes :

- **Identité stable** : un fait a un identifiant ; ses **versions** sont immuables (`fact_versions`) : chaque changement (confirmation, correction, remplacement, rejet, péremption) **ajoute** une version.
- **Deux axes temporels** : *validité métier* (`valid_from`, `valid_to` : « l'avancement de mars ») et *connaissance* (`recorded_at` : « quand Odin l'a su »). Cela permet de **reconstituer l'état connu à une date** (« photo des données » pour une décision).
- **Provenance obligatoire** : chaque version référence au moins une **preuve** (`fact_evidence`) : rapport + version + **extrait vérifié mot à mot** + position ; ou « saisie manuelle » identifiée ; ou « source outil » (alimentation).
- **Niveau de fiabilité** (F0..F4) stocké par version ; **transitions** contrôlées par la machine à états du fichier 02 du lot 1 §4.
- **Rattachements** (`fact_links`) : un fait peut viser plusieurs objets ; rattachement **certain / ambigu** conservé.
- **Niveau de classification** hérité du **plus élevé** des sources (RG-04), recalculé quand une source change.
- **Pas de suppression physique** pendant la durée de conservation ; l'**effacement** (RG-21) est un processus **contrôlé** qui conserve ce que la loi ou une décision tracée exige, et **expurge** le contenu (pas la trace d'existence minimale).

**Projections (modèles de lecture)** : santé des applications, santé des initiatives, valeurs d'indicateurs, listes de tâches. Elles sont **recalculées par des fonctions pures** à partir des faits et d'un **jeu de paramètres versionné**, puis **stockées avec la référence** (version des paramètres + horodatage de connaissance). Conséquences : tout chiffre est **reproductible** ; la **simulation d'impact** (changement de seuil) calcule « à blanc » sans écrire ; l'**explication** (« Pourquoi ? ») est produite **en même temps** que la valeur.

## 4. Documents (blobs)

- **Abstraction `BlobStore`** (port) avec deux adaptateurs : **volume de fichiers** (défaut du Compose) et **stockage objet compatible S3** (si l'organisme en dispose).
- Chaque document est **adressé par son empreinte** (déduplication, détection de doublon exact, intégrité).
- **Jamais de document servi directement** : accès via l'API après **contrôle de droits**, avec liens à durée courte.
- **Chiffrement au repos** : par le support (disque/volume/objet) de l'organisme ; **chiffrement applicatif d'enveloppe** optionnel pour N4 (ADR 009).
- **Sauvegarde** : la base et les documents sont sauvegardés **ensemble** (cohérence par empreintes ; procédure fichier 06).

## 5. Événements : « bus de données » sans courtier externe (proposition)

### 5.1 Décision

**Au départ, aucun courtier de messages externe** (ni Kafka, ni RabbitMQ, ni NATS). Les événements passent par une **boîte d'envoi transactionnelle (« outbox »)** dans PostgreSQL :

1. Le cas d'usage écrit **les données et l'événement dans la même transaction** (aucune perte, aucun événement fantôme).
2. Un relais interne lit l'outbox et **dépose des tâches** dans la file PostgreSQL (une par consommateur concerné).
3. Les **workers** exécutent les consommateurs, de façon **idempotente** (rejouables sans effet double).

**Pourquoi** : 300 utilisateurs, quelques centaines d'événements par jour ; la garantie « données + événement atomiques » est **gratuite** avec la base ; un courtier ajouterait un composant à exploiter, sauvegarder et superviser (K5, principe 1).

**Quand reconsidérer** (déclencheurs documentés dans l'ADR 006) : plusieurs équipes ou services consommateurs indépendants ; intégrations externes exigeant du publish/subscribe ; débit soutenu de milliers d'événements par seconde ; besoin de rejouer de longs historiques à grande échelle. Le contrat d'événement étant **stable**, un relais vers NATS ou Kafka se **branche sur l'outbox** sans toucher aux producteurs.

### 5.2 Règles

- Un événement porte des **identifiants et un type**, **jamais de contenu** (principe 8). Le consommateur relit les données **sous contrôle d'accès**.
- **Versionnés** (`type`, `version`), **horodatés**, avec **corrélation** (identifiant de requête / d'analyse) pour la traçabilité.
- **Idempotence** : clé d'idempotence par (événement, consommateur) ; table de suivi.
- **Reprise** : un consommateur en échec **réessaie avec attente croissante**, puis passe en « mort » avec alerte ; **rejeu manuel** possible.
- **Ordre** : garanti **par agrégat** (rapport, fait, application) via une clé de partitionnement logique ; pas d'ordre global.

### 5.3 Catalogue des événements du lot 1

| Événement | Producteur | Consommateurs principaux |
|---|---|---|
| `ReportSubmitted` | `reports` | `analysis` (lancer), `audit`, `search` (indexer le texte) |
| `ReportAnalysisCompleted` | `analysis` | `notifications` (N-01), `facts` (signaux), `audit` |
| `ReportAnalysisFailed` | `analysis` | `notifications`, supervision |
| `ReportPublished` | `reports` | `facts` (activer), `rules` (recalcul), `search` |
| `ReportRetired` / `ReportReplaced` | `reports` | `facts`, `rules`, `search`, `audit` |
| `FactProposed` | `analysis` | `facts`, `notifications` |
| `FactConfirmed` / `FactValidated` / `FactRejected` / `FactSuperseded` | `facts` | `rules` (recalcul des projections), `notifications`, `audit` |
| `ContradictionDetected` | `facts` | `notifications` (précision), `rules` |
| `ClarificationAnswered` | `facts` | `rules`, `notifications` |
| `ParameterSetPublished` | `rules` | `rules` (recalcul à partir d'une date), `audit` |
| `ReferentialChanged` | `referential` | `access` (recalcul des droits), `rules`, `search` |
| `ClearanceGranted` / `ClearanceRevoked` | `access` | `search` (réindexation des droits), `notifications`, `audit` |
| `ImportCompleted` | `ingestion` | `referential`, `rules`, `audit` |
| `AiUnavailable` / `AiRecovered` | `ai-gateway` | `analysis` (mise en attente/reprise), supervision |

### 5.4 Intégrations externes (alimentations)

Pas de bus : des **connecteurs planifiés** (tâches périodiques du worker) selon le motif **zone d'accueil → rapprochement → faits** :

1. **Récupération** brute (Jira, temps imputés, fichiers) dans `ingestion.staging_*`, **horodatée** et **non modifiée**.
2. **Rapprochement** (projets ↔ initiatives, équipes, profils) ; ce qui n'est pas reconnu va en **file de correspondance** humaine.
3. **Contrôles de qualité** (complétude, cohérence, doublons) avant toute écriture dans les faits.
4. **Production de faits « alimentés »** avec provenance « source outil » et événement.
5. **Reprise incrémentale** et **idempotence** ; **suspension** sans perte d'historique ; **indicateur d'état** de chaque source (EX-ALI-04).

## 6. Droits : la donnée d'autorisation (X1)

- **Droits calculés** (`access.grants`) : table dérivée qui exprime « *principal* peut lire *objet* au niveau *N* », recalculée par événement (rôle attribué, périmètre modifié, habilitation, délégation, départ). Elle sert **aux filtres SQL** et aux **politiques de sécurité par ligne**.
- Calcul **testable** à partir des règles de la matrice des droits (fichier 02 §4) et des **niveaux de classification** de l'organisme.
- **Invalidation** : un changement de droits est **effectif immédiatement** pour les requêtes suivantes (pas de cache de droits de longue durée).
- Détail du modèle et des tests : fichier 05.

## 7. Conservation, retrait, effacement

- **Politique par type d'objet** (RG-20) stockée comme paramètre ; **tâche d'archivage** périodique.
- **Retrait** d'un rapport (RG-21) : états `retired` ; les faits F1 non validés sortent des projections ; les faits F2 validés par un tiers restent **avec mention** « source retirée ».
- **Effacement** : opération **explicite, tracée** (journal), qui expurge contenu et index (texte, vecteurs) et conserve la **trace minimale** exigée.
- **Journal** : conservé selon la politique ; **jamais** modifié.

## 8. Volumétrie et performances (hypothèses)

| Objet | Ordre de grandeur sur 3 ans | Remarque |
|---|---|---|
| Rapports | ~50 000 | ~100 par jour au plus |
| Faits (avec versions) | ~500 000 versions | Index sur (objet, nature, étiquette) et sur les dates |
| Extraits de texte et vecteurs | ~2 millions | Index vectoriel approximatif **par partition de droits** si nécessaire |
| Journal | ~10 millions de lignes | Partitionnement par mois |
| Documents | ~1 To | Volume ou objet |

À cette échelle, PostgreSQL **sans réplication ni partitionnement complexe** suffit ; une **réplique de lecture** est envisageable plus tard.
