# 02. Acteurs, rôles, périmètres et droits

## 1. Personas

| Persona | Contexte | Ce qu'il attend d'Odin | Ce qui le ferait renoncer |
|---|---|---|---|
| **Camille, développeuse** (équipe applicative) | Écrit des comptes rendus techniques, signale de la dette, post-mortems | Déposer vite, ne pas ressaisir, voir que son signal est pris en compte | Formulaire long ; sentiment d'être surveillée ; aucun retour |
| **Karim, chef de projet** | Rapport d'avancement mensuel, dépendances, budget du projet | Un seul rapport qui alimente tout ; moins de relances | Double saisie ; indicateurs contradictoires avec ce qu'il a déclaré sans explication |
| **Nadia, responsable d'application** | Porte une application (évolutions, incidents, fin de support) | Une fiche vivante, alimentée par les rapports, et qui défend son budget | Données obsolètes ; fiche qu'elle doit tout remplir |
| **Paul, chef de bureau / responsable d'équipe** | Équipe de 8 personnes, plan de charge, recrutement | Capacité vs demande, vacances de postes, besoins de compétences | Vue individuelle exigée par la hiérarchie ; chiffres jugés injustes |
| **Sophie, architecte / urbaniste** | Cartographie, trajectoires, principes d'architecture | Référentiel qui se met à jour avec les rapports ; analyses d'impact | Référentiel périmé, double maintenance |
| **Marc, RSSI** | Posture, risques, évaluations de sécurité, audits | Remontées de sécurité reliées aux applications ; dossier pour la direction | Confidentialité insuffisante des contenus sensibles |
| **Léa, contrôleuse de gestion SI** | Budget, exécution, coûts par service | Consolidation de la dépense numérique, run / build | Chiffres hors périmètre budgétaire de l'organisme ; rapprochements manuels |
| **Hélène, responsable RH du numérique** | GEPP, recrutements, profils, prestataires | Capacité par profil, tensions de compétences, dépendances | Outil qui évalue les individus ; données nominatives exposées |
| **Antoine, directeur du numérique (DNUM)** | Arbitrages, comités, relation avec le cabinet et la tutelle | Vue unifiée, scénarios, notes et présentations prêtes, traçabilité | Chiffres non fiables ; rapports non défendables devant un contrôle |
| **Isabelle, secrétaire générale / directrice (lectrice décisionnelle)** | Reçoit synthèses et alertes | Une synthèse claire, des décisions à prendre, peu de jargon | Trop de détails ; jargon technique |
| **Julien, auditeur / contrôle interne** | Vérifie la traçabilité, suit les recommandations | Retrouver qui a décidé quoi, sur quelle base | Historique modifiable ; faits sans source |
| **Sam, prestataire (ESN)** | Contribue sur un périmètre contractuel | Déposer des comptes rendus de mission | Accès trop large ou trop étroit |

## 2. Rôles dans Odin

Un utilisateur peut cumuler plusieurs rôles. Les rôles sont **fonctionnels** (liés à des responsabilités), pas hiérarchiques.

| Code | Rôle | Description |
|---|---|---|
| R01 | **Contributeur** | Tout agent ou prestataire autorisé. Dépose et consulte ses rapports, voit les informations ouvertes et celles de son périmètre. Rôle par défaut de tous. |
| R02 | **Contributeur externe** | Prestataire : dépose uniquement sur les périmètres (projets, applications) qui lui sont ouverts ; lecture limitée à ce qu'il a déposé et aux éléments explicitement partagés. |
| R03 | **Responsable d'application** | Propriétaire d'une ou plusieurs applications : valide les faits la concernant, maintient la fiche, répond aux demandes de précision. |
| R04 | **Responsable de projet / d'initiative** | Valide les faits d'un projet, porte les rapports officiels d'avancement, les jalons et bénéfices. |
| R05 | **Responsable d'équipe** | Voit les informations agrégées de son équipe (capacité, charge, rapports déposés), jamais de vue individuelle (RG-01). |
| R06 | **Architecte / urbaniste** | Maintient le patrimoine (services rendus, flux, technologies), valide les rattachements, mène les analyses d'impact. |
| R07 | **Responsable sécurité (RSSI) et correspondants** | Voit et valide les faits de sécurité et de risque ; accède aux contenus sensibles de sécurité. |
| R08 | **Délégué à la protection des données (DPO)** | Accède aux éléments de conformité des données personnelles et à la journalisation d'usage de l'IA ; reçoit les alertes de données personnelles. |
| R09 | **Contrôle de gestion SI / finances** | Gère budgets, dépenses, imputations, consolidation. |
| R10 | **RH du numérique (GEPP)** | Gère profils, compétences, vacances de postes, capacité par profil ; accède aux données RH **agrégées par rôle**. |
| R11 | **Achats / marchés** | Gère contrats, marchés, licences, échéances. |
| R12 | **PMO / bureau de portefeuille** | Qualifie les demandes, prépare l'arbitrage, tient le portefeuille et les roadmaps. |
| R13 | **Décideur (DNUM, directions)** | Arbitre, décide, valide les notes de décision, consulte la vue stratégique. |
| R14 | **Lecteur de direction** (secrétariat général, cabinet, tutelle) | Lecture des synthèses, des alertes et des restitutions ; aucune saisie technique. |
| R15 | **Auditeur / contrôle interne** | Lecture seule étendue, accès au journal et aux preuves ; pas d'accès aux contenus sensibles hors habilitation. |
| R16 | **Curateur de connaissance** | Valide en second niveau les faits extraits (par domaine) ; traite les rattachements ambigus. Rôle attribuable à un référent par domaine. |
| R17 | **Administrateur fonctionnel** | Paramètre référentiels, gabarits, seuils, droits ; n'a pas accès aux contenus sensibles par défaut. |

## 3. Périmètres de visibilité

Chaque contenu (rapport, fait, objet) a un **niveau de classification** et un **périmètre**.

### 3.1 Niveaux de classification des contenus

| Niveau | Description | Qui voit par défaut |
|---|---|---|
| **N1. Ouvert** | Consultable par tout utilisateur authentifié de l'organisme | Tous (hors R02 sauf partage) |
| **N2. Périmètre** | Réservé à un périmètre (équipe, direction, application, projet) | Membres du périmètre + rôles de gouvernance habilités |
| **N3. Restreint** | Réservé à une liste nommée de personnes ou de rôles | Liste explicite |
| **N4. Sensible** | Sécurité, risques cyber, données personnelles, RH agrégé, éléments juridiques | Rôles dédiés (R07, R08, R10…) et personnes autorisées par eux |

- Le niveau par défaut d'un rapport est **N2** (périmètre de son rattachement). L'auteur peut le **restreindre** (N3) mais ne peut pas l'élargir au-delà de ce que son rôle l'autorise.
- Une **suggestion automatique de niveau** est faite à l'auteur (ex. détection de contenu de sécurité → N4 proposé) ; l'auteur ou un référent confirme (voir IA-07).
- Les **niveaux de classification sont configurables** par l'organisme (libellés, nombre, règles d'habilitation), y compris des niveaux de diffusion restreinte ou de défense ; **tout contenu est admissible** (D7). La protection repose sur le cloisonnement et les habilitations ; l'**habilitation des personnes** à chaque niveau relève de l'organisme. Les quatre niveaux ci-dessus sont le jeu par défaut.

### 3.2 Principe de dérivation

Un fait, une synthèse, une réponse ou un rapport généré hérite du **niveau le plus élevé** des sources qu'il utilise (RG-04).

### 3.3 Périmètres

Un périmètre est un ensemble d'objets : une équipe, une direction, une application, un projet, un programme budgétaire, un domaine (sécurité, RH, finances). Les droits s'attribuent à un rôle **sur un périmètre**.

## 4. Matrice des droits (synthèse)

Légende : **L** lecture · **C** création/dépôt · **V** validation · **M** modification · **A** administration · **–** aucun.
Les droits s'exercent **dans le périmètre** attribué (sauf mention « tout »).

| Fonction \ Rôle | R01 Contrib. | R02 Externe | R03 Resp. appli | R04 Resp. projet | R05 Resp. équipe | R06 Archi | R07 RSSI | R09 Contrôle gestion | R10 RH | R12 PMO | R13 Décideur | R14 Lecteur | R15 Audit | R16 Curateur | R17 Admin |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Déposer un rapport | C | C (périmètre) | C | C | C | C | C | C | C | C | C | – | – | C | – |
| Voir ses rapports | L | L | L | L | L | L | L | L | L | L | L | – | – | L | – |
| Voir les rapports du périmètre (N2) | L | – | L | L | L | L | L | L | L | L | L | – | L | L | – |
| Confirmer les faits de ses propres rapports | V | V | V | V | V | V | V | V | V | V | V | – | – | V | – |
| Valider les faits d'une application | – | – | V | – | – | V | V (sécurité) | – | – | – | – | – | – | V | – |
| Valider les faits d'un projet | – | – | – | V | – | – | – | V (budget) | V (ETP) | V | – | – | – | V | – |
| Maintenir la fiche application | – | – | M | – | – | M | – | – | – | – | – | – | – | M | – |
| Gérer demandes et portefeuille | C (demande) | – | C | C | C | C | C | C | C | M | V | L | L | – | – |
| Gérer roadmaps | L | – | L | M (ses initiatives) | L | M | L | L | L | M | V | L | L | – | – |
| Gérer dette | C | – | M | – | C | M | C | – | – | L | V (priorisation) | L | L | – | – |
| Gérer ressources (agrégé) | – | – | – | L | L (son équipe) | L | – | L | M | L | L | L (synthèse) | L | – | – |
| Gérer finances | – | – | L (son appli) | L (son projet) | – | – | – | M | – | L | L | L (synthèse) | L | – | – |
| Gérer contrats et marchés | – | – | L (son appli) | L (son projet) | – | L | – | L | – | L | L | L (synthèse) | L | – | – |
| Sécurité et risques (N4) | C (signal) | – | L (son appli) | L (son projet) | – | L | M | – | – | L | V (acceptation) | L (synthèse) | L (habilité) | – | – |
| Contraintes et échéances | L | – | L | L | L | L | M (sécurité) | L | L | L | V | L | L | – | A |
| Décisions et comités | L (publiques) | – | L | L | L | L | L | L | L | M | V | L | L | – | – |
| Générer rapports / présentations | C (son périmètre) | – | C | C | C | C | C | C | C | C | C | L | – | – | – |
| Assistant (questions) | C | C (périmètre) | C | C | C | C | C | C | C | C | C | C | C | C | C |
| Paramétrer référentiels et droits | – | – | – | – | – | – | – | – | – | – | – | – | – | – | A |
| Consulter le journal d'audit | – | – | – | – | – | – | L (sécurité) | – | – | – | – | – | L | – | L (limité) |

Le rôle **R08 (DPO)** voit le registre d'usage de l'IA, les alertes de données personnelles et les contenus de conformité des données ; il n'a pas accès aux autres contenus N4 sans habilitation.

## 5. Règles d'accès complémentaires

- **A-01.** Un utilisateur ne voit jamais, dans une synthèse, une réponse de l'assistant ou un rapport généré, d'information qu'il n'aurait pas pu consulter directement (RG-04).
- **A-02.** Les vues relatives aux ressources sont **agrégées par équipe, profil ou rôle**. Aucune vue ne présente de charge, de productivité ou de « performance » par personne (RG-01). Pas de classement entre personnes.
- **A-03.** L'**effectif minimal d'agrégation** (valeur par défaut proposée : 5 personnes ; paramétrable) conditionne l'affichage de toute métrique d'équipe ; en deçà, la métrique est remontée au niveau supérieur ou masquée (RG-02).
- **A-04.** Les accès à des contenus N4 sont **journalisés** et consultables par le DPO et l'auditeur.
- **A-05.** Les droits des prestataires (R02) sont limités dans le temps (date de fin liée au contrat) et révoqués automatiquement à l'échéance.
- **A-06.** Les **délégations** (absence, intérim) sont possibles pour les rôles de validation (R03, R04, R13), tracées et limitées dans le temps.
- **A-07.** À la **mobilité ou au départ** d'un agent, ses rôles sont suspendus et ses objets (applications, projets, validations en attente) doivent être réattribués (parcours P-26).
- **A-08.** Le niveau N4 d'un rapport ne peut être abaissé que par un rôle habilité du domaine concerné (ex. R07 pour la sécurité).
- **A-09.** **Rôles de pilotage** (sponsor, administrateurs fonctionnels, curateurs, responsables des gabarits) : ils ne sont pas portés par un profil unique ; **différents profils peuvent les tenir**, attribués par l'organisme (D11). Dans une organisation d'environ 300 personnes, une même personne cumule souvent plusieurs rôles : l'interface s'adapte à la **combinaison** de rôles.
