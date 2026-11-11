# Axes métier de la stack Odin : panorama, axes manquants et cadre « organismes publics »

Date de synthèse : 11 novembre 2026. Périmètre : spécifications fonctionnelles uniquement (aucun choix technique à ce stade). Base : 8 notes de recherche (`/home/user/odin/research_notes/Axes métier de la stack Odin/`), de fiabilité inégale.

**Convention de lecture (à garder en tête tout au long du rapport)**

| Marqueur | Sens |
|---|---|
| **[S]** | Affirmation appuyée par une source citée dans les notes (souvent de la presse spécialisée ou une page éditeur, rarement un texte primaire ouvert). |
| **[S?]** | Source unique, source secondaire ou sources divergentes : à confirmer avant de s'appuyer dessus. |
| **[I]** | Inférence ou proposition de conception issue des notes, non sourcée. |
| **[CG]** | Connaissance générale du domaine, non sourcée dans les notes. |
| **[U]** | Axe cité par l'utilisateur. |
| **[+]** | Axe ajouté (absent de la liste initiale). |

Les notes ont été rédigées avec 9 à 18 appels de recherche chacune ; aucune n'a lu intégralement les textes primaires (Légifrance, rapports de la Cour des comptes, JOUE). Tout chiffre ou date réglementaire ci-dessous doit donc être lu comme « tel que rapporté par les notes ».

---

## 1. Synthèse exécutive

**Panorama.** À partir de la liste initiale (dette, roadmaps, objectifs, sécurité, reporting, ressources/ETP, métiers, rapports, présentations), les notes font ressortir **environ 30 axes métier**, regroupés ici en **7 domaines** (§2). Les axes cités par l'utilisateur ne couvrent que ce qui se voit en sortie (roadmaps, reporting, rapports, présentations) et quelques entrées (dette, ressources, sécurité, objectifs). Il manque l'essentiel de ce qui rend les décisions possibles : le **patrimoine SI** et ses **liens avec les services publics**, l'**argent**, les **contrats/fournisseurs**, la **demande** et les **bénéfices**, la **conformité**, la **continuité**, la **traçabilité des décisions** et la **gouvernance de l'IA**.

**Principaux axes manquants (priorisés au §3, jugement de synthèse [I]).**
1. *Indispensables* : patrimoine applicatif/technologique et capacités métier/services publics ; finances SI (y compris le « run » invisible) ; demande, portefeuille et bénéfices ; fournisseurs, commande publique et souveraineté ; conformité et obligations datées ; continuité/criticité ; décisions et traçabilité ; compétences/GEPP ; qualité et fraîcheur des données ; gouvernance de l'IA et protection des agents.
2. *Importants* : scénarios/what-if, gouvernance politique et élus, suivi des recommandations de contrôle, absorption du changement, mutualisation multi-entités, numérique responsable, données/open data.
3. *Optionnels/sectoriels* : maturité de gouvernance (MAGNum), indicateurs d'ingénierie (DORA), benchmark inter-administrations, volet santé (CaRE).

**Points de vigilance du contexte public.**
- Le secteur public n'est pas un bloc (État, opérateurs, collectivités, syndicats mutualisés, sécurité sociale, hôpitaux/GHT, universités) : Odin doit être **paramétrable par profil d'organisme** [S/I].
- Les unités et cadres sont spécifiques : **ETPT vs ETP vs plafond d'emplois**, **LOLF** (programme, titres, AE/CP) pour l'État, **M57/AP-CP** pour les collectivités ([S] pour l'ETPT ; [CG] pour le reste).
- Le cadre réglementaire est **instable et daté** : seuil d'avis DINUM (9 M€ ou 15 M€, divergence non tranchée), loi Résilience/NIS2 non promulguée selon les notes, calendrier AI Act divergent. Odin doit porter ces règles comme des **données versionnées avec statut juridique**, pas comme du code figé (§4).
- Contrainte d'éligibilité probable : hébergement souverain (SecNumCloud ou on-premise), accessibilité (RGAA), réversibilité [S/I].

**Vigilance sur l'exigence « tous contribuent + IA ».**
- Les notes ne trouvent **aucune offre du marché** combinant dépôt de rapports par tous les profils, extraction par IA avec validation humaine, rattachement au référentiel SI et production traçable ; c'est une absence de preuve dans un échantillon limité, pas une preuve d'absence [I].
- Risques majeurs : dérive vers la **surveillance/évaluation des agents** (AI Act « emploi », RGPD, dialogue social), **injection de prompt indirecte** via les documents déposés, **hallucinations** contaminant les indicateurs, **confusion rapport/alerte protégée** (loi Waserman), **dépendance à un modèle non souverain** (§5).
- Le point d'échec historique des outils d'architecture d'entreprise est la **qualité et la fraîcheur des données**, pas la modélisation [S] ; l'adoption par « tout le monde » est donc à la fois la solution et le risque.

**Lacunes de recherche majeures** (détail §9) : textes primaires non lus ; RGPD/HDS/RGAA/DSFR/RGS/M57/seuils de marchés non sourcés ; collectivités, sécurité sociale, santé peu couvertes ; aucune donnée d'adoption ou de qualité de l'IA documentaire ; capacités IA réelles de plusieurs éditeurs non vérifiées.

---

## 2. Cartographie des axes métier

Format de chaque axe : **Définition** · **Objets clés** · **Indicateurs typiques** · **Décisions éclairées** · **Spécifique public**. Les indicateurs et décisions sont, sauf mention, des propositions [I] issues des notes.

### Domaine A. Stratégie, gouvernance et conformité aux doctrines

**A1. Objectifs et stratégie [U : « objectifs »]**
- *Définition* : cascade politique/mission → objectif stratégique → initiative → indicateur → lien budgétaire ; alignement du SI sur la stratégie.
- *Objets* : politique publique/programme, objectif, cible et trajectoire, initiative, indicateur (source, cible), lien budgétaire (action/titre). Autoriser plusieurs référentiels de cascade (LOLF, COP/COM, OKR, BSC) [I].
- *Indicateurs* : part du portefeuille alignée par objectif, avancement des cibles, taux d'objectifs sans initiative.
- *Décisions* : arbitrage entre objectifs concurrents, abandon d'objectifs sans levier.
- *Public* : la cascade budgétaire officielle existe (LOLF : PAP/RAP avec objectifs et indicateurs) [S, [PAP 2026](https://www.assemblee-nationale.fr/dyn/dyn/contenu/visualisation/1087966/file/PAP2026_BG_Direction_action_du_Gouvernement_DC.pdf)] ; FIPECO relève 729 indicateurs au budget général 2023 sans influence démontrée sur les décisions budgétaires [S?, via fipeco.fr cité par la note reporting], d'où l'intérêt d'indicateurs peu nombreux et liés à des décisions. Les feuilles de route ministérielles (numérique, cyber) à remonter à la tutelle [S?].

**A2. Gouvernance, instances, décisions et traçabilité [+]**
- *Définition* : instances de décision, relevés de décisions, hypothèses et alternatives écartées, historique immuable.
- *Objets* : instance (comité stratégique, d'investissement, d'architecture, sécurité, dialogue de gestion), ordre du jour, décision (date, décideur, options, critères, hypothèses, budget), dossier, lien décision–projet–budget, ADR (décision d'architecture), dérogation [I ; ADR/ADR registre : [CG]].
- *Indicateurs* : délai demande → décision, part de décisions documentées, dérogations ouvertes, décisions sans bilan a posteriori.
- *Décisions* : c'est le produit même d'un outil d'aide à la décision ; sert à justifier devant la tutelle ou un contrôle.
- *Public* : exigence d'audit (la Cour a signalé ne pouvoir évaluer la dépense numérique faute de consolidation [S]) ; délégations/signatures, archivage légal, communicabilité CRPA/CADA [I, non sourcé]. Composition et règles réelles des comités publics non sourcées.

**A3. Conformité aux doctrines et avis obligatoires [+]**
- *Définition* : suivi des avis préalables, des exigences de doctrine et de leurs échéances.
- *Objets* : obligation (texte, date d'entrée en vigueur, périmètre applicable par type d'organisme, statut juridique), exigence/contrôle, statut de conformité par système/projet, avis (DINUM, CNIL/DPO, RSSI), réserve, échéance [I].
- *Indicateurs* : projets proches du seuil d'avis, avis tardifs/absents, taux de conformité à la doctrine cloud (la DINUM relève environ 37 % de projets non conformes selon un bilan de janvier 2026 [S?, via Solutions Numériques]).
- *Décisions* : saisir ou non la DINUM, héberger où, dérogation ou mise en conformité.
- *Public* : voir §4. Fonction concrète citée : « jauge de seuil » d'alerte [I].

**A4. Suivi des recommandations de contrôle externe [+]**
- *Définition* : recommandations de la Cour des comptes, CRC, IGA/IGF, CNIL, ANSSI et plans d'action associés.
- *Objets* : recommandation, source, échéance, action, propriétaire, statut [I].
- *Indicateurs* : % de recommandations soldées, retards.
- *Décisions* : priorisation de remédiations imposées de l'extérieur.
- *Public* : spécifique au public ; mécanismes CRC/IGF/IGA non recherchés avec sources (lacune).

### Domaine B. Patrimoine du SI et lien avec les services publics

**B1. Capacités métier, processus et services publics (précise « métiers ») [+/U]**
- *Définition* : ce que l'organisme sait faire (capacités), les démarches/services rendus, et leur lien avec les applications.
- *Objets* : politique publique/mission, démarche/service, capacité métier, processus, direction métier, usager (citoyen, entreprise, agent) [S/I].
- *Indicateurs* : capacités servies par N applications (doublons) ou sans application ; qualité de la démarche (satisfaction, accessibilité, délai) ; % de démarches s'appuyant sur des briques mutualisées (FranceConnect, API Particulier) [I].
- *Décisions* : rationalisation entre directions, priorisation selon l'impact usager.
- *Public* : l'observatoire DINUM suit environ 250 démarches essentielles (nombre de critères divergent : 5, 8 ou 11 selon les sources) [S?, [data.gouv.fr](https://www.data.gouv.fr/datasets/observatoire-de-la-qualite-des-demarches-en-ligne/informations)]. Aucune cartographie publique outillée des processus/capacités de l'État n'a été trouvée.
- *Ambiguïté à trancher* : « métiers » peut désigner les directions métier/capacités **ou** les profils de métiers RH (voir D2 et §8).

**B2. Patrimoine applicatif, données et flux [+]**
- *Définition* : inventaire et cycle de vie des applications, interfaces, objets de données, dépendances.
- *Objets* : application, composant, service applicatif, interface/API, objet de données, jeu de données, propriétaire, environnement, licence ; référentiels de réutilisation (SILL) [S/I].
- *Indicateurs* : nombre d'applications par statut TIME (Tolerate/Invest/Migrate/Eliminate) [S], coût et ETP par application, taux de réemploi (SILL), applications sans propriétaire.
- *Décisions* : arrêter, fusionner, adopter une brique mutualisée, sortir d'un éditeur. Stratégies de type 6R/7R : [CG] (aucune source).
- *Public* : SILL (~530 logiciels en 2025, ordre de grandeur fluctuant) [S?] ; briques mutualisées (FranceConnect, ProConnect, API Particulier/Entreprise) [S] ; double cartographie urbanisation + sécurité (guide ANSSI, Mercator) [S]. Aucun chiffre consolidé du portefeuille applicatif de l'État n'a été trouvé.

**B3. Patrimoine technologique et obsolescence [+]**
- *Définition* : composants techniques, versions, dates de fin de support, standards.
- *Objets* : composant, version, fin de support, vulnérabilité (CVE), SBOM, catalogue de standards, hébergement et qualification [S/I].
- *Indicateurs* : % d'applications/composants hors support, alerte à 12/24 mois avant fin de support, âge médian [I].
- *Décisions* : montées de version prioritaires, négociation de support étendu.
- *Public* : les dates de fin de support doivent venir de sources externes (ex. endoflife.date) car CycloneDX 1.6 n'a pas de champ EOL [S, [endoflife.ai](https://endoflife.ai/article-sbom-end-of-life)].

**B4. Dette technique [U : « dette »]**
- *Définition* : écart entre l'état du SI et un état soutenable, chiffré en coût de remédiation et en risque.
- *Objets* : élément de dette (typologie : code, architecture, infrastructure, tests, documentation, sécurité, données, compétences, contractuelle [CG]), coût de remédiation, risque associé, plan de remboursement.
- *Indicateurs* : dette en jours-homme et en euros, ratio dette/valeur, ratio RUN/BUILD, applications critiques hors support, part du budget consacrée à la remédiation [I].
- *Décisions* : financer la remédiation ou des projets neufs ; arrêter des lignes de code ; plan de départs de compétences (ex. COBOL).
- *Public* : pas de chiffrage consolidé de la dette technique de l'État [S, [Cour des comptes 2024 via Solutions Numériques](https://www.solutions-numeriques.com/?p=228889)] ; la Cour juge l'obsolescence susceptible de « mettre en risque les capacités opérationnelles » [S] ; cas DGFiP (700 applications, COBOL) [S]. Le chiffre McKinsey (20 à 40 % de la valeur du parc) est déclaratif et hors secteur public [S?]. Odin répond précisément au besoin d'une vue consolidée.

### Domaine C. Transformation : demande, portefeuille, roadmaps, scénarios

**C1. Demande et priorisation [+]**
- *Définition* : entonnoir amont (idées, besoins métier), qualification, scoring, file d'attente.
- *Objets* : demande, fiche de qualification, grille de critères, score, décision d'arbitrage [I]. Méthodes : WSJF, RICE [S] ; MoSCoW, AHP, matrice valeur/risque [CG ou non sourcé].
- *Indicateurs* : volume et âge des demandes, taux d'acceptation, demande non servie par direction métier [I].
- *Décisions* : lancer, différer, refuser ; ligne de coupe budgétaire.
- *Public* : critères de valeur publique (qualité de service, équité, continuité, souveraineté) à côté du ROI [I] ; catégories « non arbitrables » (obligations réglementaires, obsolescence) [I]. Aucune source sur la gestion de la demande métier dans le public.

**C2. Portefeuille de projets/initiatives, valeur et bénéfices [+, partiellement U]**
- *Définition* : ensemble des investissements de changement gérés comme un tout, jusqu'au constat des bénéfices.
- *Objets* : initiative/projet/programme, portefeuille, jalon/stage gate, business case, bénéfice (type, propriétaire métier, cible, date de constat), bilan post-projet, coût du retard, scénario « ne rien faire » [I].
- *Indicateurs* : écart coût/délai, taux de réalisation des bénéfices, part de projets avec business case mesurable, projets arrêtés [I].
- *Décisions* : poursuivre/arrêter une initiative dont le cas d'affaires se dégrade.
- *Public* : le Panorama DINUM suit les grands projets (écart budgétaire moyen 10,8 % fin 2023 contre 24 % un an plus tôt et 32 % en 2016 [S?, [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-le-cout-des-grands-projets-it-de-l-etat-un-peu-mieux-maitrise-97718.html)]) ; évaluation socio-économique ex ante obligatoire au-delà de 20 M€ [S?, France Stratégie/Trésor] ; causes d'échec récurrentes surtout organisationnelles [S]. Aucune statistique fiable sur la réalisation des bénéfices n'a été trouvée.

**C3. Roadmaps [U : « roadmaps »]**
- *Définition* : trajectoires dans le temps, avec dépendances et scénarios.
- *Types* (tous [I]/[CG]) : stratégique/schéma directeur, transformation, produit, applicative (TIME), technologique/obsolescence, sécurité, par capacité, **réglementaire** (échéances non négociables), sourcing/contrats.
- *Objets* : horizon, thème, initiative, jalon, dépendance typée, hypothèse, niveau de confiance, baseline, version, scénario [I].
- *Indicateurs* : glissement vs baseline, part « subie » (réglementaire + obsolescence) vs « choisie », jalons en collision sur une même équipe/un même métier.
- *Décisions* : séquencement, gel/décalage, date d'engagement communicable.
- *Public* : le calendrier politique (mandats, élections) et budgétaire annuel sont des jalons structurants ; les échéances contractuelles et de fin de support aussi [S/I]. La valeur d'Odin est dans le **croisement** (fin de support + renouvellement de marché + projet métier sur la même application) [I]. Aucune source dédiée aux typologies de roadmaps.

**C4. Scénarios, simulation et aide à l'arbitrage [+]**
- *Définition* : comparaison d'options sous contraintes de budget, capacité et risque.
- *Objets* : scénario, hypothèses, critères pondérés, analyse d'impact par dépendances [I].
- *Indicateurs* : sensibilité aux poids, effets sur budget/ETP/risque.
- *Décisions* : choix de trajectoire. Le reproche récurrent aux outils SPM est un reporting qui « aide peu à décider » [S?, avis PeerSpot/Gartner Peer Insights].
- *Public* : l'évaluation socio-économique offre un cadre (valeurs tutélaires, sensibilité, valeur résiduelle) [S?].

### Domaine D. Ressources : personnes, argent, fournisseurs

**D1. Ressources et capacité en ETP [U : « ressources disponibles (ETP) »]**
- *Définition* : confrontation capacité disponible / demande par période, équipe, rôle, compétence.
- *Objets* : poste/personne, équipe, rôle, statut (titulaire, contractuel, prestataire en régie/forfait, apprenti), affectation, disponibilité, demande de ressource, scénario [I].
- *Indicateurs* : capacité brute vs nette, taux de charge, répartition run/build/transformation, ratio internes/externes, capacité libre à 3/6/12 mois [I].
- *Décisions* : nombre d'initiatives en parallèle, recruter ou externaliser, réaffecter.
- *Public* : **trois mesures à distinguer** : ETP, ETPT (moyenne annualisée, base du plafond d'emplois LOLF) et ETP prestataires ; le plafond d'emplois est une autorisation parlementaire par ministère, le schéma d'emplois est mesuré en ETP au 31 décembre [S, [Assemblée nationale MEC](https://www.assemblee-nationale.fr/13/pdf/cr-mec/10-11/c1011020.pdf)] ; risque d'« arbitrage T2/T3 » (substituer des prestataires aux agents quand le plafond est atteint, masquant le coût) [I]. Forrester France (masse salariale 35 %, prestations 25 % du budget DSI) vaut pour le privé [S?].

**D2. Compétences, métiers et GEPP [U : « métiers » (si lu comme profils)]**
- *Définition* : compétences détenues/requises, aujourd'hui et à l'horizon des roadmaps, et plan pour combler l'écart.
- *Objets* : emploi-type, compétence et niveau, personne clé, plan de succession, formation, besoin de recrutement, vacance de poste [S/I]. Référentiels : nomenclature Cigref (~50 métiers, 9 familles ; 52 ou 54 selon les sources), e-CF (EN 16234-1:2019, 41 compétences, 5 niveaux), SFIA 9 (7 niveaux) [S] ; en public RMFP (remplace le RIME) et référentiel de rémunération de 55 métiers du numérique (circulaire 6434/SG du 3 janvier 2024) [S].
- *Indicateurs* : couverture compétences × équipes, « bus factor » = 1 (non formalisé en source), part de compétences critiques détenues par des externes, départs prévisibles, ancienneté de vacance, écart rémunération/fourchette [I].
- *Décisions* : internaliser/externaliser, recrutement, faisabilité d'une trajectoire au regard des compétences.
- *Public* : référentiel paramétrable et versionné (ne pas coder en dur les nomenclatures) ; dépendance aux prestataires documentée par un rapport sénatorial ancien [S]. Référentiel territorial CNFPT non vérifié.

**D3. Finances du SI [+]**
- *Définition* : construction, suivi et explication du coût du SI selon plusieurs axes simultanés.
- *Objets* : exercice/version budgétaire, nature (CAPEX/OPEX), destination (run/build/transformation), cost pool, tour technologique, application/service, règle d'allocation, contrat, scénario budgétaire [S pour le modèle TBM ; I pour la déclinaison].
- *Indicateurs* : trajectoire RUN/BUILD, TCO et coût par application/service, écart budget/réalisé, inflation fournisseur, projection du run à périmètre constant [I].
- *Décisions* : niveau et répartition du budget, plan d'économies, showback ou chargeback (distinction [CG]).
- *Public* : **le run est invisible dans les restitutions de l'État** (seul le build capitalisé apparaît) [S?, [Acteurs publics, 09/09/2026](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)] ; absence de vision consolidée de la dépense numérique (Cour, 2024, recommandation n°11 : consolider et calculer les gains) [S] ; imputation LOLF (programme/BOP/UO, titres 2/3/5, AE/CP) [CG] ; collectivités : M57, AP/CP, PPI, FCTVA, subventions DETR/DSIL [CG, à valider]. Les ratios de référence (IT en % du CA, part du run) sont payants ou non sourcés : **ne pas en citer**.

**D4. Fournisseurs, contrats, commande publique et souveraineté [+]**
- *Définition* : portefeuille de fournisseurs et d'engagements, échéances, dépendance.
- *Objets* : fournisseur (et groupe), marché/accord-cadre/commande UGAP, durée, reconductions, préavis, montant engagé vs maximum, clause (RSE, sécurité, réversibilité, localisation des données), licence (droits détenus/déployés/utilisés), plan de sortie [S/I].
- *Indicateurs* : concentration (part des 5 ou 10 premiers), échéancier de renouvellement à 6/12/24 mois, hausse tarifaire subie, fonctions critiques dépendant d'un fournisseur unique, juridiction du fournisseur.
- *Décisions* : renouveler/renégocier/sortir, lancer la remise en concurrence suffisamment tôt.
- *Public* : UGAP (« Nuage public » : 84 M€ de commandes en 2025 dont 22 M€ SecNumCloud ; 70 % à des acteurs européens référencés [S?]) ; la Cour recommande une migration de la bureautique vers des logiciels libres en 3-4 ans (octobre 2026, via presse) [S?] ; contrôle DINUM sur les contrats SaaS [S?, seuil à vérifier] ; hausses éditeurs (Broadcom/VMware : +800 à 1 500 % selon un observatoire, non vérifié) [S?]. Seuils de procédure et durées maximales de marché : non sourcés. Le modèle du registre DORA (finance uniquement) est transposable comme structure de données [I].

### Domaine E. Sécurité, risques, résilience et conformité

**E1. Sécurité et risques cyber [U : « sécurité »]**
- *Définition* : pilotage de la posture de sécurité, des risques et de leur traitement.
- *Objets* : SI à enjeux, analyse de risques (EBIOS RM : valeurs métier, biens supports, événements redoutés, scénarios [CG]), décision d'homologation (autorité, date, durée, risques résiduels acceptés), mesure/contrôle, incident, dérogation à la PSSI, vulnérabilité [S/I].
- *Indicateurs* (proposés) : % de SI critiques homologués (en cours de validité), % de comptes administrateur sous MFA, couverture EDR, délai de correction des vulnérabilités critiques, % d'actifs hors support, couverture PCA/PRA testée, maturité ReCyF [I]. Échéances mesurables de la feuille de route de l'État 2026-2027 : homologation des SI à enjeux fin 2026, MFA admin au 31/12/2026, PSSIE à mettre à jour au plus tard T1 2027 [S?].
- *Décisions* : arbitrer entre homologations, MFA, EDR, migration SecNumCloud.
- *Public* : voir §4 (ANSSI, PSSIE, homologation, MonServiceSécurisé, CaRE). Odin s'interface avec un outil GRC plutôt que le remplacer [I].

**E2. Continuité et criticité [+]**
- *Définition* : criticité des services publics et des applications, résilience.
- *Objets* : BIA par processus/service, RTO/RPO, lien application ↔ service ↔ PCA/PRA, exercices de crise [I ; ISO 22301 : [CG]].
- *Indicateurs* : % de services essentiels couverts par un PCA testé.
- *Décisions* : priorisation de la dette et des investissements de résilience.
- *Public* : la criticité est celle de la **continuité du service public** (usagers concernés, obligations légales), distincte de la criticité technique [I] ; les projets Louvois/ONP illustrent l'impact sur les agents [S].

**E3. Conformité réglementaire et données personnelles [+]**
- *Définition* : registre des obligations, périmètres, preuves et audits.
- *Objets* : obligation, exigence, preuve, audit, registre RGPD/AIPD, registre des systèmes d'IA, responsable désigné [I].
- *Indicateurs* : % d'exigences conformes par système, échéances à 90 jours.
- *Public* : texte par texte au §4. Plusieurs textes cités par la demande ne sont pas sourcés (RGS, PSSIE détaillée, RGI, RGAA, DSFR, eIDAS 2, Data Act, HDS).

**E4. Numérique responsable [+]**
- *Définition* : empreinte environnementale et écoconception.
- *Objets/indicateurs* : bilan carbone du SI, score RGESN (78 critères, 8 familles, version finale mai 2024) [S?] ; modèle Cigref coûts + émissions (4e édition 2022) [S].
- *Public* : la loi REEN est invoquée par une source commerciale comme obligation depuis 2025 pour les collectivités concernées [S? à vérifier au texte]. La CSRD ne s'applique en principe pas directement aux entités publiques non commerciales [I].

### Domaine F. Restitution et production de documents

**F1. Reporting et tableaux de bord [U : « reporting »]**
- *Définition* : restitution outillée, par audience et cadence.
- *Objets* : tableau de bord par rôle, indicateur (définition, source, propriétaire, fraîcheur), seuil R/A/V, historique de statut avec justification [I].
- *Indicateurs* : fraîcheur et complétude de chaque donnée de pilotage.
- *Décisions* : détecter tôt les dérives. Remède documenté au « watermelon reporting » : seuils objectifs prédéfinis, statut automatisé depuis les données, escalade précoce [S?, sources blog/éditeur].
- *Public* : cadres de restitution à alimenter (PAP/RAP, Panorama DINUM semestriel, observatoire des démarches, ROB/COG/COP selon l'organisme, ces trois derniers non sourcés) ; consolidation de la dépense demandée par la Cour [S].

**F2. Rapports et contribution de tous [U : « rapports »]** : développé au §5.

**F3. Présentations et supports de décision [U : « présentations »]**
- *Définition* : production de supports par audience (COMEX, comité d'investissement, élus, tutelle).
- *Objets* : gabarit de l'organisme, note de décision (décision demandée, contexte, options dont « ne rien faire » avec coût du retard, impacts, recommandation) [I, non sourcé], one-pager par application/projet.
- *Public* : l'élu a besoin du service rendu, du risque de rupture, du coût et du calendrier lié aux échéances politiques [I] ; accessibilité des documents (RGAA/directive EAA, périmètre exact incertain, §4).

### Domaine G. IA et qualité des données d'Odin

**G1. Gouvernance de l'IA (usages de l'organisme et d'Odin) [+]**
- *Définition* : inventaire et maîtrise des systèmes d'IA.
- *Objets* : actif IA (agent, modèle, serveur MCP), classification AI Act, usage, risque, valeur, jeu de données [S pour la tendance marché (SAP LeanIX AI governance) ; I pour le reste].
- *Public* : doctrine IA de l'État (plan « Notre IA », guide DINUM juin 2026, charte du Conseil d'État décembre 2025) [S?] ; voir §5.

**G2. Qualité, fraîcheur et gouvernance des données du référentiel [+]**
- *Définition* : confiance dans les données de pilotage.
- *Objets/exigences* : propriétaire et source de vérité par donnée, complétude, fraîcheur, déclaratif vs automatisé, snapshots, rapprochement finance/ITSM/CMDB/code/SIRH [I].
- *Constat marché* : première difficulté rapportée des outils EA [S, [communauté LeanIX](https://community.leanix.net/the-americas-user-group-47/navigating-data-quality-challenges-in-leanix-726)] ; privilégier l'alimentation automatique et afficher la fiabilité de chaque donnée [I].

**G3. Mutualisation et multi-entités [+, conditionnel à la cible]**
- *Objets* : entité mutualisatrice/utilisatrice, services socle partagés, convention, quote-part, refacturation [I]. Pertinent si des syndicats informatiques ou DSI mutualisées sont clients (maturité très inégale des collectivités [S?]).

**Autres axes cités par les notes, de rang optionnel** : maturité de gouvernance (auto-évaluation type MAGNum 2026, Cigref/IFACI/ISACA France [S?]) ; indicateurs d'ingénierie type DORA (enquête 2025 : l'IA améliore le débit mais reste associée à une baisse de stabilité [S?]) ; benchmark inter-administrations (open data DINUM) [I] ; conduite du changement et capacité d'absorption des métiers (périodes de gel, populations impactées) [I, aucune source] ; santé : CaRE, GHT, HDS [S?/I].

**Récapitulatif cité vs ajouté.**

| Liste de l'utilisateur | Où dans la cartographie |
|---|---|
| dette | B4 (nourrie par B2/B3) |
| roadmaps | C3 (nourrie par C1, C2, C4, D4) |
| objectifs | A1 |
| sécurité | E1 (étendue par E2, E3) |
| reporting | F1 |
| ressources (ETP) | D1 (étendue par D2, D3) |
| métiers | ambigu : B1 (capacités/directions métier) et/ou D2 (profils RH) |
| rapports | F2 / §5 |
| présentations | F3 |

---

## 3. Axes manquants priorisés

Priorisation = jugement de synthèse [I], fondé sur la fréquence dans les notes, l'effet sur les décisions et le poids du contexte public. À valider avec l'utilisateur.

### 3.1 Indispensables

| Axe | Justification |
|---|---|
| **Patrimoine applicatif/technologique, données, capacités et services publics (B1-B3)** | Les roadmaps, la dette, la sécurité et les finances s'appuient sur un référentiel commun ; aucun outil EAM seul ne porte ETP ni risque cyber structuré [S?/I]. Référentiel de référence côté sécurité : guide ANSSI/Mercator [S]. |
| **Finances SI (D3)** | Premier langage de la direction ; « le run est invisible » et la Cour réclame une consolidation [S]. Plan de charge et budget sont deux vues d'une même réalité [I]. |
| **Demande, portefeuille et bénéfices (C1-C2)** | « Roadmaps » est un résultat ; il manque l'entonnoir amont et la boucle de vérification [I]. Référentiels PMI/MoP en font des domaines à part entière [S?]. |
| **Fournisseurs, commande publique, souveraineté (D4)** | Échéances dures et risque de dépendance chiffré (Cour 2026, doctrine cloud) [S?] ; une date de préavis manquée verrouille une décision pour des années [I]. |
| **Conformité et obligations datées (A3, E3)** | Cadre public dense, instable et versionné ; sans cet axe Odin ne peut pas dire ce qui s'applique à qui [S/I]. |
| **Continuité et criticité (E2)** | Alimente la priorisation de la dette et des investissements ; spécificité publique (continuité du service public) [I]. |
| **Décisions et traçabilité (A2)** | Exigence d'audit et nature même de l'aide à la décision [I]. |
| **Compétences/GEPP (D2)** | Deux ETP ne sont pas interchangeables ; le risque « personne clé » relie dette, capacité et continuité [I]. |
| **Qualité des données du référentiel (G2)** | Premier facteur d'échec rapporté des référentiels EA [S] ; condition de la confiance dans les indicateurs. |
| **Gouvernance de l'IA et protection des agents (G1 + §5)** | Découle de l'exigence « IA + tous contribuent » ; risque AI Act « emploi » et dialogue social [S?/I]. |

### 3.2 Importants

| Axe | Justification |
|---|---|
| Scénarios et simulation (C4) | Existent en SPM sur projets/ressources/budget mais pas croisés avec dette et risque [I]. |
| Gouvernance politique, élus, calendrier électoral (A2/F3) | Conditionne le séquencement ; entièrement [I], non sourcé. |
| Suivi des recommandations de contrôle (A4) | Spécifique public ; demandé par la logique d'audit [I]. |
| Absorption du changement par les métiers | Contrainte de capacité côté métiers, hors DSI ; aucune source [I]. |
| Mutualisation multi-entités (G3) | Critique si des collectivités via syndicats sont ciblées [S?/I]. |
| Numérique responsable (E4) | Référentiels publics existants (RGESN) ; obligation légale à confirmer [S?]. |
| Données et open data (obligations d'ouverture) | Loi pour une République numérique : [CG], non sourcée. |

### 3.3 Optionnels ou sectoriels
Maturité de gouvernance (MAGNum), indicateurs d'ingénierie (DORA), benchmark inter-administrations, volet santé (CaRE/HDS/GHT), gamification de la contribution (aucune source d'efficacité).

---

## 4. Cadre propre au secteur public

Tout ce qui suit est à lire avec les marqueurs de fiabilité. **Aucun texte primaire (Légifrance, JOUE, JO) n'a été consulté dans les notes.**

### 4.1 Acteurs
- **DINUM** (direction interministérielle du numérique), avis sur les projets, Panorama, SILL, observatoire des démarches, plateforme IA « Albert »/« Assistant » [S]. Une réorganisation est évoquée : annonce du 30 avril 2026 d'une « Autorité numérique de l'État » à créer avant le 1er janvier 2027 ([Acteurs Publics, 09/09/2026](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)) et fusion DINUM/DITP dite « Ariane » ; dates et contenus **contradictoires selon les sources** [S?]. L'organigramme est donc à traiter comme paramétrable.
- **ANSSI** (cartographie, homologation, SecNumCloud, ReCyF, guides IA) ; **CNIL** ; **DGAFP** (guide IA, RH) ; **Cour des comptes**, CRC, IGF, IGA ; **UGAP** ; **ANS/DNS** pour la santé ; **ANCT** pour les territoires [S].
- Tutelles et contrôle budgétaire : avis DINUM transmis aux contrôleurs budgétaires avant validation d'un marché [S?, [LMI](https://www.lemondeinformatique.fr/actualites/lireamp-les-contrats-saas-des-ministeres-sous-surveillance-de-la-dinum-99748.html)] ; CBCM (nom cité, règles non sourcées).

### 4.2 Textes et doctrines, avec incertitudes

| Sujet | Ce que disent les notes | Incertitude / à vérifier |
|---|---|---|
| **Décret 2019-1088 (avis DINUM)** | Avis conforme pour les projets de l'État et organismes sous tutelle ≥ 9 M€ TTC (arrêté du 5 juin 2020), 30 jours, 5 axes d'évaluation [S] ; décret modifié en 2023 (2023-304 du 22/04/2023) [S]. | **Divergence : seuil 9 M€ vs 15 M€.** Un article de presse (source unique) rapporte une révision par décret « du 18 mars » (2026 selon le contexte) relevant le seuil à 15 M€ (maintenance 2 ans incluse), avec contrôle des SaaS/suites collaboratives au-delà de 2 M€/an [S?]. Une autre note parle d'un décret de mars 2026 sans seuil confirmé. **Seuil, date et numéro du décret à vérifier sur Légifrance** ; rendre le seuil paramétrable. |
| **Cloud au centre** | Circulaire 6282-SG du 05/07/2021 ; mise à jour 2023 (**25 ou 31 mai selon les sources**) ; consolidée par la loi SREN n° 2024-449 du 21/05/2024 (art. 31) ; décret d'application au JO du 16/04/2026 selon Acteurs Publics [S?]. Données sensibles : cloud interne ou SecNumCloud. Angle mort : les opérateurs de l'État [S?]. | Extension aux collectivités > 30 000 hab. évoquée, non confirmée [S?]. |
| **SecNumCloud** | Arrêté du 12/08/2026 approuvant le référentiel v3.2 [S?, Landot] ; une source tierce indique que la v3.2 date de 2022 : l'arrêté serait l'approbation formelle [S?]. | Divergence de dates à lever. |
| **NIS2 / loi Résilience** | Au 11/11/2026 la loi n'est **pas promulguée** : adoptée au Sénat en mars 2025, discussion à l'Assemblée nationale à partir du 9/11/2026, débats prévus jusqu'au 13/11 ; renvoi devant la CJUE (8 ou 9 juillet 2026 selon les sources) ; collectivités exclues des amendes ; périmètre incertain [S?, [Leto](https://www.leto.legal/news/nis-2-projet-loi-resilience-assemblee-nationale-9-novembre-2026), [Maire-info](https://www.maire-info.com/2026/cybermalveillance/directive-nis-2-deux-ans-retard-un-perimetre-dapplication-toujours-incertain-pour-les-collectivites-art26-31146)]. Une page (Legiscope) affirme l'inverse (adoption en 2025) : contredite par toutes les autres sources, écartée. | **Re-vérifier avant livraison** : l'état a pu changer pendant les débats. Odin doit afficher « obligation anticipée, non en vigueur » et suivre ReCyF (publié le 17/03/2026, non obligatoire) [S?]. |
| **Feuille de route cyber de l'État 2026-2027** | Publiée le 9/04/2026 par l'ANSSI ; homologation prioritaire des SI à enjeux fin 2026, MFA admin 31/12/2026, PSSI de l'État mise à jour au plus tard T1 2027 [S?]. Décomptes divergents (40 actions vs 10 chantiers/100 échéances). EDR/XDR : attesté seulement par un blog. 5 % du budget numérique de chaque ministère à la cybersécurité dès 2027 (communiqué du 17/08/2026) [S?]. | Textes primaires non lus. |
| **PSSIE** | Circulaire 5725/SG du 17/07/2014 ; cadre 2022 : arrêté du 26/10/2022 approuvant l'IGI 1337 [S?]. | Détails de l'arrêté non lus. |
| **AI Act et omnibus IA** | Règlement (UE) 2026/1744 publié au JOUE le 24/07/2026, en vigueur le 27/07/2026 ; haut risque Annexe III reporté au 2/12/2027, Annexe I au 2/08/2028 ; art. 50 (transparence) au 2/08/2026 avec délai au 2/12/2026 pour le marquage 50(2) des systèmes déjà sur le marché [S?, White & Case, Lewis Silkin]. | **Divergence entre notes** : une note décrit l'omnibus comme « accord provisoire du 7 mai 2026, adoption formelle à vérifier », une autre comme en vigueur. Dates à confirmer sur EUR-Lex. |
| **CRA** | Obligations de signalement depuis le 11/09/2026, le reste au 11/12/2027 [S?]. | Pertinence pour l'acheteur public non étudiée. |
| **CSRD** | Omnibus (UE) 2026/470 ; seuils 1 000 salariés et 450 M€ de CA [S?]. | Applicabilité aux entités publiques : [I], non sourcée. |
| **Accessibilité** | Directive EAA applicable depuis le 28/06/2025 ; RGAA 4.1 référence d'audit ; périmètre des documents bureautiques et sanctions (50 000 € vs 300 000 €) incertains ; « décret n° 2026-816 du 24/08/2026 » cité par un seul blog [S?]. | **Ne pas s'appuyer** sans vérification. |
| **Dialogue social** | CSA compétents sur l'organisation des services (art. L.253-1 CGFP) ; l'autorité n'est pas tenue de suivre l'avis [S?]. | Texte imposant la consultation pour un outil d'IA : non confirmé. |
| **Alerte** | Loi du 21/03/2022 (Waserman) ; art. L.135-1 à L.135-4 CGFP ; décret du 3/10/2022 [S]. | Obligations précises de l'employeur public (délais, accusé de réception) à lire dans le décret. |

Non sourcés dans les notes (à traiter comme **[CG] ou lacunes**) : RGS, RGI (publié le 12/05/2009 [S]), DSFR, eIDAS 2, Data Act, SDG, « Dites-le-nous une fois », HDS, loi République numérique, code de la commande publique et seuils, M57, DORA (secteur financier seulement).

### 4.3 Contraintes budgétaires et RH
- **État** : LOLF (mission > programme > BOP > UO, titres 2/3/5, AE/CP, Chorus) [CG] ; plafond d'emplois en ETPT, schéma d'emplois en ETP [S]. P352 supprimé du PLF 2025 (crédits transférés au P129) [S?] ; aucun des 15 documents de politique transversale du PLF 2026 ne porte sur le numérique [S?].
- **Collectivités** : M57, sections, AP/CP, PPI, FCTVA, subventions (DETR/DSIL) [CG, à valider].
- Annualité budgétaire et gels de crédits : contrainte à modéliser dans les scénarios [I].
- Dette technique et obsolescence : voir B4.

### 4.4 Commande publique et souveraineté
Voir D4. Points saillants [S?] : doctrine cloud, SecNumCloud, SILL (et la logique « réemploi d'abord »), dépendance Microsoft/Oracle, contrôle DINUM sur les SaaS. Pondération de la souveraineté à 10-15 % dans les appels d'offres : proposition d'un acheteur (Urssaf), non règle générale [S?].

### 4.5 Gouvernance politique
Instances, avis obligatoires et suivi de recommandations : objets de A2-A4. Le calendrier électoral (présidentielle 2027, etc.) comme jalon de roadmap est une **inférence non sourcée** [I].

### 4.6 Typologie des organismes (gabarits)
Ministère/direction centrale ; opérateur de l'État ; région/département/métropole ; commune/EPCI (souvent via syndicat mutualisé) ; sécurité sociale (COG) ; GHT/hôpital ; université. Odin doit proposer un **mode léger** pour les petites structures sans architecte [I]. Tailles typiques de DSI : non trouvées.

---

## 5. L'axe « contribution de tous + IA »

Exigence : tout le monde (employés, développeurs, chefs de projet, etc.) peut se connecter, partager des rapports ; l'IA comprend et produit.

### 5.1 Types de rapports par rôle (proposition [I], non sourcée, à valider par entretiens)

| Rôle | Rapports/contributions typiques | Structuration |
|---|---|---|
| Agent métier | demande/besoin, signalement d'anomalie, rapport d'activité | faible |
| Développeur | fiche de dette, ADR, RETEX/post-mortem blameless, tickets, rapports CI | forte (natif) |
| Chef de projet | flash report, reste à faire, compte rendu de comité, bilan, fiche risque | moyenne |
| RSSI | audit/pentest, fiche incident, tableau de risques | restreinte |
| DPO | AIPD, registre, avis | contient des données personnelles |
| Architecte | ADR, cartographies, notes de cadrage | moyenne |
| DSI | synthèses de pilotage, notes de décision, présentations | moyenne |
| Élu | consommation de synthèses, demandes de clarification (surtout lecteur) | lecture |

Seul fait sourcé : le guide ANSSI sur l'IA générative vise des publics hétérogènes (développeurs, administrateurs, RSSI, DSI, utilisateurs) [S, [ANSSI 29/04/2024](https://cyber.gouv.fr/sites/default/files/document/Recommandations_de_s%C3%A9curit%C3%A9_pour_un_syst%C3%A8me_d_IA_g%C3%A9n%C3%A9rative.pdf)]. Fréquences et formats réels de l'administration française : non documentés. Un gabarit minimal commun (type, auteur, périmètre, objets SI rattachés, classification, date, statut) est proposé comme ancrage [I].

### 5.2 Cycle de vie et modèle de contribution [I]
- États : brouillon, partagé, validé, publié, archivé, périmé ; péremption par type de rapport, relance automatique.
- Modèle hybride : signaux automatiques (tickets, CI, ITSM) comme base, formulaires courts pour les faits structurés, documents libres pour le narratif, l'IA pré-remplissant les formulaires, **validés par l'auteur**.
- Boucle de retour : montrer au contributeur ce que son rapport a produit ; **pas de classement individuel**.
- Aucune donnée d'adoption ni de gamification n'a été trouvée.

### 5.3 Compréhension par l'IA
- Pipeline conseillé [I] : dépôt, antivirus/hygiène, extraction/OCR, classification, extraction d'entités avec score de confiance, rattachement au référentiel (propositions + correction manuelle), **file de validation humaine**, publication des faits validés. Principe : tout fait extrait reste une proposition tant qu'il n'est pas validé.
- Détection d'écarts (statut « vert » vs signaux techniques) : forte valeur, mais présentée comme « signal à examiner », jamais comme verdict sur une personne [I].
- RAG : citations obligatoires, refus sans source, évaluation continue sur jeu de référence [I].
- Aucune source sur la précision d'extraction ou la qualité du RAG fin 2026 : **ne pas citer de chiffres**.

### 5.4 Production par l'IA [I sauf mention]
Garde-fous : mention « généré par IA » ; chiffres injectés depuis les données, jamais écrits librement ; chaque affirmation liée à sa source ; validation humaine avant diffusion à la direction ou aux élus ; journal de génération (modèle, prompt, sources) ; synthèses par audience à partir des **mêmes faits validés** ; génération par gabarit de l'organisme. Le marché débute par la synthèse de contenus existants (ex. ServiceNow Now Assist for EA : synthèse d'ADR) [S]. Aucune source ne décrit une génération de supports de type COMEX (absence de preuve).

### 5.5 Confidentialité, accès, droits des agents
- **Surveillance des agents** : si Odin évalue des personnes (performance, répartition de tâches, activité), il entrerait dans le champ « haut risque emploi » de l'AI Act (échéance reportée au 2/12/2027 selon l'omnibus, voir §4) [S?/I]. Choix de conception proposé : unité d'analyse = projet/application/équipe, jamais l'individu ; pas de métriques par agent ; noms masqués par défaut [I].
- **Contrôle d'accès** : classification par document (public, interne, diffusion restreinte, sensible RH/sécurité), droits par rôle/périmètre/hiérarchie **appliqués avant la recherche** ; cloisonnement fort des rapports sécurité/RH/disciplinaires ; journalisation des consultations et requêtes IA [I].
- **Données personnelles** : RGPD et AI Act s'appliquent ensemble (fiches CNIL 2024-2025, centrées sur le développement des systèmes, pas leur déploiement) [S] ; pseudonymisation avant IA si le modèle n'est pas en environnement maîtrisé ; AIPD probable ; droit d'accès des agents aux données les concernant [I].
- **Dialogue social** : consultation du CSA/CST (F3SCT) à anticiper ; accord-cadre sur l'IA en négociation avec les syndicats depuis le 16/04/2026, signature visée à l'automne 2026 [S?] ; texte de consultation obligatoire non confirmé.
- **Alerte** : Odin ne doit pas être le canal d'alerte officiel (confidentialité de l'identité, délais légaux) : renvoi vers le dispositif de l'organisme et détection/routage de contenus ressemblant à une alerte [I].

### 5.6 Sécurité des LLM
ANSSI (29/04/2024) : trois catégories d'attaques (manipulation de l'IA, infection du jeu de données, exfiltration) et 35 recommandations ; interdiction des outils d'IA générative publics pour les données sensibles ; protection des données personnelles renvoyée à la CNIL [S]. OWASP Top 10 LLM 2025 : injection de prompt = LLM01, injection indirecte via les documents lus ; pas de prévention infaillible [S?]. Conséquence pour Odin [I] : traiter le contenu déposé comme donnée, jamais comme instruction ; l'IA d'extraction sans outil d'écriture ni accès inter-périmètres ; filtrage des droits avant l'index vectoriel.

### 5.7 Souveraineté de l'IA
Plan « Notre IA » (16/06/2026) généralisant « L'Assistant » (DINUM + Mistral AI), hébergement qualifié SecNumCloud (Outscale) [S?]. **Périmètre et montants divergent** (environ 1 million d'agents, 6 M€ de contrat, 750 000 € de première phase, 10 000 agents testeurs) : ne retenir aucun chiffre ferme. Conditions d'accès pour des organismes hors État : non établies. Les modèles par défaut de Now Assist EA dépendent de clouds extra-européens (Azure OpenAI, etc.), ce qui pose la question SecNumCloud [S]. Option proposée : modèle interchangeable (Assistant/Mistral SecNumCloud ou open-weight on-premise) selon la sensibilité du périmètre [I].

---

## 6. Paysage du marché et manques de marché

### 6.1 Catégories d'outils (chacune avec un « objet pivot »)
| Catégorie | Exemples cités | Pivot (analyse du chercheur [I]) |
|---|---|---|
| EAM/EA | SAP LeanIX, Ardoq, Bizzdesign, BOC ADOIT, Orbus | application / capacité |
| SPM/PPM | Planview, Broadcom Clarity, Bizzdesign Alfabet, ServiceNow SPM, Planisware, Sciforma, Triskell | initiative / ressource |
| ITFM/TBM/FinOps | IBM Apptio, Nicus, MagicOrange | coût |
| GRC/cyber | EGERIE, Tenacy | risque / référentiel |
| ITSM/CMDB | iTop, GLPI | élément de configuration |
| Portails développeurs | Backstage, Port, Cortex, OpsLevel | service logiciel |
| Dette de code | CAST Highlight | dépôt de code |
| Cartographie open source | Mercator | vues ANSSI |

Faits notables [S?] : Gartner MQ EA 2025 (6/10/2025) Leaders : Bizzdesign, Ardoq, BOC, Orbus ; MQ EA 2026 publié le 13/10/2026, liste complète non retrouvée ; MQ SPM 2026 (11/06/2026) : Planview Leader. Les positions de LeanIX, MEGA, ServiceNow, Planisware sont à vérifier. Le méta-modèle LeanIX v4 (12 types de fact sheets) est la référence publique la plus lisible [S]. En 2026, les leaders EA exposent un serveur MCP et un inventaire d'actifs IA [S?] : c'est un attendu, plus un différenciateur. Tailles de marché : EA ~1,2 à 1,7 Md$, SPM/PPM ~5 à 10 Md$ (méthodologies opaques, écarts du simple au double) ; prix non publics, ticket EA de plusieurs dizaines de k$ à plus de 100 k$/an [S?, sources éditeurs/agrégateurs].

### 6.2 Critiques récurrentes [S?]
Charge de maintien de la qualité des données ; complexité et besoin d'intégrateur (SPM) ; reporting dépendant du paramétrage et peu utile à la décision ; coût élevé pour les organisations moyennes. Les avis publics restent globalement élevés (4,2 à 4,8/5) ; les plaintes sont qualitatives et issues d'agrégateurs mêlant leurs sources.

### 6.3 Manques de marché = différenciation possible d'Odin
Tous [I] sauf mention, issus de l'analyse des notes, **non validés par une étude de besoins** :
1. Vue unifiée dette + portefeuille + capacité ETP + risque + finance (aucune catégorie n'est « cœur » sur les quatre à la fois ; matrice du chercheur, appréciation qualitative).
2. **Aide à l'arbitrage** (options, impacts, recommandation) plutôt que restitution.
3. **Production de supports de direction** (absence de preuve dans les sources consultées, à vérifier dans les notes de version 2026 d'Ardoq, LeanIX, Planview, Bizzdesign).
4. Alimentation automatique et indicateur de fraîcheur/fiabilité par donnée.
5. Accessibilité aux organisations de taille moyenne et aux petites collectivités.
6. **Souveraineté/hébergement européen** : l'offre souveraine documentée concerne surtout le cyber (Tenacy, SecNumCloud) et l'open source auto-hébergé (Mercator, GLPI, iTop) ; point non vérifié pour les leaders EA/SPM (hébergement de LeanIX, Ardoq, Bizzdesign, MEGA, Planisware à vérifier).
7. Restitution par rôle sur un référentiel commun (DSI, direction, RSSI, PMO, élus).
8. Pont sécurité ↔ portefeuille et gouvernance de l'IA reliée au budget/capacité/risque.
9. Spécifique public : registre réglementaire daté par profil d'organisme, avis DINUM, LOLF/ETPT/M57, commande publique, suivi des recommandations de la Cour, ingestion de l'open data (Panorama, avis DINUM, SILL, observatoire).
10. Ingestion de documents non structurés de tous profils avec validation humaine et hébergement souverain (ensemble non trouvé dans les offres étudiées).

**Positionnement par rapport à Mercator** : Odin ne doit pas dupliquer la cartographie technique mais s'en servir comme source (import) ; son créneau est la décision stratégique au-dessus de la cartographie [I]. Mercator : GPL, guide ANSSI, utilisé par des hôpitaux et administrations (chiffres auto-déclarés) [S?]. Le volet « fonctions couvertes par Mercator » repose sur la lecture de la documentation, pas sur un test.

Non étudiés : SaaS management, engineering intelligence, OKR, roadmapping produit, Jira Align, MEGA HOPEX (détail), éditeurs de collectivités (Berger-Levrault, Cosoluce, JVS, Ciril), Copilot/Glean/Rovo, Archi/Structurizr/OpenProject/eramba.

---

## 7. Entités métier principales et rôles

### 7.1 Premier modèle conceptuel métier [I]
Synthèse recoupant le méta-modèle LeanIX v4, TBM, MoP/PMI et les notes ; ce n'est **pas** un modèle validé.

| Groupe | Entités | Relations clés |
|---|---|---|
| Organisation | Organisme (profil, tutelle), direction/équipe, entité mutualisatrice/utilisatrice | un organisme a des directions ; une entité mutualisatrice sert N entités |
| Stratégie | Politique publique/mission, objectif, indicateur, cible, mandat/échéance politique | objectif → politique ; initiative → objectif ; indicateur mesure objectif |
| Services | Démarche/service, capacité métier, processus, usager | service réalisé par capacités ; capacité servie par applications |
| Patrimoine | Application, composant technique, interface/flux, objet de données, jeu de données, environnement, actif IA | application dépend de composants ; interface relie 2 applications ; actif IA a un usage |
| Cycle de vie | Version, fin de support, élément de dette, vulnérabilité | dette porte sur application/composant, a un coût et un risque |
| Transformation | Demande, initiative/projet/programme, portefeuille, jalon, dépendance, roadmap (versions, scénarios), bénéfice | demande → initiative ; initiative affecte applications et capacités ; bénéfice rattaché à un objectif |
| Ressources | Poste/ETP (ETP, ETPT, prestataire), personne, compétence, emploi-type, affectation, vacance | affectation lie ressource et initiative/application ; compétence requise par application |
| Finances | Exercice, ligne budgétaire (programme/BOP/UO ou section M57, titre, AE/CP), cost pool, règle d'allocation, scénario budgétaire | dépense imputée sur application/initiative/service |
| Achats | Fournisseur, marché/accord-cadre, commande, licence, clause, plan de sortie | contrat couvre application et fonction critique ; échéance = jalon de roadmap |
| Sécurité/résilience | Risque, mesure/contrôle, décision d'homologation, incident, dérogation, BIA/PCA-PRA | risque porte sur application et service ; homologation couvre un SI |
| Conformité | Obligation (texte, périmètre, date, statut juridique), exigence, statut de conformité, avis, recommandation de contrôle, preuve/audit | obligation s'applique à un type d'organisme ; avis rattaché à un projet |
| Gouvernance | Instance, décision (options, critères, hypothèses), ADR, dérogation | décision porte sur initiative, scénario, application |
| Restitution/contribution | Rapport (type, gabarit, classification, statut, version), contribution, fait extrait (confiance, validation), indicateur de pilotage (source, fraîcheur), tableau de bord, présentation générée (journal de génération) | rapport → faits extraits → objets du référentiel ; présentation cite des faits validés |

Relations transverses : **applicabilité** (obligation/doctrine → périmètre), **traçabilité** (tout fait de pilotage → source → auteur/validateur), **version/baseline** (roadmaps, budgets, référentiels), **classification** (tout objet porte un niveau de confidentialité).

### 7.2 Rôles et profils utilisateurs
Contributeurs : agent métier, développeur, chef de projet, architecte, RSSI, DPO. Décideurs/lecteurs : DSI/DNUM, direction générale, DAF, élu, tutelle, contrôleur de gestion/budgétaire, PMO. Administration : référent Odin par entité, administrateur de référentiels (nomenclatures, seuils), auditeur/lecture seule (corps de contrôle). Droits : par rôle, **périmètre** (entité, direction), et **ligne hiérarchique**, avec cloisonnement des contenus RH/sécurité [I].

---

## 8. Questions ouvertes et prochaines étapes

### 8.0 Décisions actées par l'utilisateur (11 novembre 2026)

| # | Décision | Conséquences métier retenues [I] |
|---|---|---|
| D1 | **Odin évalue des applications et des équipes, pas des personnes** (réponse à la question 1). | Les objets évalués sont l'application, le projet, l'équipe/le service. Aucun indicateur de performance individuelle, aucun classement nominatif. L'IA ne doit pas extraire des rapports un jugement sur une personne nommée : cela devient une règle de conception (filtrage/pseudonymisation des noms, pas d'attribution individuelle). Garde-fou à prévoir : seuil minimal d'effectif pour afficher une métrique d'équipe, car une « équipe » de 1 à 3 personnes équivaut de fait à une évaluation individuelle. |
| D2 | **« Métiers » = profils RH** (réponse à la question 8) : familles et profils de métiers du numérique, compétences. | Le référentiel de profils (nomenclature Cigref, RMFP dans l'État, référentiels CNFPT ; voir axes D1-D2) sert à la **capacité, aux compétences et à la GEPP** (qui sait faire quoi, risque « personne clé » au niveau du rôle/profil). Il ne sert pas à évaluer des individus. Le sens « capacités métier / services publics » reste nécessaire pour relier applications et missions (axes B1-B3), mais sous ce nom-là, pas sous « métiers ». |

**Points de vigilance que ces décisions ne suppriment pas [I, à valider avec le DPO et un juriste]**
- Évaluer des équipes ne garantit pas, à lui seul, que l'AI Act ne qualifie pas le système de « haut risque » dans le domaine de l'emploi : le critère porte sur l'usage (décisions touchant les personnes, suivi ou évaluation de leur performance). Les notes sont partagées sur le calendrier (report à décembre 2027 pour les usages haut risque emploi, adoption formelle à confirmer, voir §9). La conception doit donc **empêcher** tout usage individuel (agrégation, pas de drill-down nominatif, journalisation des requêtes), et cette garantie doit être documentée.
- Des **données de profils RH** (compétences, vacances de poste, dépendance à des rôles clés) restent des données personnelles dès qu'un profil est rattaché à une personne identifiable : travailler au niveau rôle/profil/équipe, minimiser, et prévoir l'AIPD et la consultation des instances (CSA/CST/F3SCT, question 5).
- Un rapport déposé par un agent peut mentionner des personnes (incident, post-mortem) : règle de pseudonymisation et de « blameless » à spécifier (§5.5).

### 8.1 Questions à trancher avec l'utilisateur
**Issues des notes**
1. ~~Odin évalue-t-il des personnes, ou uniquement projets/applications/équipes ?~~ **Tranchée (D1) : applications et équipes.**
2. Quel modèle et quel hébergement (Assistant DINUM, Mistral SecNumCloud, open-weight on-premise) ? Pour quels périmètres sensibles ?
3. Qui valide les faits extraits (auteur, chef de projet, référent SI) ?
4. Quel niveau de classification maximal accepté (exclure ou non rapports sécurité/RH) ?
5. Calendrier CSA/CST/F3SCT et AIPD ; DPO impliqué dès la conception.
6. Cible : organismes de l'État uniquement, ou collectivités/opérateurs/hôpitaux aussi ?
7. Intégrer le canal d'alerte interne ou seulement y renvoyer ?

**Complémentaires (jugées nécessaires)**
8. ~~« Métiers » dans la liste initiale : capacités métier ou profils RH ?~~ **Tranchée (D2) : profils RH.**
9. Un client = un organisme, ou une structure mutualisatrice avec des dizaines de membres (multi-entités, refacturation) ?
10. Périmètre de la finance : suivi budgétaire de la DSI uniquement, ou consolidation de la dépense numérique de toute l'organisation (réponse à la Cour) ?
11. Niveau de précision attendu en ressources : planification par rôle/compétence (conseillée) ou nominative ?
12. Odin est-il une source de vérité ou un agrégateur (import de Mercator, Chorus, SIRH, ITSM, Jira/GitLab) ? Quelles sources de données sont accessibles ?
13. Quels textes réglementaires sont à porter au premier lot (liste priorisée) et qui assure la veille juridique ?
14. Quelle part de rapports « sensibles » (diffusion restreinte, secret professionnel) est acceptable ?
15. Valeur publique : quelle grille de critères (service rendu, équité, continuité, souveraineté, ROI) et qui la valide ?
16. Odin doit-il fonctionner en mode déconnecté (réseaux restreints) ?
17. Licence et diffusion visées (inscription au SILL, open source) : décision stratégique à clarifier.

### 8.2 Prochaines étapes suggérées pour la spécification (métier uniquement)
1. Valider avec l'utilisateur la liste des axes et leur priorité (§3), trancher les questions 6 et 9 (les questions 1 et 8 sont tranchées, voir §8.0).
2. Entretiens avec 5 à 8 profils (DSI, RSSI, chef de projet, développeur, DAF, agent métier, DPO, élu) pour documenter les rapports réels, fréquences et formats (lacune §5.1).
3. Constituer un registre réglementaire initial avec **sources primaires** (Légifrance, EUR-Lex, ANSSI, DINUM), statut juridique et date de vérification pour chaque texte (§9).
4. Spécifier le modèle conceptuel métier (§7) : glossaire, cardinalités, règles de gestion ; définir précisément ETP/ETPT/prestataire et la hiérarchie d'imputation budgétaire.
5. Rédiger les user stories par domaine, en commençant par le socle (patrimoine, finances, demande/portefeuille, décisions) puis conformité/sécurité, puis contribution + IA.
6. Définir les règles de gouvernance de la contribution et de l'IA (classification, validation humaine, droits des agents) avec DPO, juriste et représentants du personnel.
7. Compléter la veille concurrentielle (§6, non étudiés) et vérifier les affirmations de manque de marché.
8. Établir un jeu d'indicateurs minimal par audience (peu nombreux, liés à des décisions, au vu des constats FIPECO et du « reporting qui n'aide pas à décider »).

---

## 9. Limites de la recherche et points à vérifier

### 9.1 Limites générales
- Les notes reposent sur 9 à 18 recherches web chacune ; la plupart des sources sont des résultats de recherche résumés, de la presse spécialisée, des blogs d'éditeurs ou des agrégateurs d'avis ; **aucun texte primaire** (Légifrance, JOUE, rapports de la Cour des comptes, PAP) n'a été lu en intégralité. Plusieurs hôtes étaient bloqués (catalogue.numerique.gouv.fr) ou non exploitables (Légifrance via l'outil).
- Les rapports Gartner/Forrester, PMI, AXELOS, Cigref, ISO 38500, COBIT sont payants : seules des citations d'éditeurs ou de tiers ont été obtenues.
- Les sections « typologie des rapports », « modèles de contribution », « roadmaps », « note de décision », « présentation aux élus » reposent surtout sur des inférences.
- Les marqueurs [CG] (LOLF, M57, 6R, EBIOS RM, etc.) sont de la connaissance générale non re-vérifiée.

### 9.2 Divergences et points précis à vérifier avant de s'appuyer dessus

| # | Point | Divergence / risque |
|---|---|---|
| 1 | Seuil d'avis DINUM | 9 M€ vs 15 M€ ; date/numéro du décret de mars 2026 ; seuil SaaS (2 M€/an) ; « corrigé par LMI » |
| 2 | Loi Résilience / NIS2 | statut au 13/11/2026 ou après ; date de saisine de la CJUE (8 ou 9 juillet) ; périmètre collectivités ; plafonds de sanctions ; page Legiscope contredite |
| 3 | AI Act et omnibus | « accord provisoire » vs « en vigueur depuis le 27/07/2026 » ; dates Annexe III (2/12/2027), art. 50 ; adoption formelle ; art. 4 littératie |
| 4 | SecNumCloud 3.2 | arrêté du 12/08/2026 vs version de 2022 |
| 5 | Cloud au centre | date de la mise à jour 2023 (25 ou 31 mai) ; décret SREN du 16/04/2026 ; extension aux collectivités |
| 6 | Réorganisation DINUM | « Autorité numérique de l'État » ; fusion DINUM/DITP « Ariane » ; dates contradictoires |
| 7 | Feuille de route cyber État | décompte (40 actions vs 10 chantiers/100 échéances) ; EDR/XDR non confirmé ; 5 % du budget numérique |
| 8 | Plan « Notre IA » / Assistant | périmètre (1 million d'agents), montants, hébergement, statut en novembre 2026, bilan d'été 2026 |
| 9 | Chiffres Panorama | 48 projets/3,6 Md€ vs 54 projets/4 Md€ ; fichier open data jugé incomplet ; dates |
| 10 | Observatoire des démarches | nombre de critères (5, 8, 11) ; nom actuel ; Service-Public+ non documenté |
| 11 | Nomenclature Cigref | 52 vs 54 métiers ; édition 2025 ; version de la nomenclature de coûts |
| 12 | RGAA / EAA / décret 2026-816 | périmètre des documents bureautiques ; sanctions ; décret cité par un seul blog |
| 13 | Cour des comptes (octobre 2026, bureautique, dépendance Microsoft) | relayé par presse, lien primaire non vérifié |
| 14 | SILL | ~530 logiciels (2025) ; chiffre 2026 non obtenu |
| 15 | RGESN / REEN | attribution Arcep vs DINUM ; obligation REEN d'une source commerciale |
| 16 | COBIT 2019 | répartition EDM 5/APO 14/BAI 11/DSS 6/MEA 4 (un site isole 6/3) ; ISO 38500 : principes 2024 non obtenus |
| 17 | Gartner MQ 2026 | liste des Leaders EA/SPM 2026 ; positions LeanIX, MEGA, ServiceNow, Planisware |
| 18 | Chiffres de marché et de prix | écarts du simple au double ; témoignages isolés (91 k$/an pour 300 applications) |
| 19 | Rachats d'éditeurs (LeanIX/SAP, Apptio/IBM, etc.) | connaissance générale, non vérifiés |
| 20 | Chiffres presse divers | Louvois (150-200 M€), ONP (346 M€), 37 % de non-conformité cloud, 83 % de marché américain, Broadcom (+800 à 1 500 %), 29 % de gaspillage cloud : tous secondaires |
| 21 | Texte précis CSA/CST pour un outil IA | non confirmé ; décret du 3/10/2022 non lu |
| 22 | OWASP LLM | édition 2026 « existerait » (non vérifié) |

### 9.3 Lacunes de recherche (non couvert ou couvert sans sources)
- **Textes** : RGS, RGI (version actuelle), PSSIE détaillée, RGAA/DSFR/PDF-UA, HDS, IGI 1300/II 901 (diffusion restreinte), eIDAS 2, Data Act, Data Governance Act, SDG, loi République numérique, RGPD (registre, AIPD), DORA (texte), NIS2 (texte), code de la commande publique (seuils, durées), M57/AP-CP/FCTVA, LOLF (textes).
- **Acteurs et organismes** : collectivités (peu), sécurité sociale (CNAM/CNAF/UCANSS, COG), santé hors cyber, universités, opérateurs (COP/COM), contrôleurs budgétaires (CBCM) ; contenu type d'un SDSI/schéma directeur ; composition réelle des comités ; CRC/IGA/IGF/CNIL.
- **Pratiques** : plan de charge en ETP en France, ratios internes/externes, turnover IT, « bus factor », gestion de la demande métier dans le public, absorption du changement, conduite du changement, shadow IT public, SAM/audits éditeurs, refacturation interne, réalisation des bénéfices (aucune statistique fiable), ratios financiers (IT en % du CA, run/build : non sourcés), ADR/TOGAF/ArchiMate/Club URBA-EA, doctrines étrangères (UK GDS, Estonie, Danemark), AHP/options réelles dans le SI public.
- **IA** : précision d'extraction, RAG interne et surveillance des agents (CNIL), guides ANSSI 2025-2026 sur agents/RAG, NIST AI RMF, ISO/IEC 42001, guide DINUM juin 2026 (non lu), statut de l'Assistant hors État, génération de supports COMEX par les éditeurs.
- **Marché** : SaaS management, engineering intelligence, OKR, roadmapping produit, GRC généralistes (ServiceNow IRM, Archer), Copilot/Glean/Rovo, offres des éditeurs de collectivités, tout équivalent open source d'un EAM orienté décision ; avis utilisateurs pour MEGA, ADOIT, Orbus, Apptio, EGERIE, Tenacy, Planisware, Sciforma ; aucune étude quantifiant les besoins des DSI.
- **Interfaces** : « Mon Suivi Grands Projets » (aucune trace), LASUITE numérique ; connecteurs Chorus, SIRH, ITSM (non sourcés).

---

## Annexe : sources principales citées dans les notes (échantillon, regroupées)

- **Cadres publics numériques** : [data.gouv.fr, avis DINUM](https://www.data.gouv.fr/fr/datasets/publication-des-avis-dinum-articles-3-et-7/) ; [Démarche DINUM](https://demarche.numerique.gouv.fr/commencer/demande-d-avis-conforme-dinum) ; [Circulaire 6282-SG](https://www.transformation.gouv.fr/files/presse/Circulaire-n6282-SG-5072021-doctrineuutilisation-informatique-en-nuage-Etat.pdf) ; [LMI, contrats SaaS](https://www.lemondeinformatique.fr/actualites/lireamp-les-contrats-saas-des-ministeres-sous-surveillance-de-la-dinum-99748.html) ; [SILL, data.gouv.fr](https://www.data.gouv.fr/fr/datasets/socle-interministeriel-de-logiciels-libres/) ; [Panorama grands projets, data.gouv.fr](https://www.data.gouv.fr/fr/datasets/panorama-des-grands-projets-numeriques-de-letat/).
- **Dette, budget, contrôle** : [Cour des comptes via Solutions Numériques](https://www.solutions-numeriques.com/?p=228889) ; [Acteurs Publics, le RUN](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/) ; [IGF, COM DGFiP](https://www.igf.finances.gouv.fr/files/live/sites/igf/files/contributed/Rapports%20de%20mission/2022/2022-M-034-05_Rapport_COM_DGFIP.pdf) ; [Assemblée nationale, ETPT](https://www.assemblee-nationale.fr/13/pdf/cr-mec/10-11/c1011020.pdf) ; [PAP 2026](https://www.assemblee-nationale.fr/dyn/dyn/contenu/visualisation/1087966/file/PAP2026_BG_Direction_action_du_Gouvernement_DC.pdf) ; [Vie-publique, grands projets numériques](https://www.vie-publique.fr/rapport/276699-la-conduite-des-grands-projets-numeriques-de-l-etat).
- **Sécurité et conformité** : [Leto, loi Résilience](https://www.leto.legal/news/nis-2-projet-loi-resilience-assemblee-nationale-9-novembre-2026) ; [Maire-info, NIS2 collectivités](https://www.maire-info.com/2026/cybermalveillance/directive-nis-2-deux-ans-retard-un-perimetre-dapplication-toujours-incertain-pour-les-collectivites-art26-31146) ; [ANSSI, feuille de route 2026-2027](https://cyber.gouv.fr/actualites/feuille-de-route-des-efforts-prioritaires-en-matiere-de-securite-numerique-de-letat-2026-2027) ; [Landot, SecNumCloud](https://blog.landot-avocats.net/2026/08/17/important-notamment-pour-certains-marches-publics-evolution-du-referentiel-dexigences-relatif-aux-prestataires-de-services-dinformatique-en-nuage/amp/) ; [Guide d'homologation ANSSI 04/2025](https://messervices.cyber.gouv.fr/documents-guides/guide-homologation-securite-web-04-2025.pdf) ; [Mercator, GitHub](https://www.github.com/dbarzin/mercator).
- **IA et protection des agents** : [ANSSI, IA générative](https://cyber.gouv.fr/sites/default/files/document/Recommandations_de_s%C3%A9curit%C3%A9_pour_un_syst%C3%A8me_d_IA_g%C3%A9n%C3%A9rative.pdf) ; [White & Case, omnibus IA](https://www.whitecase.com/insight-alert/eu-ai-omnibus-enters-force-amending-ai-act) ; [Lewis Silkin](https://www.lewissilkin.com/insights/2026/07/27/the-digital-omnibus-on-ai-enters-into-force-today) ; [CNIL, développement IA](https://cnil.fr/fr/developpement-des-systemes-dia-les-recommandations-de-la-cnil-pour-respecter-le-rgpd) ; [Vie-publique, loi Waserman](https://www.vie-publique.fr/loi/282472-loi-21-mars-2022-waserman-protection-des-lanceurs-dalerte) ; [Banque des Territoires, plan Notre IA](https://www.banquedesterritoires.fr/avec-le-plan-notre-ia-letat-accelere-sur-le-deploiement-des-outils-et-la-gouvernance) ; [ActuIA, Mistral](https://www.actuia.com/en/news/mistral-ai-in-ministries-what-the-state-buys-for-eur6m/).
- **Gouvernance et référentiels** : [ISO 38500](https://www.iso.org/standard/81684.html) ; [MAGNum 2026](https://docs.ifaci.com/wp-content/uploads/2026/02/MAGNum-2026-Cigref-IFACI-ISACA-France-VDEF.pdf) ; [TBM Council](https://www.tbmcouncil.org/taxonomy) ; [PMI](https://www.pmi.org/pmbok-guide-standards/foundational/standard-for-portfolio-management) ; [mop.wiki](https://mop.wiki/management-cycles/) ; [circulaire 6434/SG](https://www.fonction-publique.gouv.fr/files/files/actualites/circulaire_numero_6434-sg_referentiel_numerique.pdf).
- **Marché** : [SAP LeanIX, méta-modèle](https://docs-eam.leanix.net/docs/meta-model) ; [Ardoq, Gartner 2025](https://www.ardoq.com/news/gartner-magic-quadrant-2025) ; [Planview, MQ SPM 2026](https://secure.businesswire.com/news/home/20260616691154/en/Planview-Again-Named-by-Gartner-as-a-Leader-in-Strategic-Portfolio-Management) ; [ServiceNow, Now Assist EA](https://www.servicenow.com/docs/r/application-portfolio-management/enterprise-architecture/now-assist-ea.html) ; [Tenacy](https://tenacy.io/p/webinar-management-cyber) ; [communauté LeanIX, qualité des données](https://community.leanix.net/the-americas-user-group-47/navigating-data-quality-challenges-in-leanix-726).
