# Reporting, rapports, présentations et aide à la décision pour une DSI publique (Odin)

> Fiabilité : 9 recherches web, aucune page lue en intégral. « Cited Findings » = faits issus de résultats de recherche (beaucoup de presse spécialisée/blogs, à confirmer sur sources primaires). « Inferences » = connaissances générales non re-vérifiées.

## 1. Tableaux de bord/rapports par public, cadences, obligations de reporting propres au public
### Takeaway
Le secteur public impose ses cadres de restitution : PAP/RAP (LOLF), Panorama DINUM des grands projets, observatoire des démarches numériques essentielles, évaluation socio-économique ex ante obligatoire au-delà de 20 M€. La Cour des comptes reproche l'absence de vision consolidée de la dépense numérique. Odin doit produire des vues alignées sur ces cadres.
### Cited Findings
- Panorama des grands projets numériques de l'État : publié par la DINUM (désormais semestriellement) pour les projets ≥ 9 M€. Un rapport d'activité DINUM cite 48 projets / ~3,6 Md€ ; un rapport sénatorial de 2020 cite 54 projets / ~4 Md€ et un retard moyen de 26,6 %. Objectif DINUM : stabiliser le glissement budgétaire et calendaire global à 15 % fin 2022. Chiffres de dates différentes, à revérifier. — data.gouv.fr (panorama-des-grands-projets-numeriques-de-letat) ; Sénat r20-047 ; Acteurs publics (11e panorama)
- Baromètre des résultats de l'action publique : nouvelles politiques publiques intégrées en avril 2021 (seule mention trouvée ; contenu actuel non vérifié). — Plaquette TechGouv 2021
- LOLF : mission (unité de vote) > programme (unité de contrainte). PAP annexés au PLF (art. 51) : stratégie, objectifs, indicateurs, cibles par programme. RAP annexés à la loi de règlement : réalisations vs engagements. — Vie-publique ; Économie.gouv
- 729 indicateurs de performance (budget général 2023) selon FIPECO (633 dans une version antérieure) ; FIPECO juge que cette information n'influence pas les décisions budgétaires. — fipeco.fr
- Observatoire des démarches numériques essentielles (ex-VDE, renommé juillet 2023) : piloté par la DINUM depuis 2019, ~250 démarches (> 200 000 usages/an ou aide financière nationale). Nombre d'indicateurs divergent selon les sources (5, 8 critères, 11 après refonte). Satisfaction via « je donne mon avis ». — LMI ; Banque des Territoires ; data.gouv.fr
- Évaluation socio-économique ex ante obligatoire pour les projets financés > 20 M€ par l'État et ses établissements. Guide actualisé septembre 2023 (initial 2017, Trésor/France Stratégie) + compléments (valeurs tutélaires, cartographie des risques, valeur résiduelle). — France Stratégie ; Trésor
- Cour des comptes (juillet 2024, DINUM) : pas de « vision consolidée de la dépense numérique de l'État » ; recommandation n°11 : consolider les dépenses et systématiser le calcul des gains budgétaires. — Acteurs publics ; Solutions Numériques
- Dette technique par obsolescence jugée susceptible de mettre en risque les capacités opérationnelles de l'État ; SI DGFiP/Douanes robustes mais vieillissants (couches des années 1970). — LMI
- Cigref/IFACI/ISACA France : le GAGSI est remplacé en 2026 par « MAGNum » (modèle de maturité et référentiel d'audit de la gouvernance numérique). — docs.ifaci.com (MAGNum 2026)
- Cigref a publié un guide de tableau de bord cybersécurité pour le COMEX. — Solutions Numériques
### Inferences
- Matrice cadence (non sourcée) : hebdo/mensuel pour DSI et PMO (delivery, incidents, sécurité) ; trimestriel pour revue de portefeuille et comités investissement/architecture ; annuel pour rapport d'activité, dossier budgétaire, COP/CPOM/COG ; ad hoc pour note au cabinet et bilan de projet.
- Spécifique public : alignement programme/action LOLF, seuils DINUM et ESE, restitution à l'assemblée délibérante (collectivités), contrôle Cour/CRC. Odin devrait produire à la demande la consolidation de dépense demandée par la Cour.
- Le constat FIPECO plaide pour des tableaux de bord sobres, liés à des décisions.
### Gaps
- Contenu/cadence actuels du baromètre ; liste officielle des indicateurs de l'observatoire ; obligations des collectivités (ROB), sécurité sociale (COG), établissements publics (COP), open data.

## 2. Catalogue KPI/KRI/OKR et référentiels
### Takeaway
Référentiels sourcés : COBIT 2019, MAGNum/Cigref, DORA, observatoire DINUM. Catalogue détaillé ITIL/finance/RH non sourcé.
### Cited Findings
- COBIT 2019 : 40 objectifs en 5 domaines, 13 buts d'entreprise et 13 buts d'alignement (cascade), métriques d'exemple par objectif. — CIO Index ; ISACA
- DORA 2025 : enquête juin-juillet 2025, ~5 000 répondants ; l'IA améliore le débit mais reste associée à une baisse de stabilité ; abandon des clusters low/medium/high/elite au profit de 7 archétypes bâtis sur 8 mesures. ~90 % d'usage de l'IA, 30 % font peu ou pas confiance. — Google DORA 2025 ; RedMonk
- Cigref : tableau de bord coût/délai/qualité en benchmarking ; IT Balanced Scorecard (documents anciens, 2005-2007). — Cigref
- Indicateurs usager : satisfaction, niveau de service, accessibilité (observatoire DINUM).
### Inferences
- Familles à couvrir (non sourcé) : finances (run/build, TCO, coût par service), projets (écart coût/délai, valeur), qualité de service ITIL (incidents, MTTR, SLA), DORA et flow metrics, dette/obsolescence, sécurité (KRI), RH/ETP (vacance, dépendance prestataires, compétences rares), satisfaction usagers/agents, bénéfices réalisés, RSE.
- Spécifique public : dématérialisation, accessibilité RGAA, souveraineté/dépendance cloud, conformité RGS/SecNumCloud. Distinguer indicateurs avancés/retardés ; dater les benchmarks DORA.
### Gaps
- Benchmarks chiffrés de DSI publiques, ITIL 4, Gartner IT Key Metrics, Apptio/TBM ; contenu détaillé de MAGNum.

## 3. Bonnes pratiques de présentation aux directions et aux élus
### Takeaway
Risque documenté : « watermelon reporting ». Antidote : seuils objectifs définis à l'avance, statut automatisé depuis les données, escalade précoce des ambers. Minto, one-pager et note de décision non sourcés.
### Cited Findings
- Watermelon reporting = vert à l'extérieur, rouge à l'intérieur ; causes : culture, feux subjectifs, dissimulation, pression à rester vert ; remèdes : seuils R/A/V prédéfinis, pas de formules floues, signaler la dérive avant le seuil, automatiser le statut. Sources blog/éditeur, pas des standards. — Fluid ; Rebel's Guide to PM ; ProjectManagerTemplate
- Guide Cigref de tableau de bord cyber pour le COMEX.
### Inferences
- Note de décision (non sourcé) : décision demandée, contexte, options (dont « ne rien faire » avec coût du retard), impacts (coût, risque, service rendu, ETP, calendrier), recommandation. Principe pyramidal, one-pager par application/projet, heatmaps risque × criticité.
- Élus : traduire en service rendu aux usagers, risque de rupture, coût pour la collectivité, calendrier lié aux échéances politiques/budgétaires ; vues « élus » et « techniques » distinctes ; vigilance sur la confidentialité face aux délibérations publiques.
- Fonction Odin : statut calculé par règles paramétrables, avec historique et justification de chaque changement de couleur.
### Gaps
- Aucune source sur la présentation aux élus, Minto, gabarits publics.

## 4. Méthodes d'aide à la décision
### Takeaway
Cadre public structurant : évaluation socio-économique (analyse coûts-bénéfices, valeurs tutélaires, cartographie des risques, sensibilité, valeur résiduelle ; obligatoire > 20 M€). AHP, options réelles, optimisation de portefeuille à documenter.
### Cited Findings
- ESE > 20 M€ ; guide 2023 ; Conseil scientifique des méthodes d'évaluation socioéconomique (colloque mars 2025 sur l'ACB et les enjeux distributifs). — France Stratégie ; Trésor
- La Cour recommande de systématiser le calcul des gains budgétaires attendus. — Acteurs publics
### Inferences
- Fonctions à prévoir (non sourcé) : scoring multicritère pondéré/AHP avec sensibilité des poids, scénarios what-if budget/ETP, analyse d'impact par dépendances, business case (VAN, bénéfices non monétaires), coût du retard, optimisation de portefeuille sous contrainte, options réelles. Public : critères de valeur publique (qualité de service, équité, continuité, souveraineté) à côté du ROI.
### Gaps
- AHP, options réelles, optimisation de portefeuille appliqués au SI public ; monétisation des bénéfices du numérique public.

## 5. Traçabilité des décisions et auditabilité
### Takeaway
Point de contrôle récurrent de la Cour ; MAGNum fournit un référentiel d'audit. Registre de décisions, ADR, bilan a posteriori à spécifier à partir de bonnes pratiques non sourcées ici.
### Cited Findings
- La Cour ne peut pas évaluer la dépense numérique faute de consolidation ; RAP = comparaison a posteriori ; MAGNum 2026 = référentiel d'audit de gouvernance numérique.
### Inferences
- Objets métier (non sourcé) : décision (date, instance, options, critères, hypothèses, décideur, budget), compte rendu de comité, hypothèses du business case, bénéfices attendus vs réalisés, ADR, historique immuable, lien décision-projet-budget. Public : délégations/signatures, archivage légal, communicabilité (CRPA/CADA), exposition aux corps de contrôle.
### Gaps
- Registre de décisions, ADR, biais cognitifs.

## 6. Qualité des données conditionnant la confiance
### Takeaway
La confiance dépend de la consolidation des données ; le constat de la Cour l'illustre. Détail technique (CMDB, Chorus, SIRH) non sourcé.
### Cited Findings
- Absence de vision consolidée de la dépense numérique ; le « run » est la dépense que l'État ne veut pas voir (Acteurs publics) ; données du Panorama publiées en open data.
### Inferences
- Exigences (non sourcé) : source de vérité et propriétaire par donnée, fraîcheur/complétude affichées par indicateur, déclaratif vs automatisé, snapshots pour tendances, rapprochement finance (Chorus)/ITSM/CMDB/code/SIRH, normalisation de la frontière run/build.
### Gaps
- Intégration Chorus/SIRH ; qualité des CMDB.

## 7. IA générative fin 2026
### Takeaway
L'État déploie un « Assistant IA » souverain (ex-Albert, contrat Mistral AI) via le plan « Notre IA » ; bilan d'expérimentation prévu été 2026, publication non confirmée.
### Cited Findings
- Albert renommé « Assistant IA », contrat État-Mistral AI ; Albert expérimenté en France Services non généralisé « dans sa forme actuelle » (janvier 2026) ; Assistant IA testé auprès de 10 000 agents. — Acteurs publics ; Weka
- Plan « Notre IA » : outil conversationnel pour ~1 million d'agents, première phase évaluée à 750 000 € supplémentaires (licences Mistral, GPU en cloud souverain), outil pour 8 000 conseillers France services d'ici l'automne 2026. — Banque des Territoires ; Acteurs publics (socle IA)
- DIANE (DGFiP) mentionné par un blog de formation : source peu fiable.
- La Cour (janvier 2025) voit dans l'IA un levier majeur de gains de productivité.
### Inferences
- Cas d'usage (non sourcé) : synthèse de revue de portefeuille, langage naturel sur les données SI, brouillon de note/deck, détection d'écarts. Garde-fous : chiffres liés aux données avec sources citées (pas de chiffres libres), validation humaine, journalisation, hébergement souverain/SecNumCloud, pas de données sensibles vers des modèles non qualifiés.
### Gaps
- Cadre IA de l'État, AI Act pour les administrations, doctrine SecNumCloud pour l'IA ; bilan « Assistant IA » d'été 2026.

## 8. Besoins de diffusion
### Takeaway
Accessibilité des documents = point de vigilance, périmètre exact (RGAA 4.1 vs documents bureautiques, sanctions) incertain. DSFR et formats ouverts non sourcés.
### Cited Findings
- Directive EAA 2019/882 applicable depuis le 28 juin 2025 ; RGAA 4.1 resterait la référence d'audit française selon un consultant et ne couvrirait pas explicitement les documents bureautiques ; montants de sanction divergents (50 000 € vs 300 000 €, sources commerciales) ; un décret n° 2026-816 du 24 août 2026 est cité par un seul blog, non confirmé. — SK Web ; pdfaccessible.com
### Inferences
- À prévoir (non sourcé) : exports PDF balisés, PPTX, Excel, ODF, modèles DSFR/charte de la collectivité, vues par audience, niveaux de diffusion (Diffusion Restreinte), commentaires et workflow de validation. Une mention presse d'un rapport de la Cour d'octobre 2026 préconisant le logiciel libre pour la bureautique de l'État a été vue sans lien primaire vérifié.
### Gaps
- DSFR, PDF/UA, règles de Diffusion Restreinte, droits d'accès.

## 9. Axes oubliés potentiels
### Cited Findings
- Consolidation de la dépense numérique et calcul des gains (reco. n°11) ; suivi du glissement coût/délai des grands projets avec cible chiffrée (15 %) ; dette technique/obsolescence comme risque stratégique ; souveraineté de l'IA publique (« souveraineté opposable ») ; baromètre numérique agent (satisfaction des agents, édition 2021).
### Inferences
- Axes candidats : consolidation transverse de la dépense (run/build), suivi des bénéfices réalisés, registre et suivi des décisions, benchmark inter-administrations (open data DINUM), communication vers les métiers et agents, indicateurs avancés vs retardés, alertes et seuils paramétrables, suivi des recommandations de la Cour et des audits, souveraineté et dépendance fournisseurs, calendrier politique (élections, loi de finances), gouvernance de la donnée de pilotage elle-même.
### Gaps
- Benchmark inter-administrations hors Panorama/observatoire. Non couverts : ITIL 4, Gartner/Forrester/McKinsey, éditeurs (LeanIX, Ardoq, Planview, Apptio, ServiceNow), cabinets, DSFR, cadre IA de l'État, obligations des collectivités.
