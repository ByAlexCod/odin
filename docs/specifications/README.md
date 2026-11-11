# Odin : spécifications métier et UX

Version 0.1 (brouillon de travail), 11 novembre 2026.
Périmètre : **métier et expérience utilisateur uniquement**. Aucun choix technique (architecture, langages, hébergeur, modèle d'IA, base de données) n'est fait ici ; ils relèvent d'une phase ultérieure.

## Objet du produit en une phrase

Odin est la plateforme où **tous les acteurs d'un organisme public** (agents, développeurs, chefs de projet, architectes, sécurité, finances, RH, direction) **déposent leurs rapports et leurs informations**, où une **intelligence artificielle les comprend et les relie** au patrimoine du système d'information, et d'où la direction **décide** (dette, roadmaps, objectifs, sécurité, ressources, finances, conformité) et **produit ses rapports et présentations**.

**Positionnement** : Odin est une **plateforme d'aide à la décision**, **configurable par chaque organisme** et **auto-hébergée**. Ce n'est pas un outil d'accompagnement des procédures publiques officielles.

## Décisions actées (point de départ de tout le dossier)

| # | Décision | Source |
|---|---|---|
| D0 | Public cible principal : organismes publics ; tout le monde (agents, développeurs, chefs de projet, etc.) peut se connecter et partager des rapports ; l'IA comprend ces rapports et en produit. | Échanges du 11/11/2026 |
| D1 | Odin **évalue des applications et des équipes, jamais des personnes**. Il **peut contenir des données sur les personnes** (noms, profils, compétences, répartition entre projets, temps imputés), essentielles à la planification ; il ne les note, ne les classe ni ne les compare. | Échanges du 11/11/2026 |
| D2 | « Métiers » = **profils RH** (familles et profils de métiers du numérique, compétences). Le sens « capacité métier / mission » devient « **Service rendu** » dans ce dossier. | Échanges du 11/11/2026 |
| D3 | **Un client = un seul organisme** (pas de multi-organismes ni de refacturation entre entités). | Échanges du 11/11/2026 |
| D4 | Cible : **organismes publics, en priorité de l'État**. **Chaque organisme configure son instance selon ses propres règles** (nomenclature budgétaire, rôles, seuils, classification, vocabulaire). Aucun périmètre (ministère, opérateur, sécurité sociale…) n'est codé en dur. | Échanges du 11/11/2026 |
| D5 | **Aide à la décision, pas accompagnement des procédures publiques** : Odin n'embarque ni textes officiels, ni seuils, ni circuits d'avis, ni registre réglementaire. L'organisme peut saisir ses propres **contraintes et échéances externes**. | Échanges du 11/11/2026 |
| D6 | **Auto-hébergé** : chaque organisme héberge sa propre instance ; contenus et traitements d'IA restent dans son infrastructure. | Échanges du 11/11/2026 |
| D7 | **Tous les contenus sont acceptés**, y compris sensibles, de diffusion restreinte ou classifiés ; les **niveaux de classification sont configurables** ; la protection repose sur le cloisonnement et les habilitations, dont la responsabilité revient à l'organisme. | Échanges du 11/11/2026 |
| D8 | **Choix de conception par défaut (à valider)** : les faits sont validés par le **responsable de l'objet** (curateur de domaine optionnel) ; les **autorités** (acceptation de risque, validation de restitutions officielles) sont paramétrables, par défaut le **décideur du périmètre**. | Décision de conception (délégation de l'utilisateur) |
| D9 | **Taille de référence : environ 300 personnes** (utilisateurs potentiels ; à confirmer s'il s'agit de l'organisme entier ou de la seule direction du numérique). | Échanges du 11/11/2026 |
| D10 | **Sources de données disponibles** : outil de suivi de projets (**Jira**), **imputation des temps**, et **finances saisies manuellement** (aucune source automatique). | Échanges du 11/11/2026 |
| D11 | **Rôles de pilotage d'Odin** (sponsor, administration, curation) : **différents profils peuvent les tenir**, attribués par l'organisme ; le cumul de rôles est la norme. | Échanges du 11/11/2026 |
| D12 | **Référentiel de profils** : jeu par défaut **simplifié, proposé par Odin et modifiable** (fichier 09 §5), avec correspondance optionnelle vers un référentiel officiel. | Échanges du 11/11/2026 |

## Plan du dossier

| Fichier | Contenu |
|---|---|
| [01-vision-et-perimetre.md](01-vision-et-perimetre.md) | Vision, objectifs, principes directeurs, périmètre (inclus / exclu), mesures de succès |
| [02-acteurs-roles-et-droits.md](02-acteurs-roles-et-droits.md) | Personas, rôles, périmètres de visibilité, classification des contenus, matrice des droits |
| [03-modele-metier.md](03-modele-metier.md) | Glossaire, objets métier, relations, cycles de vie, niveaux de fiabilité |
| [04-parcours-utilisateurs.md](04-parcours-utilisateurs.md) | 27 parcours détaillés (étapes, alternatives, résultats, critères d'acceptation) |
| [05-exigences-fonctionnelles.md](05-exigences-fonctionnelles.md) | Exigences par module, numérotées et priorisées |
| [06-intelligence-artificielle.md](06-intelligence-artificielle.md) | Ce que l'IA comprend et produit, garde-fous, validation humaine, qualité |
| [07-ux-navigation-et-ecrans.md](07-ux-navigation-et-ecrans.md) | Architecture de l'information, écrans clés (maquettes textuelles), états, notifications, accessibilité |
| [08-regles-de-gestion-et-transverses.md](08-regles-de-gestion-et-transverses.md) | Règles de gestion, confidentialité, droit des agents, audit, exigences transverses |
| [09-annexes-gabarits-et-indicateurs.md](09-annexes-gabarits-et-indicateurs.md) | Gabarits de rapports, catalogue d'indicateurs, exemples de contraintes |
| [10-lots-priorites-et-questions-ouvertes.md](10-lots-priorites-et-questions-ouvertes.md) | Découpage en lots, priorités, critères de recette, questions ouvertes |

## Conventions

- **Identifiants** : `P-nn` parcours ; `EX-<module>-nn` exigence ; `RG-nn` règle de gestion ; `IA-nn` règle propre à l'IA ; `E-nn` écran ; `OBJ-nn` objet métier.
- **Priorités** (méthode MoSCoW) : **M** = indispensable au lot concerné ; **S** = important ; **C** = souhaitable ; **W** = reporté (hors lot courant).
- **Vocabulaire** : voir le glossaire (fichier 03). « Service rendu » remplace « métier/capacité métier » (D2).
- **Règles externes** : Odin n'embarque aucun texte ni procédure officielle (D5) ; nomenclatures, seuils, échéances et contraintes sont des **paramètres de l'organisme**.
- Le **rapport de recherche** (`reports/Axes métier de la stack Odin.md`) est la base de justification ; ses marqueurs [S], [S?], [I], [CG] indiquent la fiabilité de ses affirmations.

## Statut

Brouillon à relire avec le commanditaire. Les points non tranchés sont listés au fichier 10 (« Questions ouvertes ») ; chacun indique ce qu'il bloque.
