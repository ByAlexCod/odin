# Gouvernance et pilotage stratégique du SI d'un organisme public : cadres, objectifs, alignement stratégique (axes métier Odin)

Date de la recherche : 11/11/2026. Limites : 16 appels outils, certains hôtes bloqués (catalogue.numerique.gouv.fr), Légifrance non exploitable via l'outil, PDF MAGNum illisible. Les éléments marqués « [connaissance générale] » ne sont pas sourcés dans cette session et doivent être vérifiés avant publication.

## 1. Quels domaines définissent COBIT 2019, ISO/IEC 38500, ITIL 4, IT4IT, TOGAF, Cigref ?

### Takeaway
COBIT 2019 = 40 objectifs en 5 domaines (1 gouvernance EDM + 4 de gestion APO/BAI/DSS/MEA). ISO/IEC 38500:2024 = modèle Évaluer-Diriger-Surveiller, aligné sur ISO 37000. IT4IT 3.0 = 7 value streams. Le Cigref fournit côté français le modèle de coûts/benchmark, le pilotage économique et écologique, la nomenclature des profils métiers et le modèle de maturité MAGNum 2026.

### Cited Findings
- COBIT 2019 : 40 objectifs de gouvernance et de gestion, domaine EDM (gouvernance, conseil : évaluer, orienter, surveiller) + domaines de gestion APO, BAI, DSS, MEA. Répartition la plus citée EDM 5, APO 14, BAI 11, DSS 6, MEA 4 ; un site isolé donne EDM 6 / MEA 3, donc à vérifier auprès d'ISACA — [cybersigmacs](https://cybersigmacs.com/knowledge-center/cobit/); divergence : [ayinedjimi](https://ayinedjimi-consultants.fr/glossaire/cobit-2019-gouvernance-it)
- ISO/IEC 38500:2024 : modèle à trois tâches (évaluer, diriger, surveiller), six principes, édition 2024 alignée sur les principes de l'ISO 37000 ; norme payante, non disponible en français — [ISO](https://www.iso.org/standard/81684.html); [ISO JTC1/SC40](https://committee.iso.org/sites/jtc1sc40/home/projects/wg-1/published-wg1/content-left-area/isoiec-sc-40-wg-1-develops-the-s/white-paper-on-the-differences-b.html)
- IT4IT 3.0 (Open Group) : sept value streams — Evaluate, Explore, Integrate, Deploy, Release, Consume, Operate ; centré sur la gestion de produits numériques, remplace la chaîne de valeur par un réseau de valeur ; complémentaire d'ITIL — [Open Group IT4IT 3.0](https://pubs.opengroup.org/it4it/3.0/standard/VSs_IT4IT-Value-Streams.html); [techtarget](https://www.techtarget.com/news/IT4IT/871906/)
- Cigref : guide « Modèle d'analyse et de benchmarking des coûts informatiques » (codification bilingue FR/EN, édition citée 2014) ; 4e édition du « modèle de pilotage économique et écologique IT » publiée le 26/10/2022 (coûts + émissions) ; nomenclature 2025 des profils métiers (~50 descriptions, 9 familles), qui n'est pas la nomenclature de coûts — [Aubay sources](https://blog.aubay.com/wp-content/uploads/2026/04/Sources-et-Lexique-Article-Controle-de-gestion-IT.pdf); [LMI](https://www.lemondeinformatique.fr/actualites/lireamp-le-chief-digital-officer-disparait-du-referentiel-rh-du-cigref-98307.html)
- Cigref/IFACI/AFAI 2019 : guide de gouvernance du SI par l'entreprise (création de valeur) ; février 2026 : MAGNum 2026 (Cigref, IFACI, ISACA France), modèle d'évaluation de la maturité et d'audit de la gouvernance numérique — [GAGSI 2019](https://docs.ifaci.com/wp-content/uploads/2019/03/GAGSI2019_AFAI_IFACI_CIGREF_versionweb.pdf); [MAGNum 2026](https://docs.ifaci.com/wp-content/uploads/2026/02/MAGNum-2026-Cigref-IFACI-ISACA-France-VDEF.pdf)

### Inferences
- [connaissance générale, à vérifier] COBIT : EDM = assurance de la réalisation des bénéfices, optimisation du risque, optimisation des ressources, engagement des parties prenantes ; APO = stratégie, architecture, portefeuille, budget/coûts, ressources humaines, fournisseurs, risques, sécurité, données, qualité ; BAI = programmes, exigences, changement, mise en service, actifs, configuration ; DSS = exploitation, incidents, continuité, sécurité ; MEA = performance/conformité, contrôle interne, conformité réglementaire, assurance. Les 6 principes ISO 38500 (2015) : responsabilité, stratégie, acquisition, performance, conformité, comportement humain. ITIL 4 : système de valeur du service (principes, gouvernance, chaîne de valeur, pratiques, amélioration continue, 4 dimensions). TOGAF : phase A/vision, extension « Motivation » (drivers, objectifs, cibles, mesures) pertinente pour la cascade stratégique.
- Axes Odin déduits : objectifs de gouvernance (bénéfices/risques/ressources), portefeuille, architecture, budget/coûts (TCO modèle Cigref), fournisseurs, risques, conformité, performance/mesure, maturité de gouvernance (auto-évaluation type MAGNum), empreinte environnementale du SI.

### Gaps
- Liste nominative des 40 objectifs COBIT, intitulés exacts des 6 principes ISO 38500:2024, détail ITIL 4 et TOGAF Motivation non obtenus (sources payantes/non retournées).
- Contenu détaillé du MAGNum 2026 (domaines, niveaux) non lisible.
- Version actuelle de la nomenclature de coûts Cigref non trouvée.

## 2. Cadres publics structurant la stratégie SI (SDSI, DINUM, cloud au centre, feuilles de route, COP, collectivités)

### Takeaway
Spécifique public : décret 2019-1088 (modifié 2023, puis relevé en mars 2026 avec seuil 15 M€), doctrine « cloud au centre » (circulaire 6282-SG, 5/07/2021, màj 2023), feuilles de route ministérielles numériques/cyber 2026, réorganisation de la DINUM annoncée (30/04/2026). Les collectivités relèvent de schémas territoriaux distincts.

### Cited Findings
- Avis DINUM : tout projet de l'État de plus de 9 M€ relevait de l'article 3 du décret 2019-1088 ; avis consultatifs pour les organismes sous tutelle ; décret modifié par le décret 2023-304 du 22/04/2023 — [data.gouv.fr avis DINUM](https://www.data.gouv.fr/fr/datasets/publication-des-avis-dinum-articles-3-et-7/); [demarche DINUM](https://demarche.numerique.gouv.fr/commencer/demande-d-avis-conforme-dinum); [avis 2023](https://numerique.gouv.fr/uploads/2023-CMR-28-MEFSIN-URF_AVIS_DINUM_VF.pdf)
- Révision par décret du 18 mars (2026, selon contexte de l'article) : seuil de l'article 3 relevé de 9 M€ (maintenance 2 ans incluse) à 15 M€ ; contrôle SaaS/suites collaboratives au-delà de 2 M€/an ; étendu aux évolutions fonctionnelles et exigences SREN art. 31 (sécurisation/hébergement) ; pas de droit de veto, mais l'avis conforme est transmis aux contrôleurs budgétaires avant validation d'un marché (courrier mai 2025) ; 6 projets audités en 2025 (au 25/03) contre 19 en 2024. Source unique (presse) : vérifier sur Légifrance — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lireamp-les-contrats-saas-des-ministeres-sous-surveillance-de-la-dinum-99748.html)
- Cloud au centre : circulaire 6282-SG du 05/07/2021, cloud par défaut pour tout nouveau projet numérique de l'État ; données sensibles sur cloud interne de l'État ou cloud commercial qualifié SecNumCloud ; mise à jour 2023 (25 ou 31 mai selon sources) ; consolidée par la loi SREN (mai 2024) ; bilan DINUM janvier 2026 : ~37 % de projets non conformes ; angle mort : les opérateurs de l'État — [circulaire](https://www.transformation.gouv.fr/files/presse/Circulaire-n6282-SG-5072021-doctrineuutilisation-informatique-en-nuage-Etat.pdf); [Cloud Temple](https://www.cloud-temple.com/en/documentary-base/the-new-cloud-doctrine-at-the-centre/); [QE AN](https://www2.assemblee-nationale.fr/questions/detail/17/qe/1692/(vue)/pdf); [Solutions Numériques](https://www.solutions-numeriques.com/?p=246326); [Acteurs publics](https://acteurspublics.fr/articles/les-operateurs-de-letat-angle-mort-de-la-doctrine-cloud-au-centre/)
- Feuille de route stratégique DINUM mars 2023 (4 priorités) ; nouvelle feuille de route 2026 du ministre David Amiel ; ministères tenus de remettre leurs feuilles de route (réduction des dépendances numériques) ; ANSSI : feuille de route sécurité numérique de l'État 2026-2027 (avril 2026), ministères invités à formuler la leur d'ici fin 2026 ; plan « Notre IA » et fusion de la DINUM dans « Ariane » annoncée le 30/04/2026 (sources de presse, dates parfois contradictoires) — [Acteurs publics](https://acteurspublics.fr/articles/la-dinum-reoriente-sa-feuille-de-route-avec-un-oeil-vers-le-prive/); [Banque des Territoires](https://www.banquedesterritoires.fr/avec-le-plan-notre-ia-letat-accelere-sur-le-deploiement-des-outils-et-la-gouvernance); [Acteurs publics fusion](https://acteurspublics.fr/articles/la-fusion-de-la-dinum-et-de-la-ditp-symbole-dune-absence-de-pilotage-sur-la-cybersecurite/); [info.gouv](https://www.info.gouv.fr/index.php/communique/protection-des-donnees-des-francais-l-etat-poursuit-une-strategie-acceleree-de-securisation)
- DINUM : tournée de 3 ans (depuis février 2026) pour présenter sa feuille de route aux collectivités — [Acteurs publics](https://acteurspublics.fr/articles/la-dinum-lance-son-tour-de-france-de-la-transformation-numerique-des-territoires/)
- Collectivités : SDTAN (art. L.1425-2 CGCT), SDUN, SDUS, plan numérique territorial ; ANCT propose un pas-à-pas numérique responsable distinguant collectivités avec/sans DSI — [ARCEP](https://www.arcep.fr/fileadmin/cru-1714402758/reprise/dossiers/collectivites/L1425-2/declaration-L1425-2.doc); [maire-info](https://www.maire-info.com/numerique-responsable-un-guide-pour-aider-les-collectivites-�-sengager-article2-29716)
- Cour des comptes (10/07/2024) : légitimité de la DINUM « à consolider », absence de vision consolidée de la dépense numérique, dette technique ; (31/10/2025) gouvernance éclatée de la souveraineté des SI civils — [LMI](https://www.lemondeinformatique.fr/actualites/lire-la-cour-des-comptes-pousse-la-dinum-a-plus-d-action-94294.html); [Solutions Numériques](https://www.solutions-numeriques.com/?p=242059); [Acteurs publics](https://acteurspublics.fr/articles/la-cour-des-comptes-sagace-de-ne-pas-pouvoir-evaluer-les-depenses-numeriques-de-letat)

### Inferences
- Odin doit gérer la conformité à des « avis » (objet : dossier d'avis, seuil, statut conforme/consultatif, réserves) et des feuilles de route ministérielles à remonter à la tutelle ; le seuil et la structure DINUM évoluent, donc paramétrables.
- Le contenu type d'un SDSI/plan de transformation n'a pas été trouvé dans des sources primaires ; [connaissance générale] : diagnostic de l'existant, orientations stratégiques, cartographie cible, plan d'action pluriannuel, budget, gouvernance.
- Un dashboard « dépenses numériques consolidées » répond directement au grief de la Cour.

### Gaps
- Texte consolidé du décret 2019-1088 et du décret de mars 2026 (Légifrance inaccessible via l'outil) ; numéro et date exacts du décret de 2026.
- Panorama des grands projets numériques, feuille de route DINUM 2026 complète (hôte catalogue.numerique.gouv.fr bloqué) ; contenu type de COP/COM d'opérateurs ; doctrines UK GDS, Estonie, Danemark non recherchées ; SILL non vérifié.
- Sécurité sociale (CNAM/CNAF/UCANSS) et santé (ANS/DNS) non couverts.

## 3. Cascade stratégie → objectifs → initiatives → indicateurs dans le public

### Takeaway
Le public dispose d'une cascade budgétaire officielle (LOLF : programme → objectifs → indicateurs dans les PAP/RAP) et d'un suivi de résultats (baromètre) ; OKR/BSC sont des surcouches [connaissance générale].

### Cited Findings
- PAP : présentation stratégique du programme, objectifs, indicateurs de performance, justification par action ; indicateurs quantifiés associés aux objectifs ; le PAP 2026 de la mission Direction de l'action du Gouvernement inclut le programme de coordination de la politique numérique et la récapitulation des crédits et emplois des opérateurs — [PAP 2026 DAG](https://www.assemblee-nationale.fr/dyn/dyn/contenu/visualisation/1087966/file/PAP2026_BG_Direction_action_du_Gouvernement_DC.pdf); [PAP 2026 transformation](https://www.assemblee-nationale.fr/dyn/dyn/contenu/visualisation/1088044/file/PAP2026_BG_Transformation_fonction_publiques_TR.pdf)
- Baromètre des résultats de l'action publique : développé par Etalab/DINUM, indicateurs par politique, déclinés pour 101 départements, version de mai 2023 avec 49 chantiers prioritaires ; données sur data.gouv.fr — [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/barometre-des-resultats-de-laction-publique/)
- Baromètre des services publics (distinct, juin 2025) : délais, accessibilité, simplicité, cinq indicateurs de qualité — [modernisation.gouv.fr](https://www.modernisation.gouv.fr/files/2025-06/CP-Laurent-Marcangeli-Publication-du-Barometre-des-services-publics-2-juin-2025.pdf)

### Inferences
- Modèle de données minimal : politique publique/programme LOLF → objectif stratégique (SI et métier) → initiative/projet → indicateur (cible, trajectoire, source) → lien budgétaire (action/titre). Autoriser plusieurs référentiels de cascade (LOLF, COP, OKR, BSC) selon l'organisme.

### Gaps
- Détail de la structure COP/COM, usage réel des OKR/BSC dans le public français, dictionnaire des indicateurs du baromètre non consultés.

## 4. Décisions stratégiques récurrentes d'un DNUM/DSI public

### Takeaway
Les sources trouvées montrent surtout les décisions encadrées : hébergement cloud/souveraineté, achats SaaS, projets > seuil, dépendances. Les autres décisions (build/buy, mutualisation, SILL, décommissionnement) relèvent d'une déduction.

### Cited Findings
- Cloud : exigence SecNumCloud pour données sensibles, dérogations sous responsabilité du ministre (note DINUM 15/09/2021 sur Office 365) — [DINUM doctrine](https://www.april.org/sites/default/files/20210915-DINUM-doctrine-cloud-au-centre.pdf)
- Stratégie interministérielle de réduction des dépendances numériques ; DINUM migre ses postes vers Linux ; circulaire en préparation sur le rôle de la DINUM dans les achats numériques — [Acteurs publics](https://acteurspublics.fr/articles/une-circulaire-en-preparation-pour-repositionner-la-dinum-sur-les-achats-numeriques-publics/); [tech-insider](https://tech-insider.org/dinum-france-linux-windows-souverainete-numerique-avril-2026/)
- Dette technique et obsolescence relevées par la Cour (DGFiP, douanes, État) — [LMI](https://www.lemondeinformatique.fr/actualites/lire-la-cour-des-comptes-pointe-des-faiblesses-des-si-des-dgfip-et-des-douanes-75485.html)

### Inferences
- Fiche de décision type : option (build/buy/réutiliser/mutualiser/libre), coût complet pluriannuel (RUN/BUILD), conformité (cloud, SecNumCloud, RGPD, RGAA), dépendance fournisseur/réversibilité, risque, alignement objectifs, capacité ETP, calendrier budgétaire annuel (contrainte d'annualité). Ajouter : décommissionnement (gains attendus, dépendances), arbitrage sous gel/annulation de crédits, mutualisation inter-administrations.

### Gaps
- SILL, doctrine de réutilisation (code.gouv.fr), UK GDS/Estonie/Danemark non sourcés.

## 5. Instances de gouvernance dans le public et artefacts consommés

### Takeaway
Instances sourcées : avis DINUM, contrôle budgétaire (CBCM), Cour des comptes. Les autres sont déduites.

### Cited Findings
- Avis DINUM transmis aux contrôleurs budgétaires avant validation d'un marché ; publication des avis sur data.gouv.fr — [LMI](https://www.lemondeinformatique.fr/actualites/lireamp-les-contrats-saas-des-ministeres-sous-surveillance-de-la-dinum-99748.html); [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/publication-des-avis-dinum-articles-3-et-7/)
- Cour des comptes : audits sur la DINUM, les grands projets (11 recommandations en 2020) — [Banque des Territoires](https://www.banquedesterritoires.fr/grands-projets-numeriques-de-letat-la-cour-des-comptes-veut-transformer-lessai)

### Inferences
- Instances à modéliser : comité stratégique numérique, comité d'investissement/arbitrage, comité d'architecture, CAB, comité sécurité (RSSI/HFDS), dialogue de gestion avec la tutelle, conseil d'administration d'opérateur ; chacune avec ordre du jour, décisions, relevé de décisions, artefacts (dossier de cadrage, fiches projet, tableau de bord, plan de risques). Chaque instance doit pouvoir produire un dossier à partir des données Odin.

### Gaps
- Composition et règles de fonctionnement réelles de ces comités non sourcées.

## 6. Valeur et performance du SI public

### Takeaway
La valeur publique se mesure par la qualité de service et l'usage, plus que par le ROI ; benchmarks internationaux existent (OCDE DGI).

### Cited Findings
- OCDE Digital Government Index 2025 : France 0,80 (moyenne OCDE 0,70), +0,13 depuis 2023 ; six dimensions : data-driven public sector 0,92, open by default 0,87, proactiveness 0,80, digital by design 0,79, government as a platform 0,77, user-driven 0,67 (seule dimension sous la moyenne 0,71) ; France 1re à l'OURdata 2025 (0,96) — [OCDE note France](https://www.oecd.org/en/publications/government-at-a-glance-2025-country-notes_da3361e1-en/france_fcb2c4da-en.html); [OCDE DGI](https://www.oecd.org/en/publications/2025/06/government-at-a-glance-2025_70e14c6c/full-report/digital-government-index_1edec44e.html)
- Suivi qualitatif des 250 démarches les plus utilisées (critères : rapidité, FranceConnect) ; programme TECH.GOUV 2019 sur les démarches essentielles ; 73 % des Français ont fait une démarche en ligne en 2024 (Arcom) — [QE AN](https://www.assemblee-nationale.fr/dyn/15/questions/QANR5L15QE28463.pdf); [Plaquette TECH.GOUV](https://numerique.gouv.fr/uploads/Plaquette_TechGouv_mi2021.PDF)
- Cigref : mesure coûts + émissions (modèle économique et écologique) — voir Q1.

### Inferences
- Indicateurs : taux de démarches en ligne, satisfaction, délais, accessibilité, usage, coût par transaction, maturité (MAGNum, DGI), empreinte carbone, conformité aux exigences interministérielles.

### Gaps
- Méthodes de mesure de la valeur d'usage propres à chaque organisme, benchmarks inter-administrations (hors OCDE) non trouvés.

## 7. Axes souvent oubliés

### Takeaway
Plusieurs points sont documentés par les sources, les autres sont des propositions à valider.

### Cited Findings
- Souveraineté/dépendances comme axe stratégique 2026 : feuille de route de 33 mesures, 18,6 Md€ dont 11,1 Md€ de fonds publics (source de presse spécialisée, à vérifier) — [tech-insider](https://tech-insider.org/dinum-france-linux-windows-souverainete-numerique-avril-2026/)
- IA : plan « Notre IA » et gouvernance de l'IA dans la fonction publique en 2026 — [Banque des Territoires](https://www.banquedesterritoires.fr/en-2026-le-ministere-de-la-fonction-publique-promet-daccelerer-sur-lia)
- Numérique responsable et inclusion numérique, relation élus/territoires (guide ANCT de mobilisation des élus) — [ANCT](https://lesbases.anct.gouv.fr/download/user/9b976bee-0fb4-42cc-b63e-cb79bb9a04ba/2geGWkAtDnqcDk2cimIZ4_Guide%20Mobilisation%20des%20%C3%A9lus%20autour%20d'une%20strat%C3%A9gie%20d'inclusion%20num%C3%A9rique.pdf)
- Obligations sociales et environnementales des projets numériques — [Banque des Territoires](https://www.banquedesterritoires.fr/obligations-sociales-et-environnementales-des-projets-numeriques-suivez-le-guide)

### Inferences
- Axes à ajouter à Odin (proposition) : registre de décisions et traçabilité (exigence d'audit Cour des comptes), gestion de la demande métier/BRM, conduite du changement, gouvernance de la donnée et de l'IA, shadow IT, risque de dépendance fournisseur/souveraineté, relation tutelle/élus (rapports, avis, feuilles de route), conformité réglementaire (SREN, RGPD, RGAA, NIS2), maturité de gouvernance, empreinte environnementale, référentiel de conformité aux doctrines (cloud au centre, SILL), suivi des recommandations d'audit.

### Gaps
- Shadow IT, BRM, conduite du changement dans le public : aucune source trouvée.
