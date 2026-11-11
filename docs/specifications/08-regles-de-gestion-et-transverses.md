# 08. Règles de gestion et exigences transverses

## 1. Règles de gestion (RG-nn)

### 1.1 Protection des personnes et confidentialité

| ID | Règle |
|---|---|
| **RG-01** | **Odin n'évalue pas les personnes** (D1). Aucune vue, aucun export, aucune réponse de l'assistant, aucun fait ne présente de jugement, score, classement, charge, productivité ou activité **par personne**. Les objets évalués sont les applications, projets, équipes (agrégés) et services. |
| **RG-02** | **Seuil minimal d'agrégation** : une métrique d'équipe n'est affichée que si l'effectif concerné atteint le seuil (valeur par défaut proposée : 5, paramétrable par l'administrateur avec journal). En deçà, la métrique est remontée au niveau supérieur ou masquée. Les croisements successifs ne doivent pas permettre de déduire une valeur individuelle (par exemple par différence). |
| **RG-03** | **Niveau par défaut** d'un rapport : N2 (périmètre de rattachement). L'auteur peut restreindre ; il ne peut pas élargir au-delà de son habilitation. |
| **RG-04** | **Héritage et droits de lecture** : tout fait, synthèse, réponse, restitution ou notification hérite du niveau le plus élevé de ses sources, et n'est lisible que par ceux qui peuvent lire **toutes** les sources utilisées (ou une version expurgée). L'assistant, les synthèses et les exports respectent cette règle. |
| **RG-05** | **Faits et indicateurs de direction** : un indicateur de direction n'est calculé qu'avec des faits F2 ou F3 ; les faits F1 peuvent y figurer en mention « déclaratif » ; les faits F0 jamais. |
| **RG-06** | **Fiabilité et fraîcheur** : tout indicateur affiche la répartition de fiabilité de ses faits, sa fraîcheur et sa complétude (part des objets couverts). |
| **RG-22** | **Journalisation** : l'usage de l'IA (analyses, réponses de l'assistant, documents générés) est journalisé (qui, quand, périmètre, version de l'outil) ; le contenu des questions est protégé et n'est accessible qu'à l'utilisateur, sauf procédure d'audit habilitée tracée. |
| **RG-23** | **Signalement discret** : un utilisateur peut transmettre un signalement à un rôle précis (RSSI, référent) sans exposer son identité aux autres lecteurs ; l'identité reste connue du rôle destinataire et des auditeurs habilités. |
| **RG-24** | **Alerte protégée** : Odin ne se substitue pas à la procédure légale de recueil des alertes. Lorsqu'un contenu relève manifestement de ce cadre (faits graves, infraction, mise en cause de personnes), Odin affiche le renvoi vers la procédure de l'organisme, n'analyse pas le contenu et ne le diffuse pas. |
| **RG-31** | **Contributeurs externes** : visibilité limitée aux périmètres ouverts ; droits expirant avec le contrat ; aucune visibilité sur les contenus N3/N4 hors habilitation explicite. |
| **RG-32** | **Informations classifiées de défense** : non admises dans Odin (hypothèse à confirmer, Q-04) ; avertissement permanent ; tout contenu soupçonné est écarté et signalé à l'administrateur de sécurité. |

### 1.2 Faits, santé, qualité

| ID | Règle |
|---|---|
| **RG-07** | Un fait est toujours **sourcé** (rapport + extrait, ou saisie manuelle identifiée). Un fait plus récent d'une même nature sur le même objet **remplace** l'ancien (qui reste dans l'historique). Des faits contradictoires **ne sont jamais arbitrés automatiquement** : un signal est créé. |
| **RG-08** | **Santé calculée** : la santé (conforme / sous vigilance / critique) d'une application ou initiative résulte de **règles paramétrables** (ex. jalon dépassé de plus de N jours, budget consommé hors tendance, risque majeur ouvert, absence de rapport depuis N jours, fin de support dans moins de N mois). La **justification** (règles et faits) est affichable. Une santé **déclarée** peut coexister ; tout écart est signalé. Toute modification manuelle d'une santé calculée exige un motif et est tracée. |
| **RG-09** | **Criticité** d'une application : déduite des services rendus qu'elle sert et de leur criticité de continuité ; confirmable ou ajustable par le responsable avec motif. |
| **RG-10** | **Objet orphelin ou périmé** : application sans responsable, sans équipe, ou sans fait validé depuis N jours (seuil par criticité). Signalé au référent et dans la qualité du référentiel (indicateur de dispositif, pas de personne). |
| **RG-11** | **Péremption** : chaque type de rapport a une durée de validité ; à expiration, ses faits ne sont plus utilisés pour les indicateurs « à jour » sans nouvelle confirmation. |
| **RG-33** | **Rattachement** : un fait est rattaché à un objet existant ; en cas d'ambiguïté il reste en file de curation et n'alimente aucun indicateur. |
| **RG-34** | **Relances** : maximum d'une relance par semaine et par personne (hors alerte critique) ; formulation factuelle ; escalade de la **fonction** (rôle), pas de la personne, tracée. |

### 1.3 Stratégie, portefeuille, roadmap

| ID | Règle |
|---|---|
| **RG-12** | Toute initiative sert au moins un objectif ou un service rendu ; à défaut elle est marquée **« hors stratégie »** et visible comme telle. |
| **RG-13** | Une obligation réglementaire ou doctrinale applicable avec échéance ferme rend l'initiative **« non arbitrable »** (pas de report sans décision explicite et motivée) ; elle est traitée en contrainte dans les scénarios. |
| **RG-14** | Les **avis obligatoires** (instance interministérielle, sécurité, protection des données…) et leurs **seuils** sont des **paramètres datés** ; leur valeur initiale (par exemple le seuil financier d'avis de l'instance interministérielle) est à **vérifier** avant mise en service : les sources de la recherche divergent (9 ou 15 M€). |
| **RG-15** | La **priorisation** est explicable : chaque score montre la contribution de chaque critère ; **grille et pondérations sont versionnées** et rattachées aux décisions qui les ont utilisées. |
| **RG-27** | Une **roadmap publiée** est une version immuable liée à une décision ; toute évolution crée une nouvelle version ; la comparaison entre versions est disponible. |
| **RG-35** | Une **dette acceptée** a un motif, une durée et une date de revue ; sans revue elle redevient « à traiter ». |
| **RG-36** | Une **initiative** ne peut être clôturée sans bilan (réalisé vs prévu, bénéfices) ou décision de dispense motivée. |

### 1.4 Ressources et finances

| ID | Règle |
|---|---|
| **RG-16** | **Unités RH** : capacité et charge en **ETP** ; suivi du plafond d'emplois en **ETPT** (moyenne annualisée) ; la **règle de conversion** ETP ↔ ETPT (quotité, présence sur l'année) est paramétrée, visible et expliquée. Les plafonds et schémas d'emplois sont saisis par la fonction habilitée. |
| **RG-17** | **Imputation financière** : les règles d'allocation des coûts partagés (hébergement, licences communes) sont déclarées par le contrôle de gestion, visibles et versionnées ; une dépense non imputée est comptée et signalée. |
| **RG-18** | **Run / build** : classification selon une règle paramétrable (maintenance et exploitation = run ; évolution et projets = build) ; les dépenses ambiguës sont arbitrées par le contrôle de gestion. |
| **RG-19** | **Échéances de contrats** : alertes graduées paramétrables (par défaut 180/90/30 jours avant le préavis) ; un préavis dépassé crée un signal critique avec les options restantes. |
| **RG-37** | Aucune **valorisation financière individuelle** de personnes : les coûts de ressources sont présentés au niveau agrégé (équipe, profil, service). |

### 1.5 Décisions, conservation, droits

| ID | Règle |
|---|---|
| **RG-25** | **Acceptation d'un risque** : formelle, par l'autorité compétente désignée, datée et attribuée ; durée limitée avec revue. |
| **RG-26** | **Décision** : tout enregistrement comporte options, critères, hypothèses, décideur, motifs ; une décision **contraire à la recommandation** exige un motif ; une **date de bilan** est obligatoire ; la photo des faits au jour de la décision est conservée. |
| **RG-20** | **Conservation** : durées par type d'objet fixées par la politique de l'organisme (rapports, faits, journaux, décisions, restitutions), conformément à ses obligations d'archivage ; à échéance, archivage ou effacement tracé. |
| **RG-21** | **Retrait, rectification, effacement** : l'auteur peut retirer un rapport ou demander la rectification d'un fait le concernant ; la demande suit un circuit (responsable de l'objet, DPO) avec délai de réponse ; une obligation de conservation ou une décision tracée qui s'appuie sur le contenu limite l'effacement (le motif est exposé). |
| **RG-28** | **Textes et règles externes** : toute règle issue d'un texte ou d'une doctrine est une **donnée datée** (source, statut juridique, date de vérification). Un statut incertain est affiché comme tel ; Odin ne le présente jamais comme acquis. |
| **RG-29** | **Notifications neutres** : aucune notification ne révèle de contenu N3/N4 à un non-habilité. |
| **RG-30** | **Langage non accusatoire** : relances, signaux et indicateurs de couverture parlent de dispositif, d'objet et de rôle, jamais de défaillance d'une personne. |

## 2. Exigences transverses (non fonctionnelles, exprimées en besoin métier)

Les valeurs chiffrées sont des **objectifs de départ** à confirmer ; leur réalisation est étudiée en phase technique.

### 2.1 Confidentialité et sécurité (besoin)

- **ET-01.** Les contenus de l'organisme sont traités dans des conditions de **confidentialité, de souveraineté et d'hébergement** conformes aux exigences de l'État applicables à leur sensibilité (doctrine d'hébergement, référentiels de sécurité). Le niveau exigé (par exemple qualification de l'hébergement, exploitation interne) est à instruire en phase technique ; **question ouverte Q-05**.
- **ET-02.** L'**homologation de sécurité** de la plateforme avant ouverture, selon la procédure de l'organisme, est une condition de mise en service.
- **ET-03.** **Cloisonnement strict** des contenus N4 et des périmètres ; aucun accès par défaut des administrateurs.
- **ET-04.** **Traçabilité** de tous les accès et actions significatives (EX-AUD-01).
- **ET-05.** L'**IA** respecte les mêmes règles de confidentialité que l'utilisateur (IA-10, IA-11, IA-18).

### 2.2 Protection des données personnelles et droit des agents

- **ET-06.** Une **analyse d'impact relative à la protection des données (AIPD)** est réalisée avant la mise en service ; le **DPO** est associé dès la conception.
- **ET-07.** Les **instances de dialogue social** compétentes (comité social d'administration ou équivalent) sont **informées et consultées** selon les règles applicables avant le déploiement ; une note d'information aux agents précise les finalités et les garanties (pas d'évaluation individuelle, agrégation, transparence sur l'IA).
- **ET-08.** **Finalité limitée** : les données de contribution ne servent à aucun usage d'évaluation, de contrôle d'activité ou de décision individuelle (RG-01).
- **ET-09.** **Qualification juridique de l'IA** : une revue (juridique, DPO) vérifie que l'usage d'IA d'Odin ne relève pas d'une catégorie « à haut risque » (gestion des travailleurs), au regard du cadre européen applicable et de son calendrier (calendrier non tranché dans la recherche). **Hypothèse de conception** : l'évitement structurel de tout usage individuel (RG-01, RG-02, IA-08, IA-09) est la mesure principale ; la qualification n'est pas laissée à la seule interprétation.
- **ET-10.** **Droits des agents** : accès, rectification, retrait, information sur l'usage de leurs contributions (P-27).

### 2.3 Accessibilité, ergonomie, langue

- **ET-11.** Conformité au **référentiel d'accessibilité** applicable aux services numériques de l'État (visée AA), pour l'application et les documents produits. 
- **ET-12.** **Charte graphique** et **identité** de l'organisme ou de l'État (à confirmer, Q-12).
- **ET-13.** Interface en **français** ; vocabulaire paramétrable ; aide contextuelle.

### 2.4 Disponibilité, performance perçue, continuité

- **ET-14.** **Disponibilité** compatible avec un usage de pilotage (pas d'exigence de haute disponibilité 24 h/24 ; plages d'indisponibilité planifiées hors périodes de pic de comité) : objectif à fixer.
- **ET-15.** **Performance perçue** : confirmation de dépôt immédiate ; analyse d'un rapport courant en quelques minutes ; affichage des tableaux de bord en quelques secondes ; production d'un rapport de direction en quelques minutes.
- **ET-16.** **Continuité** : en cas d'indisponibilité de l'IA, les fonctions manuelles restent ouvertes ; les brouillons ne sont pas perdus.
- **ET-17.** **Reprise après incident** : objectifs de reprise et de perte maximale de données à définir (par exemple perte maximale d'une journée de contributions).

### 2.5 Historisation, reproductibilité, réversibilité

- **ET-18.** **Historisation** complète des faits, validations, décisions, versions de roadmaps et de restitutions ; reconstitution de l'état à une date donnée.
- **ET-19.** **Reproductibilité** : une restitution ou décision peut être régénérée avec les données du jour de sa production.
- **ET-20.** **Réversibilité** : l'organisme peut **exporter l'intégralité** de ses contenus (rapports, faits, objets, décisions, journaux) dans des formats ouverts et documentés.
- **ET-21.** **Formats ouverts** privilégiés pour les entrées et sorties bureautiques.
- **ET-22.** **Licence et diffusion** : le mode de diffusion du produit (logiciel libre, inscription à un socle interministériel) est une décision stratégique ouverte (Q-13).

### 2.6 Alimentations et interfaces (besoins, sans choix technique)

- **ET-23.** **Alimentation initiale** du référentiel (applications, organisation) par import de fichiers ou de sources de l'organisme.
- **ET-24.** **Alimentations récurrentes** souhaitables (par ordre de valeur) : sources financières de l'État (dépenses imputées), sources RH agrégées (effectifs par profil, plafonds), outils de suivi de projets et de développement (jalons, volumes), outils de gestion de services (incidents), outils de gestion de risques et de cartographie, bases publiques (calendrier de fin de support des technologies, bases ouvertes de l'État comme le panorama des grands projets).
- **ET-25.** Chaque alimentation déclare sa **fiabilité** (F3 si objective), sa **fréquence** et son **périmètre**.
- **ET-26.** **Ouverture** : Odin expose aux autres outils de l'organisme les objets et indicateurs, selon les droits.

### 2.7 Exploitation et soutien (besoin)

- **ET-27.** **Soutien aux utilisateurs** : canal identifié, délai de réponse cible, base de connaissances.
- **ET-28.** **Formation** : modules courts par rôle (contributeur, responsable, décideur, administrateur).
- **ET-29.** **Évolution des règles** sans développement (paramétrage), avec aperçu d'impact.
- **ET-30.** **Mesure d'adoption et de qualité** (indicateurs du fichier 01 §5) accessible à l'équipe de pilotage du produit.
