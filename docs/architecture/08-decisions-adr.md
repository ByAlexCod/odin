# 08. Journal des décisions d'architecture (ADR)

Statuts : **Accepté** (contrainte du commanditaire), **Proposé** (recommandation à valider ensemble), **À décider** (dépend d'une information ou d'un prototype). Chaque ADR indique ce qui nous ferait **le réexaminer**.

| # | Titre | Statut |
|---|---|---|
| 001 | Monolithe modulaire | Proposé |
| 002 | TypeScript sur Node, sans NestJS ; cadre HTTP léger | **Accepté** (langage, sans NestJS) / Proposé (Fastify) |
| 003 | Front Vue 3 en application monopage | **Accepté** (Vue) / Proposé (monopage) |
| 004 | Docker Compose comme déploiement de référence | **Accepté** |
| 005 | PostgreSQL comme base unique | Proposé |
| 006 | Pas de courtier de messages : outbox + file sur PostgreSQL | Proposé |
| 007 | Port `ai-gateway` ; le modèle n'a aucun outil | Proposé |
| 008 | Contrôle d'accès central + sécurité par ligne | Proposé |
| 009 | Chiffrement d'enveloppe des contenus N4 | À décider |
| 010 | Stockage des documents derrière `BlobStore` | Proposé |
| 011 | Authentification par OpenID Connect | Proposé |
| 012 | Observabilité au format OpenTelemetry | Proposé |
| 013 | Recherche texte et vecteurs dans PostgreSQL | Proposé |
| 014 | Extraction de texte par un service isolé | Proposé (moteur à choisir) |
| 015 | Bibliothèque de composants Vue | À décider |
| 016 | Accès aux données : Drizzle ou Kysely | À décider (prototype) |
| 017 | File de tâches : pg-boss ou Graphile Worker | À décider (prototype) |
| 018 | Journal d'audit chaîné | Proposé |
| 019 | Embeddings : service IA, conteneur local ou différé | À décider (Q-A1) |
| 020 | Monopage sans rendu serveur ; SSE sans WebSocket | Proposé |

---

## ADR 001. Monolithe modulaire
**Contexte** : ~300 utilisateurs, cohérence forte (droits, historique, journal), équipe de 6 à 15 avec plateforme, volonté de portabilité Compose.
**Décision** : un **seul code** en modules à frontières strictes ; **deux processus** (API, worker) du même code ; services annexes limités (extraction, base).
**Alternatives** : microservices (coûts d'exploitation et de cohérence sans bénéfice) ; monolithe « non modulaire » (dérive rapide).
**Conséquences** : déploiement simple ; refactoring facile ; il faut **faire respecter** les frontières (outil d'analyse).
**Réexamen si** : charge ou autonomie d'équipes imposent d'extraire un module ; le module `analysis` est le premier candidat.

## ADR 002. TypeScript sur Node, sans NestJS
**Contexte** : demande explicite : back TypeScript, **pas de NestJS** (trop lourd).
**Décision** : **Node.js LTS + TypeScript strict**. Cadre HTTP **Fastify** (léger, schémas, plugins).
**Alternatives** : Hono ; Express ; AdonisJS ; tRPC (couplage fort front/back, API non ouverte).
**Conséquences** : moins de conventions imposées que NestJS : **les conventions du fichier 07** les remplacent ; un **gabarit de module** et un **outil de frontières** compensent.
**Réexamen si** : le cadre devient un frein ; la logique étant dans les modules (hors cadre), un changement reste **local**.

## ADR 003. Vue 3 en application monopage
**Décision** : **Vue 3** (API de composition), **Vite**, TypeScript ; **monopage** servie en statique.
**Alternatives** : Nuxt (rendu serveur inutile pour un outil interne).
**Conséquences** : déploiement trivial (fichiers statiques) ; pas de SEO (non requis).

## ADR 004. Docker Compose de référence
**Décision** : le Compose est **la** référence ; tout le système (hors service IA) y fonctionne ; **portabilité** vers d'autres orchestrateurs par construction (fichier 06 §7).
**Conséquences** : on évite les services gérés propriétaires ; les mises à jour sont **simples** mais **sans haute disponibilité** native (acceptable, ET-14).

## ADR 005. PostgreSQL unique
**Contexte** : relationnel, historique, recherche texte, vecteurs, file, journal, sécurité par ligne ; volumes modestes.
**Décision** : **une base PostgreSQL** avec extensions standards.
**Alternatives** : base documentaire + moteur de recherche + courtier + base vectorielle (4 composants à exploiter pour des volumes qui n'en ont pas besoin) ; base relationnelle seule + moteur de recherche externe.
**Conséquences** : **cohérence transactionnelle** ; une technologie à maîtriser ; la base est **critique** (sauvegardes, supervision).
**Réexamen si** : volume de recherche ou de vecteurs dépasse le confort de PostgreSQL ; besoin de recherche avancée (ADR 013).

## ADR 006. Pas de courtier de messages : outbox + file PostgreSQL
**Contexte** : quelques centaines d'événements par jour ; exigence **atomicité données + événement** ; équipe qui n'a pas à exploiter un courtier de plus.
**Décision** : **outbox transactionnelle**, **relais** vers une **file PostgreSQL**, **consommateurs idempotents** ; événements **sans contenu** ; versionnés.
**Alternatives** : Kafka (surdimensionné) ; RabbitMQ / NATS (utiles si plusieurs consommateurs indépendants).
**Conséquences** : un composant de moins ; **contrat d'événement stable** permettant de brancher un courtier plus tard.
**Réexamen si** : plusieurs équipes/services consommateurs ; intégrations en publish/subscribe ; débit de milliers d'événements par seconde ; rejeu massif.

## ADR 007. Port `ai-gateway` ; le modèle n'a aucun outil
**Contexte** : IA externe au Compose ; exigences IA-01, IA-12 ; **service IA non encore décrit** (Q-A1).
**Décision** : interface **stable** (extraction structurée, réponse, synthèse, embeddings, santé) ; **le modèle n'écrit rien** ; **validation déterministe** (preuve mot à mot, schéma, rattachement par candidats fermés, droits) ; **disjoncteur** ; **simulateur** pour les tests ; **jeu de référence** bloquant.
**Conséquences** : un changement de modèle ou de service est **local** ; les garanties de sécurité **ne dépendent pas** du comportement du modèle.
**Réexamen si** : le service impose une API spécifique (nouvel adaptateur, pas de refonte).

## ADR 008. Contrôle d'accès central + sécurité par ligne
**Décision** : module `access` = **seul décideur** ; **dépôts exigeant un principal** ; **politiques de sécurité par ligne** en seconde défense ; tests de propriété.
**Alternatives** : contrôles dans chaque route (risque d'oubli) ; moteur de politiques externe (composant de plus ; l'expressivité requise est modeste).
**Conséquences** : **filtre de droits** appliqué aux recherches et à l'IA **avant** lecture ; surcoût de conception maîtrisé.
**Réexamen si** : les règles de droits deviennent beaucoup plus riches (alors moteur de politiques dédié).

## ADR 009. Chiffrement d'enveloppe des contenus N4
**À décider.** **Option A** : chiffrement du support par l'organisme seulement. **Option B** : en plus, chiffrement **applicatif** des documents N4 (clé de données par document, clé maîtresse externe) : protège contre un accès au stockage **sans** passer par Odin ; coûte en **recherche** (le texte N4 indexé reste sensible) et en **gestion de clés**. **Recommandation provisoire** : **A** au lot 1, **B** si l'organisme l'exige (Q-A6).

## ADR 010. Stockage des documents derrière `BlobStore`
**Décision** : port avec **volume** (défaut) et **S3 compatible** ; adressage par **empreinte** ; accès **toujours via l'API** ; liens à durée courte.
**Conséquences** : migration vers un stockage objet **sans changement métier** ; sauvegarde **cohérente** avec la base.

## ADR 011. Authentification par OpenID Connect
**Décision** : **OIDC** vers l'IdP de l'organisme ; pas de comptes locaux en production ; IdP local en développement.
**Réexamen si** : l'organisme n'expose que de l'ancien (LDAP direct) ; ajouter un adaptateur (Q-A3).

## ADR 012. Observabilité au format OpenTelemetry
**Décision** : **journaux structurés sans contenu**, **métriques**, **traces** ; **format OpenTelemetry** ; outils de l'organisme ou profil `obs`.

## ADR 013. Recherche texte et vecteurs dans PostgreSQL
**Décision** : recherche texte intégral française, trigrammes (noms approchants), **vecteurs** avec **filtre de droits dans la requête**.
**Alternatives** : moteur de recherche dédié ; base vectorielle dédiée (le filtrage de droits y est plus difficile à garantir).
**Réexamen si** : > 10 M d'extraits ou besoins de pertinence avancés.

## ADR 014. Extraction de texte par un service isolé
**Décision** : **conteneur dédié**, sans réseau sortant, ressources bornées. **Moteur à choisir par prototype S1** : (a) serveur d'extraction multi-formats éprouvé (couverture large des formats bureautiques) ; (b) bibliothèques Node par format ; (c) outil d'analyse de documents plus récent (meilleure structure des tableaux, plus lourd).
**Critères** : couverture des formats réels de l'organisme, **qualité des tableaux**, sécurité, empreinte, maintenance.

## ADR 015. Bibliothèque de composants Vue
**À décider.** **PrimeVue** : riche, thématisable, proche de la pratique actuelle de l'équipe. **Vue DSFR** : système de design de l'État, accessibilité pensée pour le secteur public, **moins** de composants de données complexes. **Critères** : accessibilité (niveau visé), charte **configurable par organisme** (ET-12), tableaux/édition riches, maintenance. **Prototype S5**.

## ADR 016. Accès aux données
**À décider (prototype).** **Drizzle** (types, migrations intégrées) ou **Kysely** (constructeur de requêtes très proche du SQL). **Critère clé** : écrire proprement les requêtes avec **sécurité par ligne**, **recherche texte/vecteurs**, **historique**.

## ADR 017. File de tâches
**À décider (prototype).** **pg-boss** ou **Graphile Worker** : fiabilité des réessais, planification périodique, visibilité, priorités, performance, maintenance. **Prototype S4**.

## ADR 018. Journal d'audit chaîné
**Décision** : table **en ajout seul**, **chaînage de condensats**, **points de contrôle exportés**, **vérification** périodique ; droits `UPDATE`/`DELETE` retirés.

## ADR 019. Embeddings
**À décider (Q-A1).** Options A (service IA), B (conteneur local), C (différé). Recommandation fichier 04 §6.

## ADR 020. Monopage ; SSE
**Décision** : application **monopage** sans rendu serveur ; **SSE** pour la progression et les notifications.
