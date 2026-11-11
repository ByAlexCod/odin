# 09. Questions ouvertes, prototypes et plan de démarrage

## 1. Questions pour le commanditaire (à trancher ensemble)

Chaque question indique **ce qu'elle bloque**, **ma recommandation par défaut** (utilisée si vous n'avez pas d'avis) et **le risque** si on se trompe. Priorité : **P1** = bloque le démarrage du lot 1 ; **P2** = à connaître avant la mise en recette ; **P3** = plus tard.

| # | Prio | Question | Bloque | Recommandation par défaut |
|---|---|---|---|---|
| **Q-A1** | **P1** | **Le service IA interne** : quel format d'API (compatible avec l'API de conversation standard ?) ; quels **modèles** (nom, taille de contexte) ; supporte-t-il la **sortie structurée contrainte** (schéma JSON) ; propose-t-il des **embeddings** ; **limites** de débit et de taille ; **disponibilité** ; fournisseur ? | Port IA, qualité d'extraction, recherche sémantique (ADR 007, 019) | Adaptateur « API de conversation standard » ; si pas de sortie structurée : validation par schéma + nouvelle tentative ; si pas d'embeddings : conteneur local |
| **Q-A2** | **P1** | **Quel niveau de classification maximal** le service IA est-il autorisé à traiter ? (N3 ? N4 ? défense ?) | Politique d'envoi à l'IA ; analyse des rapports de sécurité (fichier 04 §7) | N3 maximal ; au-delà : traitement **sans IA** |
| **Q-A3** | **P1** | **Fournisseur d'identité** : OIDC, SAML, LDAP/Active Directory ? Y a-t-il des **groupes** exploitables pour attribuer des rôles ? | Authentification et rôles automatiques (ADR 011) | OIDC ; groupes pour les rôles par défaut |
| **Q-A4** | **P1** | **Équipe plateforme** : quel **registre d'images** interne, quel **proxy**, quel **outil de supervision**, quel **antivirus** ? Quelle **forge/CI** (GitLab auto-hébergé ?) ? | Chaîne de livraison, profils du Compose | Registre et CI de l'organisme ; profil `obs` si pas d'outil |
| **Q-A5** | **P1** | **Réseau isolé** (aucun accès Internet sortant) ? Un **miroir interne de paquets** (npm, images) existe-t-il ? | Dépendances, images, modèles | Concevoir **sans accès sortant** à l'exécution (déjà le cas) |
| **Q-A6** | P2 | **Chiffrement applicatif** des contenus N4 nécessaire, ou le chiffrement du support suffit-il ? | ADR 009 | Support seulement au lot 1 |
| **Q-A7** | P2 | **Stockage des documents** : volume local, NAS, ou stockage objet compatible S3 ? | ADR 010 | Volume (défaut), adaptateur S3 si disponible |
| **Q-A8** | P2 | **Sauvegardes** : RPO/RTO acceptables ? Outil de sauvegarde imposé ? | Fichier 06 §4 | RPO ≤ 24 h, RTO ≤ 4 h |
| **Q-A9** | P2 | **Jira** : version (service hébergé ou serveur de l'organisme), droits d'API, projets concernés, et **outil d'imputation des temps** (export, API ?) | Connecteurs (lots 2 et 3) | Connecteur par API ; export fichier en secours |
| **Q-A10** | P2 | **Courriel** : relais SMTP interne disponible ? | Notifications | SMTP interne |
| **Q-A11** | P2 | **Bibliothèque UI** : charte de l'État (système de design) exigée, ou charte propre ? | ADR 015 | PrimeVue avec thème configurable ; Vue DSFR si la charte de l'État est exigée |
| **Q-A12** | P2 | **Navigateurs et postes** à supporter (versions, accessibilité, postes d'agents) | Front | Navigateurs courants à jour (2 versions majeures) |
| **Q-A13** | P3 | **Homologation de sécurité / audit** de la plateforme exigés ? Quand ? | Planning | Tests d'intrusion avant mise en service (recommandé) |
| **Q-A14** | P3 | **Plan de reprise** : un second site est-il disponible ? | Haute disponibilité | Non requis (ET-14) |
| **Q-A15** | P3 | **Licence** du code (libre ou non) : impacts sur les dépendances et la publication | Choix des bibliothèques | À décider avec Q-13 (spécifications) |

## 2. Hypothèses d'architecture à valider

| # | Hypothèse | Si fausse |
|---|---|---|
| H-A1 | Le service IA est joignable depuis le réseau du Compose et accepte des appels de plusieurs workers | Prévoir un point de sortie dédié ou une passerelle |
| H-A2 | Le service IA est **assez performant** pour analyser ~100 rapports/jour (quelques dizaines de millisecondes par jeton, contextes de quelques dizaines de milliers de jetons) | Réduire l'ambition (analyse par lots, priorisation), ou changer de modèle |
| H-A3 | L'IA française d'extraction **atteint** les seuils de qualité du lot 1 avec des invites bien conçues | Renforcer les gabarits structurés ; abaisser les seuils ; affiner les invites ; modèle plus gros |
| H-A4 | PostgreSQL suffit pour la recherche texte, les vecteurs et la file | Moteur de recherche dédié derrière `search` (ADR 013) |
| H-A5 | Les documents de l'organisme sont majoritairement **des formats bureautiques courants** | Étendre l'extraction (OCR, formats spécifiques) |
| H-A6 | Le Compose est accepté par l'équipe plateforme comme **mode de déploiement de production** | Prévoir le chart pour l'orchestrateur de l'organisme dès le départ |

## 3. Prototypes à mener avant de figer (« spikes »)

Chaque prototype a une **durée courte**, un **but unique**, des **critères de réussite** et produit une **décision** consignée dans le journal des ADR.

| # | Prototype | Durée | But | Critères de réussite | Décision éclairée |
|---|---|---|---|---|---|
| **S1** | **Extraction de texte** sur 50 à 100 documents réels (ou représentatifs) | 3 j | Comparer 2 ou 3 moteurs d'extraction | ≥ 95 % de documents lus ; **tableaux** exploitables ; aucun échec de sécurité (documents piégés) ; empreinte mémoire maîtrisée | ADR 014 |
| **S2** | **Extraction de faits par le service IA** sur le corpus de référence (lot 1 fichier 05) | 5 j | Mesurer rappel/précision, preuve mot à mot, sortie structurée, injection, refus | Seuils du lot 1 §IAX atteints **ou** plan d'amélioration clair ; 0 injection exécutée | ADR 007, 019 ; H-A2, H-A3 |
| **S3** | **Droits + recherche** : sécurité par ligne et filtre dans une requête de recherche (texte + vecteurs) sur 2 M d'extraits | 4 j | Valider la perf et la **correction** (zéro fuite) | 0 résultat non autorisé sur un jeu de principaux de test ; requête < 300 ms au 95e centile | ADR 008, 013 |
| **S4** | **File de tâches** : pg-boss vs Graphile Worker | 2 j | Fiabilité, réessais, périodique, visibilité | Pas de perte sur arrêt brutal ; priorités ; observabilité | ADR 017 |
| **S5** | **UI** : PrimeVue vs Vue DSFR sur 3 écrans (E-02, E-06, E-25) | 3 j | Accessibilité, thème configurable, productivité | Audit d'accessibilité ; thème changé sans développement | ADR 015 |
| **S6** | **Journal chaîné** et points de contrôle | 2 j | Vérifier l'intégrité et le coût | Détection d'une altération simulée ; débit | ADR 018 |
| **S7** | **Accès aux données** : Drizzle vs Kysely sur les requêtes critiques (faits historisés, droits, recherche) | 2 j | Lisibilité, types, performance | Requêtes critiques propres et testées | ADR 016 |
| **S8** | **Connecteur Jira** (lecture projets, versions, états) | 3 j | Faisabilité du lot 2 | Récupération incrémentale fiable | Q-A9 |

**Total** : environ **24 jours-personne**, parallélisables en **2 à 3 semaines**.

## 4. Plan de démarrage (squelette marchant)

Objectif : obtenir **tôt** un parcours **de bout en bout, minimal mais réel**, qui exerce **toutes** les couches et **les garanties de sécurité**, avant de construire les fonctionnalités.

| Étape | Livrable |
|---|---|
| 0 | Dépôt, chaîne de livraison, Compose de développement, **vérification des frontières de modules**, simulateur d'IA |
| 1 | `access` : principal, rôles, périmètres, niveaux, **droits dérivés** et **sécurité par ligne** ; **tests de propriété** |
| 2 | `reports` : dépôt d'un document, stockage par empreinte, états ; **API + écran E-02 minimal** |
| 3 | `platform` : outbox, file, consommateur idempotent, SSE |
| 4 | `analysis` : pipeline **avec simulateur** (extraction, validation de preuve, rattachement), faits F0 |
| 5 | `facts` : revue (E-06 minimal), confirmation, historique, **journal d'audit chaîné** |
| 6 | `rules` : santé d'une application (fonction pure + paramètres versionnés) ; **« Pourquoi ? »** |
| 7 | `dashboards` : une tuile (L1-I01) avec fiabilité et fraîcheur |
| 8 | Remplacement du simulateur par le **service IA réel** ; **évaluation** sur le jeu de référence |

Le squelette est **terminé** quand les tests **T-DRO, T-NOM, T-SEC, T-AUD** du lot 1 sont **verts** sur ce parcours minimal.

## 5. Risques d'architecture

| Risque | Gravité | Atténuation |
|---|---|---|
| Qualité insuffisante de l'IA interne | Haute | Prototype S2 précoce ; gabarits structurés ; rôle central de la revue humaine ; modèle interchangeable |
| Fuite via l'assistant ou l'IA | **Critique** | Filtre de droits **avant** l'invite ; modèle sans outil ; sécurité par ligne ; tests de propriété |
| Dérive des frontières de modules | Moyenne | Vérification automatique en intégration continue |
| PostgreSQL saturé (recherche + vecteurs + file) | Moyenne | Supervision ; ports isolant `search` et la file ; réplique de lecture |
| Exploitation sous-estimée | Moyenne | Équipe plateforme associée dès S0 ; runbooks ; restauration testée |
| Documents piégés | Haute | Extraction isolée ; limites ; antivirus optionnel |
| Dépendance à un service IA unique | Moyenne | Port + simulateur + mode dégradé |
| Chaîne d'approvisionnement | Moyenne | Miroir interne, verrouillage, SBOM, images épinglées |
| Dette technique d'Odin | Moyenne | Budget récurrent ; Odin se mesure lui-même |
