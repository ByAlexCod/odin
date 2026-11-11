# 10. Lots, priorités, critères de recette et questions ouvertes

## 1. Principe de découpage

Odin est découpé en **lots livrables** qui apportent chacun de la valeur **utilisable**. Le **lot 1** valide l'hypothèse centrale (« tous contribuent, l'IA comprend, la direction voit ») ; les suivants étendent la décision.

## 2. Lots

| Lot | Nom | Modules (exigences marquées L1 etc. au fichier 05) | Valeur livrée |
|---|---|---|---|
| **L1** | **Contribution et compréhension** | ACC, RAP, IAF, REF (applications, équipes, services rendus), NOT, ASS (sur rapports), QUA, ADM (base), AUD (journal), TDB (vue stratégique initiale, santé applicative, fraîcheur), RST (synthèses, résumé hebdomadaire) | Tous les agents déposent ; l'IA propose ; les responsables valident ; la direction voit une première vue fiable et peut interroger Odin |
| **L2** | **Transformation** | OBJ, POR (demandes, portefeuille, santé), ROA (roadmaps, versions), DET (dette, obsolescence), DEC (instances, décisions, bilans), TDB (alertes, historique) | Objectifs, portefeuille, roadmaps et dette reliés aux rapports ; décisions tracées |
| **L3** | **Ressources et finances** | RSR, FIN, FOU, ROA (cohérence, scénarios), POR (contraintes), IAF (rapprochement objectif) | Capacité par profil (ETP/ETPT), budget, coûts, contrats ; scénarios sous contraintes |
| **L4** | **Sécurité et conformité** | SEC, REG, DET (lien sécurité), FOU (souveraineté), ADM (registre) | Risques, homologations, obligations et échéances intégrés aux arbitrages |
| **L5** | **Décision avancée et restitution** | DEC (notes, comptes rendus), RST (rapports de direction, présentations, exports), ROA (sensibilité, vues de diffusion), FIN (dossier d'arbitrage), POR (capitalisation) | Production assistée de supports de décision et de présentations |
| **L6** | **Audit, comparaison, ouverture** | DEC (recommandations de contrôle), AUD (exports), TDB (benchmark), DET (outils de mesure), FIN (évaluation socio-économique), SEC (quantification), REG (accessibilité/RSE), RSR (formation) | Contrôle externe, comparaison, rapprochements avancés |

### 2.1 Cheminement conseillé

L1 est **un prérequis** de tous les autres. L2 et L3 peuvent être menés **en parallèle partiel** (L3 dépend de la qualité des faits de ressources et de finances). L4 peut démarrer dès L1 pour le volet « conformité » (registre) si le besoin d'échéances est urgent. L5 s'appuie sur la maturité des faits des lots 2 à 4.

### 2.2 Contenu minimal du lot 1 (pour être utile)

Parcours P-01 à P-08, P-22, P-23 (vue réduite), P-25, P-26 (base), P-27 ; écrans E-00 à E-09, E-24, E-25 (réduite), E-27, E-28 (base) ; gabarits G-01, G-02, G-04, G-05, G-09, G-18 ; indicateurs I-10, I-11, I-23, I-25, I-90 à I-95.

## 3. Priorités par axe de la liste initiale de l'utilisateur

| Axe cité | Où il se trouve | Lot |
|---|---|---|
| Dette | EX-DET | L2 (lien sécurité L4) |
| Roadmaps | EX-ROA | L2 (scénarios L3) |
| Objectifs | EX-OBJ | L2 |
| Sécurité | EX-SEC | L4 |
| Reporting | EX-TDB, EX-RST, EX-QUA | L1 (base), L5 |
| Ressources disponibles (ETP) | EX-RSR | L3 |
| Métiers (= profils RH) | EX-RSR-01 et suivants, référentiel de profils (fichier 09 §5) | L3 |
| Rapports | EX-RAP, EX-IAF | L1 |
| Présentations | EX-RST-04 | L5 (synthèses dès L1) |
| IA qui comprend et produit | EX-IAF, EX-RST, EX-ASS, fichier 06 | L1 (comprendre, répondre), L5 (produire) |
| Tout le monde y entre et partage | EX-ACC, EX-RAP, P-01 à P-07 | L1 |

## 4. Critères de recette (par lot, niveau métier)

### L1

| # | Critère |
|---|---|
| C-1.1 | Un agent sans formation dépose un rapport et atteint « Partagé » en moins de 2 minutes (P-02). |
| C-1.2 | Sur un jeu de rapports de référence réalistes, au moins 80 % des faits proposés sont confirmés sans correction pour les natures *avancement, jalon, risque* (seuil à confirmer après essais). |
| C-1.3 | Aucun fait F0 ni évaluatif nominatif n'apparaît dans un indicateur de direction ; un test sur des rapports contenant des jugements nominatifs ne produit aucun fait évaluatif (RG-01, IA-08). |
| C-1.4 | Un utilisateur sans droit ne peut ni voir, ni déduire, ni se faire résumer un contenu N4 (y compris via l'assistant et les notifications) (RG-04, RG-29). |
| C-1.5 | Toute valeur d'indicateur est cliquable jusqu'à ses faits sources, avec fiabilité et fraîcheur. |
| C-1.6 | Une contradiction entre deux rapports génère un signal et une demande de précision traités de bout en bout (P-06). |
| C-1.7 | Les métriques d'équipe de moins de N personnes ne s'affichent pas (RG-02) ; aucune vue nominative n'existe. |
| C-1.8 | Avec l'IA indisponible, le dépôt, la saisie de faits et la validation fonctionnent. |
| C-1.9 | Un document contenant des consignes adressées à l'IA est traité comme du contenu et signalé (IA-12). |
| C-1.10 | La vue stratégique est utilisable par un décideur sans aide, selon un test utilisateur (tâches P-23). |
| C-1.11 | Le journal permet de reconstituer qui a déposé, validé, consulté du N4, utilisé l'IA. |
| C-1.12 | Accessibilité vérifiée sur les parcours P-01, P-02, P-05, P-22, P-23. |

### L2 à L6 (critères principaux)

| Lot | Critère principal |
|---|---|
| L2 | Une décision d'arbitrage est enregistrée, ses suites sont créées, son bilan est rappelé et comparable (P-12, P-20). La santé déclarée vs calculée détecte les « verts de façade ». |
| L3 | Un scénario de réduction de capacité d'un profil affiche les initiatives retardées et le coût du report ; le plafond d'emplois (ETPT) est suivi avec règle de conversion explicite ; la dépense numérique est consolidée de façon reproductible. |
| L4 | Un texte dont le statut change met à jour obligations, alertes et roadmap proposée ; une homologation proche de l'échéance alerte les bons rôles. |
| L5 | Une présentation générée est entièrement traçable (chaque chiffre) et son export vers une audience non habilitée est bloqué. |
| L6 | Un dossier d'audit (preuves, recommandations, journal) est produit sans intervention technique. |

## 5. Dépendances et risques de projet (métier)

| Risque | Conséquence | Atténuation prévue dans le dossier |
|---|---|---|
| Faible adoption par les contributeurs | Indicateurs vides | Valeur immédiate pour le contributeur (P-07), confirmation en lot, rappels sobres, conduite du changement |
| Faits mal extraits ou fiabilité surévaluée | Décisions erronées | Niveaux de fiabilité, validation humaine, contradictions, mesure de qualité IA |
| Perception de surveillance des agents | Rejet social, risque juridique | RG-01, RG-02, transparence, consultation des instances, AIPD |
| Fuite de contenus sensibles via l'IA | Incident grave | RG-04, IA-10/11/18, journalisation, cloisonnement |
| Données réglementaires fausses ou périmées | Mauvaise conformité | RG-28, date de vérification, « à revérifier » |
| Surcharge de validation (goulot) | Retard des indicateurs | Curateurs, validation en lot, seuils de confiance |
| Périmètre trop large en lot 1 | Retard de livraison | Contenu minimal du lot 1 (§2.2) |
| Dépendance à un fournisseur d'IA unique | Perte de souveraineté | Contrainte à traiter en phase technique (ET-01, IA-18), réversibilité (ET-20) |

## 6. Questions ouvertes

Chaque question indique **ce qu'elle bloque** et une **proposition par défaut** (hypothèse de travail) pour avancer.

| # | Question | Bloque | Proposition par défaut |
|---|---|---|---|
| **Q-01** | Les **opérateurs de l'État** (établissements publics, agences) sont-ils dans le périmètre ? Et les **organismes de sécurité sociale** ? | Cadre budgétaire (programmes vs budgets propres), référentiels RH, avis | Opérateurs inclus ; sécurité sociale exclue |
| **Q-02** | **Qui valide** les faits en second niveau : curateur dédié par domaine, ou responsable de l'objet seulement ? | Charge de validation, délais | Responsable de l'objet + curateur de domaine pour les ambiguïtés |
| **Q-03** | **Jusqu'où** accepter les contenus sensibles (sécurité, RH, juridique) dans Odin ? | Classification, cloisonnement | Sécurité acceptée en N4 ; RH nominatif exclu ; juridique en N3 |
| **Q-04** | Odin peut-il recevoir des **informations classifiées de défense** ou de **diffusion restreinte** ? | Hébergement, conception | Exclues (RG-32) ; diffusion restreinte à confirmer selon l'organisme |
| **Q-05** | Quel **niveau d'hébergement et de souveraineté** est exigé pour les contenus et l'IA (exploitation interne, hébergement qualifié, autre) ? | Phase technique, faisabilité de l'IA | À instruire avec le RSSI ; niveau le plus protecteur par défaut |
| **Q-06** | **Qui est l'autorité** d'acceptation des risques, de validation des restitutions officielles, des décisions d'avis ? | Workflows de validation | Rôles paramétrables ; défaut : DNUM pour risques et décisions |
| **Q-07** | **Quelle valeur** pour le seuil d'avis de l'instance interministérielle et les autres seuils (9/15 M€, 20 M€) ? | Avis obligatoires | Paramètre ; valeur à vérifier sur le texte consolidé |
| **Q-08** | **Calendrier et état de la transposition de la directive cyber (NIS 2)** et du **règlement sur l'IA** pour une organisation de l'État | Registre réglementaire, priorités L4 | Portés comme données datées ; revérification avant mise en service |
| **Q-09** | **Référentiel de profils** : référentiel de l'État, nomenclature de la profession, ou hybride ? | Capacité, compétences | Référentiel de l'État complété si besoin |
| **Q-10** | **Quelles sources de données** existent et sont accessibles (finances, RH agrégé, suivi de projets, outils de gestion de services, cartographie, risques) ? | Alimentations, fiabilité F3 | Import de fichiers au lot 1 ; alimentations ensuite |
| **Q-11** | Le **dialogue social** : calendrier de consultation, AIPD, qui porte la communication aux agents ? | Date de mise en service | À lancer dès le lot 1 |
| **Q-12** | **Charte graphique** : charte de l'État, de l'organisme, ou libre ? | UX | Charte de l'organisme |
| **Q-13** | **Mode de diffusion** (logiciel libre, inscription à un socle interministériel, usage interne) | Gouvernance produit | À décider avec le commanditaire |
| **Q-14** | **Niveau de précision attendu** en ressources : par rôle/profil (proposé) ou nominatif ? (déjà tranché sur le principe : pas de nominatif) | RSR | Rôle/profil/équipe agrégé |
| **Q-15** | **Part des dépenses numériques** à consolider : seulement la direction du numérique, ou tout l'organisme (réponse aux contrôles) ? | FIN | Tout l'organisme, avec périmètre paramétrable |
| **Q-16** | **Cible d'effectif** et d'utilisateurs (centaines, milliers) et profil de l'organisme (ministère, direction) ? | Dimensionnement, adoption | À fournir par le commanditaire |
| **Q-17** | **Langue de travail** : français seul, ou documents en anglais fréquents ? | IAF | Français ; documents en anglais tolérés |
| **Q-18** | **Canal d'alerte protégée** : l'organisme dispose-t-il d'un dispositif ? Odin y renvoie-t-il seulement ? | RG-24 | Renvoi uniquement |
| **Q-19** | **Politique de conservation** : durées par type de contenu ? | RG-20 | À fournir par l'organisme/archives |
| **Q-20** | **Qui pilote le produit** côté organisme (sponsor, product owner, administrateurs, curateurs) ? | Gouvernance, lot 1 | À désigner |
| **Q-21** | **Dépôts par courriel ou transfert** : acceptés comme mode de dépôt ? | RAP | Oui, avec contrôle de l'expéditeur |
| **Q-22** | **Évaluation socio-économique** et autres méthodes publiques : doivent-elles être outillées dès L3 ? | FIN | Reportée à L6 |

## 7. Prochaines étapes suggérées

1. **Relecture** du dossier par le commanditaire ; arbitrage des questions Q-01 à Q-08 (celles qui bloquent le lot 1).
2. **Entretiens** avec 6 à 10 personnes représentatives (contributeur, responsable d'application, chef de projet, RSSI, contrôle de gestion, RH, DNUM, direction) pour valider personas, parcours et gabarits.
3. **Collecte de rapports réels** (anonymisés) pour constituer le jeu de référence de qualité de l'IA et valider le catalogue de faits.
4. **Vérification des textes** du registre réglementaire (fichier 09 §4) sur sources officielles.
5. **Prototype de parcours** (maquettes cliquables) de P-02, P-05, P-22, P-23 et tests avec de vrais utilisateurs.
6. **Consultation du DPO et du juridique** (AIPD, qualification IA, dialogue social).
7. **Spécification détaillée du lot 1** (cas de test, jeux de données) puis ouverture de la **phase technique** (architecture, hébergement, choix d'IA).
