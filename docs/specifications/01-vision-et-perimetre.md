# 01. Vision, objectifs et périmètre

## 1. Problème à résoudre

Dans un organisme de l'État, les informations qui permettent de décider sur le système d'information (SI) sont **dispersées et déclaratives** : rapports d'avancement dans des documents bureautiques, comptes rendus de comités, audits de sécurité, notes d'architecture, tableaux budgétaires, plans de charge, courriels. La direction obtient une image **tardive, embellie et non comparable** (« tout est vert » jusqu'à ce que ce soit rouge). Les chiffres (dépense numérique, dette, ressources) sont difficiles à **consolider**, ce qui est aussi un reproche récurrent des corps de contrôle. Les outils existants (architecture d'entreprise, portefeuille de projets, gestion de risques) exigent une saisie lourde, sont peu adoptés hors des architectes et aident peu à **arbitrer**.

## 2. Vision

> Que chaque personne qui sait quelque chose d'utile sur le SI puisse le dire **simplement**, sous la forme qui lui est naturelle (un rapport), et que la direction dispose, **sans ressaisie**, d'une vue **fiable, traçable et décisionnelle** de la dette, des roadmaps, des objectifs, de la sécurité, des ressources et des finances, avec la possibilité de **produire ses rapports et présentations** en quelques minutes.

## 3. Objectifs du produit

| # | Objectif | Pourquoi |
|---|---|---|
| O1 | **Faciliter la contribution de tous** : déposer un rapport en moins de 2 minutes, sans changer ses habitudes de rédaction. | La qualité des données est le premier facteur d'échec des outils comparables ; l'adoption est la condition de tout le reste. |
| O2 | **Comprendre automatiquement** les rapports : en extraire des faits (avancement, risques, dépendances, besoins en ressources, budgets, dette…), les relier au bon objet du SI, et faire **valider** ces faits par un humain. | Supprimer la ressaisie sans sacrifier la fiabilité. |
| O3 | **Offrir une vue décisionnelle unifiée** : dette, portefeuille, roadmaps, objectifs, ressources, finances, sécurité, conformité, fournisseurs, croisés. | Aucune solution existante ne croise dette, capacité (ETP), risque et finances pour arbitrer. |
| O4 | **Aider à arbitrer** : scénarios, critères multiples, coût du retard et de l'inaction, note de décision prête à présenter. | Passer de la restitution à l'aide à la décision. |
| O5 | **Produire** rapports de direction, synthèses, notes et présentations, **avec la source de chaque affirmation**. | Gain de temps ; confiance ; auditabilité. |
| O6 | **Tracer** les décisions, hypothèses, bénéfices attendus et recommandations de contrôle, et leur suivi. | Exigence d'audit et de contrôle propre au secteur public. |
| O7 | **Respecter les agents** : évaluer des applications et des équipes, jamais des personnes ; confidentialité et transparence sur l'usage de l'IA. | Décision D1 ; protection des agents ; acceptabilité sociale. |
| O8 | **Intégrer le cadre de l'État** : budget par programme, ETPT et plafond d'emplois, avis obligatoires, doctrines, calendrier réglementaire. | Contexte cible (D4). |

## 3 bis. Principes directeurs (arbitrent les choix de conception)

1. **Le rapport est l'unité de contribution.** On ne demande pas aux gens de remplir des fiches d'un référentiel ; on les laisse écrire ou déposer, et Odin structure.
2. **L'IA propose, l'humain dispose.** Aucun fait extrait par l'IA n'alimente un indicateur de direction sans avoir été confirmé par un humain habilité (voir RG-05, IA-03).
3. **Toute information est traçable** : qui l'a dite, quand, dans quel document, avec quel niveau de confiance, et qui l'a validée.
4. **Fiabilité visible** : chaque chiffre affiche s'il est déclaré, confirmé, validé ou vérifié, et sa fraîcheur.
5. **On évalue des objets, pas des personnes** (D1) : applications, projets, équipes, services. Aucune vue ne permet de classer ou de juger un individu ; agrégation minimale d'effectif.
6. **Utile dès le premier rapport** : l'outil donne de la valeur au contributeur (retour, synthèse, rappel) et pas seulement à la direction ; sinon l'adoption s'effondre.
7. **Simplicité par rôle** : le contributeur voit une interface minimale ; la complexité est réservée à ceux qui en ont besoin.
8. **Les règles externes sont des données** : textes, seuils et calendriers sont paramétrables, datés et attribuables (registre réglementaire) ; Odin ne présente jamais une règle contestée comme un fait.
9. **Sobriété** : peu d'indicateurs, chacun lié à une décision (un tableau de bord qui ne déclenche aucune décision est supprimé).
10. **Fonctionne sans l'IA** : tout parcours essentiel reste possible manuellement si l'IA est indisponible ou refusée.
11. **Souveraineté et confidentialité d'abord** : l'IA n'accède qu'à ce que l'utilisateur est autorisé à voir ; les contenus sensibles sont cloisonnés.

## 4. Périmètre

### 4.1 Inclus

| Domaine | Contenu |
|---|---|
| Contribution collective | Dépôt, rédaction guidée, bibliothèque, cycle de vie de rapports, demandes de précision |
| Compréhension IA | Extraction de faits, rattachement, détection d'écarts et de signaux faibles, résumé, questions-réponses avec sources |
| Patrimoine du SI | Applications, technologies, données, flux, services rendus, processus, organisation, équipes, profils |
| Stratégie | Objectifs, cascade objectif → initiative → indicateur, valeur attendue |
| Transformation | Demandes, qualification, portefeuille, priorisation, initiatives, roadmaps, scénarios, bénéfices |
| Dette et obsolescence | Éléments de dette, cycle de vie des technologies, priorisation du remboursement |
| Ressources | Équipes, profils RH, compétences, capacité et plan de charge en ETP / ETPT, vacances, dépendance aux prestataires |
| Finances | Budgets par programme et titre, dépenses, run / build, coûts par application ou service |
| Fournisseurs | Marchés, contrats, licences, échéances, dépendance |
| Sécurité et risques | Posture, risques, mesures, homologations, audits, exceptions, continuité |
| Conformité | Registre réglementaire daté, obligations, échéances, applicabilité |
| Décision | Comités, notes de décision, registre des décisions, recommandations de contrôle |
| Restitution | Tableaux de bord, rapports générés, présentations, exports |
| Administration | Référentiels, droits, gabarits, seuils, paramétrage |

### 4.2 Exclu (initialement)

| Exclusion | Raison |
|---|---|
| **Évaluation individuelle** des agents (performance, notation, classement, suivi d'activité nominatif) | Décision D1 ; protection des agents ; cadre IA européen |
| **Multi-organismes, mutualisation, refacturation entre entités** | Décision D3 |
| **Collectivités, hôpitaux, santé** (CaRE, HDS) | Décision D4 |
| **Opérations de sécurité** (détection, journaux, réponse à incident en temps réel) | Odin pilote, il n'opère pas ; il s'alimente des constats |
| **Gestion des services informatiques** (tickets, support, CMDB opérationnelle) | Odin consomme des signaux ; il ne remplace pas ces outils |
| **Canal d'alerte protégée** (lanceurs d'alerte) | Procédure légale distincte ; Odin y **renvoie** (voir RG-24) |
| **Informations classifiées de défense** | Hors cible ; à confirmer (question ouverte Q-04) |
| **Gestion RH nominative** (évaluations, rémunérations individuelles, dossiers) | Hors périmètre ; Odin raisonne par profil, rôle et équipe |
| **Comptabilité et exécution budgétaire** | Odin consolide et pilote ; il ne remplace pas les outils financiers de l'État |

### 4.3 Hypothèses de travail

- H1. L'organisme dispose d'une direction du numérique (DNUM/DSI) et d'au moins un responsable sécurité, un contrôle de gestion et une fonction RH.
- H2. Les utilisateurs s'authentifient avec les moyens d'identité de leur organisme ; Odin ne gère pas d'annuaire propre autre que les rôles fonctionnels.
- H3. Les rapports existent déjà sous forme de documents (texte, tableurs, présentations, comptes rendus) ; Odin ne demande pas de les réécrire.
- H4. Le périmètre « opérateurs de l'État » est inclus par hypothèse (voir question Q-01).
- H5. Les contributeurs externes (prestataires) peuvent être autorisés avec un périmètre restreint.

## 5. Mesures de succès du produit

| Indicateur | Cible indicative (à calibrer) | Lecture |
|---|---|---|
| Part des agents du SI ayant contribué au moins une fois dans le trimestre | ≥ 60 % à 12 mois | Adoption |
| Délai moyen entre dépôt d'un rapport et faits validés | ≤ 2 jours ouvrés | Fluidité de la validation |
| Taux de faits extraits acceptés sans correction | ≥ 80 % (suivi, non garanti) | Qualité de l'IA |
| Part des indicateurs de direction fondés sur des faits confirmés ou validés | ≥ 90 % | Confiance |
| Fraîcheur : part des applications critiques avec un rapport de moins de 90 jours | ≥ 85 % | Couverture |
| Temps de préparation d'un comité (avant / après) | divisé par 2 | Valeur pour la direction |
| Part des décisions du registre avec bilan a posteriori | ≥ 70 % | Boucle de décision |
| Incidents de confidentialité (contenu visible hors périmètre) | 0 | Exigence absolue |
| Plaintes ou signalements d'usage individuel des données | 0 | Respect de D1 |

Ces cibles sont des **hypothèses de départ** ; elles doivent être validées avec le commanditaire avant d'être contractuelles.
