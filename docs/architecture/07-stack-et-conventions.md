# 07. Pile technique, patterns et conventions

Les **contraintes** viennent du commanditaire (front Vue, back TypeScript sans NestJS, Compose). Les **choix de bibliothèques** sont des **propositions argumentées** ; ceux qui dépendent d'un essai sont marqués **« à trancher par prototype »** (voir fichier 09 §3).

## 1. Vue d'ensemble de la pile

| Couche | Proposition | Alternatives écartées ou en réserve | Statut |
|---|---|---|---|
| Exécution back | **Node.js** (version LTS en vigueur au démarrage, à figer) | Bun, Deno : écosystème de sécurité et support moins établis en environnement institutionnel | Proposé |
| Langage | **TypeScript** en mode strict | JavaScript seul | **Contrainte** |
| Cadre HTTP | **Fastify** : léger, schémas de validation, plugins, bonnes performances | **Hono** (très léger, écosystème Node plus jeune), Express (ancien, peu typé), AdonisJS (plus lourd, convention forte) ; **NestJS écarté** (contrainte) | Proposé |
| Validation et contrats | **Schémas partagés** (Zod ou TypeBox) entre front et back ; **OpenAPI** généré | Validation manuelle | Proposé |
| Accès aux données | **Requêtes typées proches du SQL** : **Drizzle** ou **Kysely** | Prisma (moteur lourd, moins adapté à la sécurité par ligne et aux requêtes avancées) | À trancher par prototype |
| Migrations | **Migrations SQL versionnées** (outil léger, réversibles sur un cycle) | Génération automatique opaque | Proposé |
| File de tâches | **Bibliothèque de file sur PostgreSQL** (pg-boss ou Graphile Worker) | Courtier externe (voir ADR 006) | À trancher par prototype |
| Front | **Vue 3** (API de composition), **Vite**, **TypeScript** | Nuxt (SSR inutile : outil interne ; ajoute un serveur) | **Contrainte** (Vue) ; SPA proposée |
| Gestion d'état front | **Pinia** pour l'état local ; **TanStack Query** pour les données serveur | Vuex (ancien) | Proposé |
| Routage | Vue Router | — | Proposé |
| Internationalisation / vocabulaire | **vue-i18n** (libellés paramétrables par l'organisme) | — | Proposé |
| Bibliothèque de composants | **PrimeVue** (thématisable, riche, proche de la pratique actuelle) **ou Vue DSFR** (système de design de l'État, accessibilité intégrée) | Vuetify, Quasar | **À décider** (ADR 015) |
| Temps réel | **SSE** (flux serveur → navigateur) pour la progression et les notifications | WebSocket : inutile ici, plus complexe à exploiter | Proposé |
| Journalisation | Journaux structurés ; **OpenTelemetry** | — | Proposé |
| Tests | **Vitest** (unitaires, intégration), **Playwright** (bout en bout), **axe** (accessibilité), **Testcontainers** (base réelle en test), **k6** (charge) | — | Proposé |

## 2. Style d'architecture interne : « hexagonal » par module

Chaque module respecte la même organisation :

```
modules/<nom>/
  domain/          règles métier pures : entités, valeurs, machines à états, fonctions de calcul
                   (aucune dépendance au cadre HTTP, à la base ou à l'IA)
  application/     cas d'usage (commandes et requêtes), transactions, publication d'événements
  ports/           interfaces vers l'extérieur du module (dépôts, IA, stockage, horloge…)
  infrastructure/  adaptateurs : requêtes SQL, appels IA, stockage, connecteurs
  http/            routes, schémas, présentation des erreurs
  index.ts         interface publique du module (seul point d'entrée autorisé)
```

**Avantages** : le métier est **testable sans infrastructure** ; l'IA, le stockage ou Jira sont **remplaçables** ; les règles de santé et d'indicateurs sont des **fonctions pures**.

## 3. Règles de modularité (vérifiées automatiquement)

1. **Un module n'importe que l'interface publique** (`index.ts`) d'un autre module ; jamais ses fichiers internes.
2. **Un module n'accède pas aux tables d'un autre** (schéma propre, droits de base distincts).
3. **Pas de cycle** de dépendances ; **sens** défini au fichier 02 §4.
4. **Communication** : appel **synchrone** via l'interface publique pour les **requêtes** ; **événements** (outbox) pour les **réactions** et tout ce qui peut être **asynchrone**.
5. **Les règles de dépendance sont des tests** : un outil de vérification (règles de frontières) **échoue la construction** en cas de violation.
6. **Les droits d'accès** : chaque lecture passe par un dépôt qui **exige un principal** (fichier 05 §2).

## 4. Patterns retenus

| Pattern | Où | Pourquoi |
|---|---|---|
| **Ports et adaptateurs** | IA, stockage, courriel, connecteurs, horloge | Remplaçabilité, tests, mode dégradé |
| **Événements de domaine + outbox transactionnelle** | Toute réaction inter-modules | Cohérence sans courtier (ADR 006) |
| **CQRS léger (projections)** | Santé, indicateurs, tâches, files | Lectures rapides, **reproductibles**, expliquées |
| **Machines à états explicites** | Rapport, fait, demande de précision, analyse, demande → initiative | Transitions **autorisées et testées** (fichier 02 du lot 1 §4, §7) |
| **Dépôt exigeant un principal** | Accès aux données | Impossible d'oublier le filtre de droits |
| **Spécification (prédicats composables)** | Règles d'accès, de santé, de contradiction | Lisibles, testables, traduisibles en SQL |
| **Règles en données, calculs purs** | Santé, indicateurs, priorisation (lot 2) | Reproductibilité, simulation d'impact |
| **Couche anticorruption** | Jira, temps, fichiers | Isoler les formats externes |
| **Idempotence et réessais** | Consommateurs d'événements, tâches, connecteurs | Fiabilité asynchrone |
| **Disjoncteur (circuit breaker)** | Appels au service IA et aux intégrations | Mode dégradé |
| **Concurrence optimiste** | Fiches, faits (colonne de version) | Pas de verrou long ; conflits visibles (E-04) |
| **Journal d'audit transversal** | Intercepteur au niveau des cas d'usage | Aucune action sensible sans trace |
| **Configuration en base, versionnée** | Seuils, gabarits, classification, vocabulaire | Administration sans développement (X8) |

## 5. Conventions d'API

| Sujet | Règle |
|---|---|
| Style | **REST/JSON** orienté ressources ; **OpenAPI** généré à partir des schémas ; client typé généré pour le front |
| Versionnement | Préfixe de version (`/api/v1`) ; **compatibilité** : un changement non rétrocompatible = nouvelle version ; **contrôle automatique** de différence d'interface en intégration continue |
| Erreurs | Format standard (type, titre, détail, **code** stable référencé aux textes MSG) ; **pas de détail interne** ; **réponses neutres** pour les accès refusés (RG-04) |
| Pagination | Par curseur ; tri et filtres **explicites et bornés** |
| Idempotence | En-tête de clé d'idempotence sur les créations sensibles (dépôt, import) |
| Fichiers | Dépôt par **flux** (pas de chargement en mémoire) ; types et tailles contrôlés ; **liens d'accès à durée courte** pour la lecture |
| Progression | **SSE** (abonnement par utilisateur) ; événements de **statut** (analyse), **notification** ; **reprise** après coupure |
| Sécurité des routes | **Liste blanche** testée : aucune route de classement/comparaison de personnes (fichier 05 §3) |
| Journalisation des requêtes | Identifiant de corrélation ; **aucun contenu** |

## 6. Structure du dépôt (proposition)

```
odin/
  apps/
    web/                  application Vue
    server/               points d'entrée : api, worker, migrate (même image)
  modules/                les modules métier (fichier 02 §4)
  packages/
    contracts/            schémas partagés, types, OpenAPI
    ai-gateway/           port IA, invites versionnées, schémas de sortie, garde-fous
    extraction-client/    client du service d'extraction
    testing-kit/          jeux de données fictifs, simulateur d'IA, principaux de test
  deploy/
    compose/              Compose de référence, profils, exemples de variables
    runbooks/             procédures d'exploitation
  evaluation/             jeu de référence de l'IA et harnais d'évaluation
  docs/                   spécifications, architecture, décisions
```

Gestion du dépôt : **monorepo** (un seul langage, schémas partagés front/back) ; gestionnaire de paquets avec espaces de travail ; **numérotation unique** des versions.

## 7. Stratégie de tests (pyramide adaptée aux exigences critiques)

| Niveau | Contenu | Outils | Bloquant ? |
|---|---|---|---|
| **Unitaires** | Règles de domaine : santé, contradiction, machines à états, héritage de niveau, agrégation | Vitest | Oui |
| **Propriété** | « Aucun résultat non autorisé quel que soit le principal » ; « la santé est déterministe » | Tests de propriété | **Oui** |
| **Intégration** | Cas d'usage avec **base réelle** (conteneur jetable) ; **politiques de sécurité par ligne** ; outbox ; file | Vitest + Testcontainers | Oui |
| **Contrat** | API (différence OpenAPI), événements (schémas), port IA (simulateur) | Contrôle de schéma | Oui |
| **IA : jeu de référence** | Extraction, rattachement, refus, injection, non-évaluation | Harnais d'évaluation | **Oui** (seuils du lot 1 §IAX) |
| **Bout en bout** | Parcours P-01, P-02, P-05, P-22, P-23 | Playwright | Oui (cœur) |
| **Accessibilité** | Écrans clés | axe + revue manuelle | Oui (cœur) |
| **Sécurité** | Dépendances, secrets, analyse statique, images | Outils de la chaîne | Oui |
| **Charge** | 300 utilisateurs, dépôts simultanés, assistant | k6 | Avant mise en service |
| **Recette** | **Les 219 cas du lot 1** (fichier 04 du lot) | Manuel + automatisé | Avant mise en service |

Les cas de test du lot 1 sont **la source** des tests automatisés : chaque `T-xxx-nn` correspond à un test (ou une vérification manuelle identifiée).

## 8. Chaîne de livraison (intégration et déploiement continus)

Étapes (ordre) : installation à partir du **fichier de verrouillage** → typage et règles de frontières → tests unitaires et de propriété → tests d'intégration (base réelle) → contrats d'interface → **évaluation IA sur simulateur** (déterministe) → construction des images → **SBOM, analyse, signature** → **bout en bout** sur Compose éphémère (avec **axe**) → publication au registre interne → déploiement en recette.

**Nightly** : évaluation IA sur **modèle réel** (détection de dérive) ; test de restauration périodique ; scan de dépendances.

**Règles** : aucune fusion sans revue ; **mainline** protégée ; versions **étiquetées** ; **notes de version** générées.

## 9. Organisation de l'équipe (proposition, 6 à 15 personnes)

| Équipe | Modules | Compétences |
|---|---|---|
| **Cœur et sécurité** | `access`, `audit`, `platform`, `referential`, `ingestion` | Back, base de données, sécurité |
| **Contribution et IA** | `reports`, `analysis`, `ai-gateway`, `facts`, `assistant`, `search` | Back, traitement de texte, évaluation IA |
| **Décision et expérience** | `rules`, `dashboards`, `notifications`, front | Front, UX, calculs |
| **Plateforme / exploitation** (équipe existante) | Compose, CI, sauvegardes, observabilité | Exploitation |
| **Transverse** | Product owner, UX, QA, représentant sécurité/DPO | — |

Conway : les **frontières d'équipes suivent les frontières de modules**, pour que l'ajout d'un module n'exige pas de coordination massive.

## 10. Définition de « prêt à développer » pour le lot 1

- Décisions **Q-A1 à Q-A5** (fichier 09) **tranchées**.
- **Prototypes S1 à S4** réalisés (fichier 09 §3) avec résultats consignés.
- **Squelette marchant** (« walking skeleton ») opérationnel : dépôt → analyse **simulée** → faits → revue → indicateur → journal, **avec droits et RLS**, dans le Compose.
- Chaîne de livraison **verte** sur le squelette.
