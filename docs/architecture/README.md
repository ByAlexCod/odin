# Odin : architecture

Version 0.1 (proposition à discuter), 11 novembre 2026. Phase **technique**, distincte des spécifications métier (`../specifications/`).

## Contraintes données

- Front **Vue.js** · back **TypeScript sans NestJS** · tout dans un **Docker Compose** (sauf le serveur de modèle de langue) · **service IA interne** déjà fourni · équipe de **6 à 15 personnes** avec équipe de plateforme · **auto-hébergé**, environnement exact **inconnu** · ~300 utilisateurs.

## Proposition en bref

| Sujet | Proposition |
|---|---|
| Style | **Monolithe modulaire** TypeScript : un code, **deux processus** (API, worker), modules à frontières strictes |
| Base de données | **PostgreSQL unique** : relationnel, historique, recherche texte, vecteurs, file de tâches, journal, **sécurité par ligne** |
| « Bus de données » | **Pas de courtier externe** : **outbox transactionnelle** + file PostgreSQL, événements **sans contenu**, consommateurs idempotents ; **relais vers un courtier prévu** si les déclencheurs apparaissent |
| IA | **Port `ai-gateway`** vers le service interne ; **le modèle n'agit pas** ; validation déterministe (preuve mot à mot, schémas, candidats fermés) ; récupération **filtrée par droits avant l'invite** ; mode dégradé |
| Sécurité | **Contrôle d'accès central** + **sécurité par ligne** ; **aucun champ d'évaluation de personnes** ; journal **chaîné** immuable ; extraction de fichiers **isolée** |
| Front | **Vue 3** monopage, Vite, Pinia, TanStack Query ; bibliothèque UI **à décider** (PrimeVue ou DSFR) |
| Back | **Node.js + TypeScript strict**, **Fastify**, schémas partagés, requêtes typées proches du SQL (Drizzle ou Kysely) |
| Déploiement | **Compose de référence** (profils `core`, `av`, `embeddings`, `obs`, `dev`), **portable** vers Kubernetes ; aucune dépendance Internet à l'exécution |

## Plan du dossier

| Fichier | Contenu |
|---|---|
| [01-contraintes-et-principes.md](01-contraintes-et-principes.md) | Contraintes, exigences issues des spécifications, qualités, principes |
| [02-vue-d-ensemble.md](02-vue-d-ensemble.md) | Style, contexte et conteneurs (schémas), modules, flux clés |
| [03-donnees-et-evenements.md](03-donnees-et-evenements.md) | Base de données, modèle de faits, documents, **bus d'événements**, alimentations, droits dérivés |
| [04-ia.md](04-ia.md) | Port IA, pipeline d'analyse, confiance, assistant sûr, qualité, résilience |
| [05-securite-et-acces.md](05-securite-et-acces.md) | Authentification, autorisation (deux lignes de défense), menaces, secrets, journal |
| [06-deploiement-et-exploitation.md](06-deploiement-et-exploitation.md) | Compose, environnements, mises à jour, sauvegardes, observabilité, runbooks |
| [07-stack-et-conventions.md](07-stack-et-conventions.md) | Bibliothèques, patterns, API, structure du dépôt, tests, livraison, équipes |
| [08-decisions-adr.md](08-decisions-adr.md) | Journal des 20 décisions (statut, alternatives, réexamen) |
| [09-questions-ouvertes-et-prototypes.md](09-questions-ouvertes-et-prototypes.md) | Questions à trancher, hypothèses, 8 prototypes, plan de démarrage |

## Ce qui est décidé, proposé, à décider

- **Acceptés** (contraintes du commanditaire) : Vue ; TypeScript sans NestJS ; Compose de référence.
- **Proposés** (à valider ensemble) : monolithe modulaire, PostgreSQL unique, outbox sans courtier, port IA avec modèle sans outil, accès central + sécurité par ligne, OIDC, journal chaîné, SPA + SSE.
- **À décider** : bibliothèque UI, accès aux données, file de tâches, embeddings, chiffrement applicatif N4 ; **plusieurs dépendent d'informations sur le service IA et l'environnement** (fichier 09 §1).

## Prochaines étapes suggérées

1. Valider ou amender les **ADR proposés** (fichier 08).
2. Répondre aux **questions P1** (Q-A1 à Q-A5) : surtout le **service IA** (Q-A1, Q-A2).
3. Lancer les **prototypes S1 à S4** (fichier 09 §3).
4. Construire le **squelette marchant** (fichier 09 §4), puis ouvrir le lot 1.
