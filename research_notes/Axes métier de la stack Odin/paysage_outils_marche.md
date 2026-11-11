# Paysage des outils de pilotage stratégique du SI et couverture fonctionnelle (benchmark marché, état novembre 2026)

> Avertissement de méthode. Recherche menée par requêtes web (résumés de résultats, pas de lecture intégrale des rapports Gartner/Forrester, qui sont payants). Les « Cited Findings » sont sourcés ; beaucoup de sources sont des pages éditeurs ou des agrégateurs d'avis (rfp.wiki, SelectHub, PeerSpot, Appvizer) : elles sont signalées. Les rubriques « Inferences » relèvent de l'analyse du chercheur (y compris connaissance générale du marché non re-vérifiée lors de cette session) et doivent être lues comme telles. Plusieurs catégories demandées n'ont pas pu être documentées par des sources dans le budget imparti : elles figurent explicitement en « Gaps ».

## 1. Quelles catégories d'outils couvrent le pilotage stratégique du SI, et que fait chacune ?

### Takeaway
Le pilotage stratégique du SI est éclaté en une dizaine de catégories d'outils dont chacune possède un « objet pivot » (l'application pour l'EAM, le projet/investissement pour le SPM, le coût pour le TBM, le risque/contrôle pour le GRC, le CI pour la CMDB, le service logiciel pour les portails développeurs, le code pour les outils de dette). Les recouvrements augmentent (ServiceNow réunit SPM + EA + CMDB ; Bizzdesign réunit EA + SPM via Alfabet ; IBM réunit ITFM + FinOps + SPM), mais aucune catégorie ne couvre seule l'ensemble dette + portefeuille + capacité + risque + finance.

### Cited Findings

**EAM / EA tools (SAP LeanIX, Ardoq, Bizzdesign, BOC ADOIT, OrbusInfinity, MEGA HOPEX, Alfabet…)**
- Leaders du Magic Quadrant Gartner EA Tools 2025 (publié le 6 octobre 2025) confirmés par leurs propres communiqués : Bizzdesign (18e année), Ardoq (5e année), BOC Group, Orbus Software (4e année). SAP LeanIX est cité comme Leader le mieux placé par une source secondaire (post LinkedIn) seulement. GBTEC entre comme Challenger. — [Bizzdesign](https://bizzdesign.com/press-releases/bizzdesign-recognized-leader-2025-gartnerr-magic-quadranttm-enterprise-architecture) ; [Ardoq](https://www.ardoq.com/news/gartner-magic-quadrant-2025) ; [BOC Group](https://tools.prnewswire.com/en-us/live/20823/release/20251007EN91164) ; [Orbus](https://www.orbussoftware.com/company/newsroom/orbus-software-leader-2025-gartner-magic-quadrant-for-enterprise-architecture-tools) ; [GBTEC](https://www.gbtec.com/company/news-article/gbtec-recognized-as-a-challenger-in-2025-gartner-magic-quadrant-for-enterprise-architecture-tools/)
- Une édition 2026 du MQ EA Tools existe (publiée le 13 octobre 2026) ; Bizzdesign y est Leader pour la 19e année. La liste complète des Leaders 2026 n'a pas été retrouvée. Un rapport Critical Capabilities associé est daté du 5 novembre 2026. — [Gartner, abstract](https://www.gartner.com/en/documents/8502677) ; [IT Brief UK](https://itbrief.co.uk/story/bizzdesign-named-gartner-leader-for-19th-straight-year) ; [Gartner Critical Capabilities](https://www.gartner.com/doc/8597237)
- Cas d'usage évalués par Gartner (Critical Capabilities 2025) et revendiqués par Ardoq : « Enterprise Transformation », « Portfolio Management » (classé n°1) et « Advanced Roadmapping » (n°2). — [Ardoq](https://www.ardoq.com/blog/leader-gartner-magic-quadrant-ea-2025)
- Avis d'utilisateur/agrégateur : SAP LeanIX excelle en gestion de portefeuille applicatif et visualisation, mais offre des capacités de modélisation moins complètes que les plateformes EA traditionnelles. — [fitgap](https://us.fitgap.com/products/sap-leanix)

**SPM / PPM (Planview, Broadcom Clarity, Bizzdesign Alfabet, ServiceNow SPM, Planisware, Sciforma, Triskell, Shibumi…)**
- Leaders du MQ Gartner SPM 2025 (publié le 4 août 2025) : Bizzdesign (Alfabet), Broadcom (Clarity), Planview. Planview déclare le meilleur score sur les 3 cas d'usage. — [Planview](https://www.businesswire.com/news/home/20250807268238/en/Planview-Again-Named-by-Gartner-as-a-Leader-in-Strategic-Portfolio-Management) ; [itdesign/Clarity](https://clarity.itdesign.de/en/blog/news/clarity-leader-in-gartner-magic-quadrant-2025-for-strategic-portfolio-management/)
- MQ SPM 2026 publié le 11 juin 2026 : Planview Leader pour la 5e année, placé le plus haut en exécution et le plus loin en vision, 1er sur les trois cas d'usage Critical Capabilities. Shibumi inclus (6e année). ServiceNow et Broadcom Clarity ne sont cités comme Leaders 2026 que par un blog tiers (ONES), non vérifié ; la position de Planisware n'a pas été trouvée. — [Planview](https://secure.businesswire.com/news/home/20260616691154/en/Planview-Again-Named-by-Gartner-as-a-Leader-in-Strategic-Portfolio-Management) ; [Shibumi](https://shibumi.com/blog/shibumi-included-in-the-2026-gartner-magic-quadrant-for-strategic-portfolio-management-for-the-sixth-consecutive-year/) ; [ONES (non vérifié)](https://ones.com/blog/?p=1071524)
- Planisware (éditeur français) : priorisation des projets, planification des ressources et des capacités, suivi budgets/plannings/livrables, reporting, simulation de scénarios d'investissement, agents IA ; environ 650 organisations clientes selon un comparateur. — [La Fabrique du Net](https://www.lafabriquedunet.fr/logiciel/planisware) ; [Appvizer](https://www.appvizer.fr/operations/ppm/planisware)
- Planisware (affirmation éditeur) : la prévision capacitaire compare la charge attendue aux ressources disponibles sur tout le portefeuille ; des scénarios « what-if » testent des changements d'affectation. — [Planisware, guide 2026](https://fr.planisware.com/ressources/gestion-des-ressources-capacity-planning/guide-2026-outils-spm-planification-capacites-staffing-temps)
- Triskell : simulation de scénarios (ajout d'un projet et effet sur ressources et budget), gestion capacitaire, méthodes agile / cycle en V / hybride. — [Appvizer](https://www.appvizer.fr/operations/ppm/triskell)
- Sciforma : gestion des idées et de la demande, planification, gestion des ressources, suivi des temps, capacités, budgétisation. — [Appvizer](https://www.appvizer.fr/operations/ppm/sciforma) ; [Capterra](https://www.capterra.fr/reviews/18756/sciforma)

**ServiceNow (SPM + EA/APM + CMDB)**
- Le produit « Application Portfolio Management » a été renommé « Enterprise Architecture » à la release Xanadu ; l'Enterprise Architecture Workspace centralise les capacités ; le portail affiche carte hiérarchique des capacités métier, vue applications, portefeuille technologique et indicateurs clés. Abonnement séparé requis. — [ServiceNow docs](https://www.servicenow.com/docs/r/yokohama/application-portfolio-management/explore-apm.html)
- Capacités SPM listées : Strategy Mapping et Roadmapping, Value Tracking and Measurement, Enterprise Architecture Management ; planification stratégique par « lentille » capacité métier ou application. — [SoftwareReviews](https://www.softwarereviews.com/products/servicenow-strategic-portfolio-management) ; [ServiceNow docs, scenario planning](https://www.servicenow.com/docs/r/zurich/it-business-management/scenario-planning-in-spw/better-together-with-other-apps-spw.html)

**TBM / ITFM / FinOps (IBM Apptio, Nicus, MagicOrange)**
- Gamme IBM Apptio (octobre 2026) : IBM Apptio (ITFM), IBM Cloudability (FinOps cloud), IBM Kubecost (coûts Kubernetes), IBM Targetprocess (SPM). Source : blog d'un concurrent (Finout), recoupé par le site Apptio. — [Finout](https://www.finout.io/blog/8-apptio-competitors-to-know-in-2026) ; [Apptio](https://www.apptio.com/products/)
- IBM Apptio est annoncé Leader de la Forrester Wave IT Financial Management Software Q2 2026 ; IBM a annoncé « IBM Apptio AI Value & ROI » le 6 août 2026. — [Apptio](https://apptio.com/)
- Nicus : plateforme ITFM/TBM, sur Nicus Cloud ou nativement sur ServiceNow. MagicOrange : modèle de coûts ITFM/TBM/FinOps avec refacturation (chargeback) et prévisions. — [Finout](https://www.finout.io/blog/8-apptio-competitors-to-know-in-2026)

**GRC / pilotage cyber (EGERIE, Tenacy)**
- Tenacy (ex-AugmentedCISO, français, créé en 2019) : SaaS de pilotage de la cybersécurité ; modélisation de 40+ référentiels publics et de référentiels privés (PSSI), catalogue de 200 indicateurs pour tableaux de bord, catalogue unifié de mesures pour la multi-conformité ; hébergement dédié et SecNumCloud possibles ; levée de 6 M€ en 2024 orientée NIS 2. — [Tenacy](https://tenacy.io/p/webinar-management-cyber) ; [Maddyness](https://www.maddyness.com/2024/01/15/tenacy-leve-6-millions-deuros-pour-accelerer-la-mise-en-conformite-nis-2/) ; [Journal des Entreprises](https://www.lejournaldesentreprises.com/article/tenacy-veut-devenir-un-leader-europeen-de-la-cybersecurite-2080584)
- EGERIE (français) : plateforme collaborative de gouvernance, pilotage et conformité des risques cyber et de protection des données personnelles (Risk Manager, Privacy Manager) ; évaluation du niveau de sécurité des sous-traitants/fournisseurs ; intégration de la sécurité dans les projets. — [Solutions Numériques](https://www.solutions-numeriques.com/fiche/egerie) ; [EGERIE CISO](https://cybersecurity.egerie.eu/en/ciso) ; [EGERIE, cas d'usage projets](https://egerie.eu/en/infosec-mag-integrating-cybersecurity-into-projects/)

**ITSM / CMDB (iTop, GLPI)**
- iTop (Combodo, français) : plateforme open source ITSM + CMDB alignée ITIL ; édition Community gratuite, offres supérieures sur devis ; CMDB et processus de changement dans le même système ; personnalisation low-code ; auto-hébergé ou SaaS. — [La Fabrique du Net](https://www.lafabriquedunet.fr/logiciel/itop) ; [europeanpurpose](https://europeanpurpose.com/tool/itop)
- GLPI (Teclib) : suite de gestion IT, projets, finances et utilisateurs ; on-premise ou SaaS ; open source GPL. — [SourceForge comparatif](https://www.sourceforge.net/software/compare/GLPi-vs-ITOP)

**Portails développeurs internes / scorecards (Backstage, Port, Cortex, OpsLevel)**
- Backstage est le framework open source ; Port, Cortex et OpsLevel sont des portails SaaS managés. Les scorecards sont le cœur de Cortex et OpsLevel (maturité de service, ownership) ; Port est l'option low-code à modèle de données flexible. Backstage exige un effort dédié d'ingénierie plateforme. Prix non publiés/peu fiables (ordres de grandeur cités : ~20 à 35 $/développeur/mois, non vérifiés). Sources en grande partie rédigées par les éditeurs concurrents. — [Roadie](https://roadie.io/blog/backstage-alternatives/) ; [Cortex](https://www.cortex.io/post/port-alternatives) ; [OpsLevel](https://www.opslevel.com/resources/port-vs-cortex-whats-the-best-internal-developer-portal) ; [wetheflywheel](https://wetheflywheel.com/en/comparisons/backstage-vs-port-vs-cortex/)

**Outils de dette technique / software intelligence (CAST Highlight)**
- CAST Highlight : SaaS analysant le code source à l'échelle du portefeuille : santé logicielle, dette technique, maturité/blocages cloud (recommandations AWS/Azure/GCP, score de conteneurisation, estimation de l'effort de refactoring), risques open source, SCA et génération de SBOM, coûts et durabilité (« green »). La priorisation de la dette croise criticité métier et densité de dette. — [CAST Highlight](https://casthighlight.com) ; [CAST capabilities](https://www.castsoftware.com/highlight/capabilities) ; [appsecsanta](https://appsecsanta.com/cast-highlight)
- Limite rapportée : chaque portefeuille nécessite son propre abonnement, ce qui complique la gouvernance multi-entités. Prix : par application et par paliers, « à partir de 39 000 $/an » selon une source, « 27 k$/an » (offre Cloud Insights) selon une place de marché ; chiffres d'agrégateurs possiblement périmés. — [rfp.wiki](https://www.rfp.wiki/sustainability-esg/green-software-engineering/cast-highlight) ; [AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-rjrikuvzqawl6)

### Inferences
- Lecture par « objet pivot » (analyse du chercheur) : EAM = application / capacité métier ; SPM = initiative / investissement / ressource ; TBM = coût / tour de coûts / service ; GRC = risque / contrôle / référentiel ; CMDB = élément de configuration ; IDP = service logiciel / équipe propriétaire ; outils de dette = dépôt de code. Un outil intégré orienté décision doit relier ces pivots plutôt que les redéfinir.
- Trois mouvements de convergence ressortent des sources : (a) EA + SPM (Bizzdesign-Alfabet présent dans les deux MQ ; ServiceNow liste l'EA comme capacité de SPM) ; (b) ITFM + FinOps + SPM (gamme IBM Apptio) ; (c) dette de code remontée au niveau portefeuille (CAST Highlight). La convergence GRC/cyber avec le portefeuille reste marginale (EGERIE ne l'aborde que par « sécurité dans les projets »).

### Gaps
- Non documenté par des sources lors de cette session (budget de recherche atteint) : SaaS management (Zylo, Torii), engineering intelligence (LinearB, Jellyfish, Swarmia), OKR (Perdoo, Quantive/WorkBoard), roadmapping produit (Aha!, Productboard, Roadmunk), GRC généralistes (ServiceNow IRM, Archer), Jira Align, Avolution ABACUS, MEGA HOPEX (détail des modules), SonarQube, vFunction, Stepsize. Ces catégories sont traitées uniquement dans la matrice finale, au titre de l'analyse du chercheur.
- Liste complète des Leaders des MQ 2026 (EA et SPM) non obtenue ; positions de SAP LeanIX, MEGA, ServiceNow, Planisware à vérifier dans les rapports Gartner.
- Rachats à vérifier (non retrouvés dans les sources de cette session, issus de la connaissance générale) : LeanIX par SAP (2023), Apptio par IBM (2023), rapprochement Bizzdesign / Alfabet / MEGA, Quantive par WorkBoard. Seule l'« intégration de l'activité Alfabet » chez Bizzdesign est attestée par les sources consultées ([itdesign](https://clarity.itdesign.de/en/blog/news/clarity-leader-in-gartner-magic-quadrant-2025-for-strategic-portfolio-management/)).

## 2. Quels cas d'usage, modules et méta-modèles publics chez les leaders EAM et SPM ?

### Takeaway
Le méta-modèle LeanIX v4 (12 types de fact sheets en 4 couches) est la référence publique la plus lisible et fournit une liste d'objets directement réutilisable. Les leaders EAM convergent vers les mêmes cas d'usage : portefeuille applicatif, cartographie des capacités métier, risque technologique/obsolescence, feuilles de route de transformation ; les leaders SPM ajoutent demande, priorisation, capacité, budgets et scénarios.

### Cited Findings
- Méta-modèle SAP LeanIX v4 : 12 types de fact sheets. Stratégie et transformation : Objective, Platform, Initiative. Architecture métier : Organization, Business Capability, Business Context. Architecture applicative et données : Application, Interface, Data Object. Architecture technique : IT Component, Tech Category, Provider. — [SAP LeanIX docs, Meta Model](https://docs-eam.leanix.net/docs/meta-model)
- Évolution v3 → v4 : User Group → Organization, Project → Initiative, Process → Business Context ; ajout du type Platform. — [SAP LeanIX docs, Delta to v3](https://docs-eam.leanix.net/docs/delta-to-meta-model-v3)
- Les administrateurs peuvent créer, supprimer et réordonner des types de fact sheets personnalisés ; l'éditeur recommande de se faire accompagner avant de personnaliser. — [SAP LeanIX docs, Custom Fact Sheet Types](https://docs-eam.leanix.net/docs/custom-fact-sheet-types)
- Extension « AI governance » LeanIX : sous-types de fact sheets pour agents IA, applications, serveurs MCP et modèles d'IA ; attributs d'usage, de risque et de potentiel ; collection de rapports, KPI pour le tableau de bord exécutif d'architecture, calcul automatique de la valeur métier des agents. — [SAP LeanIX updates](https://updates.leanix.net/announcements/ann_Cfi5Rf9QFCfiJ)
- Mécanismes de qualité de données LeanIX mentionnés par les utilisateurs : complétude des fact sheets, enquêtes (surveys), « Quality Seal ». — [Communauté LeanIX](https://community.leanix.net/the-americas-user-group-47/navigating-data-quality-challenges-in-leanix-726)
- ServiceNow EA : carte hiérarchique des capacités, vue applications, portefeuille technologique ; release « Australia » : agent de requête EA en langage naturel et « Architecture Analyzer » pour l'exploration visuelle. — [ServiceNow release notes](https://www.servicenow.com/docs/r/australia/release-notes/enterprise-architecture-rn.html)
- Ardoq : cas d'usage Portfolio Management, Enterprise Transformation, Advanced Roadmapping (classements Gartner revendiqués par l'éditeur). — [Ardoq](https://www.ardoq.com/blog/leader-gartner-magic-quadrant-ea-2025)
- Mercator (open source) : vues du guide ANSSI — écosystème (entités, fournisseurs), métier (processus), applications, administration (annuaires, comptes à privilèges), infrastructure logique, infrastructure physique ; rapport de cartographie, niveaux de maturité, suivi des changements sur 12 mois. — [LinuxFr](https://linuxfr.org/news/mercator-cartographie-de-si-open-source) ; [Slides SSTIC 2023](https://www.sstic.org/media/SSTIC2023/SSTIC-actes/mercator_-_la_cartographie_des_systmes_dinformatio/SSTIC2023-Slides-mercator_-_la_cartographie_des_systmes_dinformation-barzin.pdf)

### Inferences
- Objets candidats pour le méta-modèle Odin, par recoupement (analyse du chercheur) : Objectif, Initiative/Projet, Organisation/Équipe, Capacité métier, Processus/Contexte métier, Application, Interface/Flux, Objet de données, Composant technique (avec cycle de vie), Catégorie technique, Fournisseur/Contrat, Plateforme ; à compléter par les objets absents du modèle LeanIX mais présents dans les autres catégories : Ressource/ETP et compétence (SPM), Poste de coût/budget (TBM), Risque, Contrôle/mesure de sécurité, Exigence/référentiel (GRC), Élément de dette, Décision d'architecture, Actif IA (agent, modèle, serveur MCP).
- Le méta-modèle LeanIX ne porte nativement ni la capacité en ETP ni le risque cyber structuré : ce sont précisément les axes « ressources » et « sécurité » déjà identifiés pour Odin, ce qui confirme qu'ils ne sont pas couverts par un outil EAM seul.

### Gaps
- Méta-modèles publics d'Ardoq, Bizzdesign (ArchiMate), MEGA HOPEX, ADOIT, Planview et Planisware non consultés.
- Liste détaillée des modules produit de LeanIX (APM, Technology Risk and Compliance, Architecture and Road Map Planning) non re-vérifiée sur les pages produit lors de cette session.
- Aucune documentation retrouvée sur une fonction d'« architecture decision records » chez LeanIX.

## 3. Quelles nouveautés 2025-2026 (IA, agents, MCP, gouvernance de l'IA) ?

### Takeaway
En 2026, tous les leaders EA exposent leur référentiel aux assistants IA via un serveur MCP et ajoutent un inventaire/gouvernance des actifs IA (agents, modèles, serveurs MCP) ; les leaders SPM et ITFM ajoutent des agents IA et la mesure de la valeur de l'IA. Ce sont désormais des attendus de marché, et non plus des différenciateurs.

### Cited Findings
- SAP LeanIX : serveur MCP utilisé par plus de 200 clients (chiffre éditeur) ; « MCP apps » annoncées le 3 juin 2026, affichant fact sheets, cartes de relations, rapports et tableaux de bord dans Claude ou Microsoft Copilot. — [SAP LeanIX, Sapphire](https://www.leanix.net/en/blog/leanix-at-sapphire)
- SAP AI Agent Hub : inventaire des agents, LLM et serveurs MCP, rattachés aux capacités et aux propriétaires ; « AI Governance Assistant » intégrant EU AI Act et NIST pour classer automatiquement les risques (affirmation de communiqué, disponibilité à vérifier). — [SAP News](https://news.sap.com/2025/11/leanix-signavio-walkme-sap-transformation-excellence-summit/) ; [Futurum](https://futurumgroup.com/?p=95960)
- LeanIX : configuration par l'administrateur du mode de vérification de chaque type d'actif IA avant mise en production. — [SAP LeanIX updates](https://updates.leanix.net/announcements/ann_NgnZHcpWeOwWH)
- Ardoq : relance « AI-first » au T2 2026 (communiqué du 28 mai 2026) ; « agentic AI workforce » (architectes virtuels) ; serveur MCP d'abord en préversion en lecture seule (2025), puis capacité d'alimenter le référentiel via assistant IA et MCP ; SSO MCP via OAuth ; agents personnalisés en bêta ouverte avec les partenaires, déploiement clients annoncé pour le T3 2026. — [Ardoq, communiqué](https://www.businesswire.com/news/home/20260528712753/en/Ardoq-Launches-AI-First-Enterprise-Architecture-Platform) ; [Ardoq, agentic workforce](https://www.ardoq.com/blog/new-agentic-ai-workforce-spring-2026) ; [Ardoq, MCP](https://www.ardoq.com/blog/ea-ai-mcp)
- Bizzdesign : positionne son serveur MCP (blog de janvier 2026) comme exposition de l'entreprise en « intelligence structurée interrogeable », avec gouvernance embarquée, parcours multi-sauts entre couches et introspection de schéma. Un comparatif d'un concurrent le classe « annoncé » plutôt que disponible (non vérifié). — [Bizzdesign](https://bizzdesign.com/blog/model-context-protocol-mcp-turning-enterprise-architecture-ai-ready-intelligence) ; [Albumi (concurrent)](https://albumi-website.pages.dev/guides/ai-enterprise-architecture)
- ServiceNow EA (release Australia) : agent de requête en langage naturel sur le portefeuille. — [ServiceNow release notes](https://www.servicenow.com/docs/r/australia/release-notes/enterprise-architecture-rn.html)
- Gartner : les capacités d'IA deviennent un facteur déterminant de sélection des outils EA, pour leur promesse de productivité de la fonction EA. — [Gartner Critical Capabilities, abstract](https://www.gartner.com/doc/7021698)
- IBM Apptio « AI Value & ROI » (6 août 2026) ; Planisware met en avant des agents IA. — [Apptio](https://apptio.com/) ; [La Fabrique du Net](https://www.lafabriquedunet.fr/logiciel/planisware)
- Découverte automatique : la précision des cycles de vie dépend d'alimentations automatiques (CMDB/ServiceNow) ; les composants de niche ou spécifiques demandent un enrichissement manuel. — [rfp.wiki, Ardoq vs LeanIX](https://www.rfp.wiki/it-security/enterprise-architecture-tools/ardoq/leanix)

### Inferences
- Pour Odin, un serveur MCP / une API interrogeable en langage naturel et un inventaire des actifs IA (avec classification EU AI Act) sont à considérer comme axes de base. La différenciation se situe plutôt dans ce que l'IA produit pour le décideur (arbitrages, supports) que dans la simple interrogation du référentiel.
- L'« AI governance » fait apparaître un nouvel axe métier absent de la liste initiale de l'utilisateur : inventaire et gouvernance des usages d'IA (agents, modèles, risques, valeur).

### Gaps
- Génération automatique de rapports, diagrammes et présentations : aucune source consultée ne décrit précisément une génération de supports de type COMEX ; seules des mentions générales (« diagram templates », rapports dans le chat MCP) ont été trouvées.
- Nouveautés IA 2025-2026 de Planview, MEGA HOPEX, BOC ADOIT, Orbus, EGERIE et Tenacy non documentées.

## 4. Quelles critiques et limites récurrentes selon les utilisateurs ?

### Takeaway
Les critiques documentées convergent sur quatre points : effort de maintien de la qualité des données (EA), complexité et coût de mise en œuvre (SPM, surtout ServiceNow), reporting dépendant du paramétrage et aidant peu la décision, prix prohibitif pour les organisations de taille moyenne. Les avis publics restent toutefois globalement élevés (4,2 à 4,8/5) : les plaintes viennent des commentaires qualitatifs.

### Cited Findings
- Qualité des données (EA) : un utilisateur de la communauté LeanIX écrit que la plupart ont connu des difficultés à maintenir la qualité des données malgré complétude, enquêtes et Quality Seal, et qu'il est difficile de motiver les parties prenantes à maintenir leurs données ; un autre juge les scores de complétude insuffisants. — [Communauté LeanIX (Amériques)](https://community.leanix.net/the-americas-user-group-47/navigating-data-quality-challenges-in-leanix-726) ; [Communauté LeanIX (DACH)](https://community.leanix.net/dach-user-group-45/how-to-ensure-data-quality-in-leanix-and-having-a-good-governance-established-224)
- Gartner Peer Insights liste parmi les axes d'amélioration de LeanIX l'effort requis pour maintenir la qualité des données et l'intégrité du référentiel. — [Gartner Peer Insights](https://www.gartner.com/reviews/product/leanix-enterprise-architecture/alternatives)
- Synthèse d'avis : la plateforme LeanIX est la plus forte quand la gouvernance des données est disciplinée ; la précision des cycles de vie d'Ardoq faiblit sans flux automatisés ; risque de verrouillage éditeur signalé pour Ardoq (sans détail). — [rfp.wiki LeanIX](https://www.rfp.wiki/vendors/leanix) ; [rfp.wiki Ardoq](https://www.rfp.wiki/vendors/ardoq)
- Complexité : les outils EA sont critiqués pour leur complexité, même s'ils s'améliorent (TechTarget) ; selon Ardoq (source éditeur), beaucoup d'outils EA ont été conçus comme outils de conception de solutions, centrés sur la visualisation, inadaptés à des besoins d'information plus larges. — [TechTarget](https://techtarget.com/searchapparchitecture/news/252521534/Ardoq-Discover-boosts-enterprise-architecture-tool-usability) ; [Ardoq](https://www.ardoq.com/blog/enterprise-architecture-tool-three-new-challenges)
- Coût (EA) : le positionnement haut de gamme de SAP LeanIX peut être prohibitif pour les organisations de taille moyenne ; un avis PeerSpot le juge cher pour les fonctionnalités offertes, un autre le juge compétitif (avis partagés). — [fitgap](https://us.fitgap.com/products/sap-leanix) ; [PeerSpot](https://www.peerspot.com/questions/what-is-your-experience-regarding-pricing-and-costs-for-leanix)
- ServiceNow SPM : un avis Gartner Peer Insights cite comme principal défaut la complexité et l'effort de paramétrage initial, et note qu'un reporting pertinent dépend fortement de la configuration et de la qualité des données ; un avis PeerSpot estime que le reporting temps réel aide peu la décision ; des utilisateurs trouvent le reporting limité ; le premier déploiement requiert généralement un partenaire certifié ou une équipe dédiée ; pas de prix public. — [Gartner Peer Insights](https://external.pi.gpi.aws.gartner.com/reviews/product/servicenow-strategic-portfolio-management) ; [PeerSpot](https://www.peerspot.com/products/servicenow-it-business-management-reviews?company_size=A) ; [SelectHub](https://www.selecthub.com/p/ppm-software/servicenow-spm/) ; [rfp.wiki](https://www.rfp.wiki/project-management/servicenow-strategic-portfolio-management)
- Planview : interface dense, navigation complexe, courbe d'apprentissage ; coût et licences constituant une barrière pour les petites organisations ; reporting jugé solide pour les vues exécutives standard, mais demande de davantage d'analyse en libre-service. Notes agrégées contradictoires (4,4 sur 61 avis contre 4,2 sur 654). — [rfp.wiki Planview](https://www.rfp.wiki/project-management/planview)
- Triskell : le moteur de règles paramétrables est cité comme point à améliorer. — [GetApp](https://www.getapp.fr/software/104053/triskell-ppm)
- Portails développeurs : Backstage demande un investissement d'ingénierie dédié ; l'interface de Cortex a une courbe d'apprentissage pour les non-techniciens. — [Roadie](https://roadie.io/blog/backstage-alternatives/) ; [wetheflywheel](https://wetheflywheel.com/en/comparisons/backstage-vs-port-vs-cortex/)
- Notes de référence : Ardoq 4,8/5 (232 avis) et LeanIX 4,7/5 (475 notes) sur Gartner Peer Insights ; ServiceNow EA 4,4/5 (47 avis) sur G2. — [Gartner Peer Insights](https://www.gartner.com/reviews/market/enterprise-architecture-tools/compare/product/ardoq-vs-leanix-enterprise-architecture) ; [G2](https://www.g2.com/products/servicenow-enterprise-architecture/reviews)

### Inferences
- La charge de saisie et la péremption des données sont le premier facteur d'échec rapporté pour les référentiels EA : un nouvel outil devrait privilégier l'alimentation automatique (CMDB, SSO, dépôts de code, outils projet, finance) et afficher la fraîcheur/fiabilité de chaque donnée, plutôt que de s'en remettre au « crowdsourcing ».
- Le reproche « le reporting n'aide pas à décider » (ServiceNow SPM) et la demande de libre-service (Planview) désignent un besoin distinct du tableau de bord : formuler des arbitrages (options, impacts, recommandation).
- L'adoption faible hors architectes et les silos EA/PPM/finance/sécurité sont cohérents avec les constats ci-dessus (difficulté à mobiliser les parties prenantes, outils nés de la conception de solutions), mais n'ont pas été établis par une source directe dans cette session.

### Gaps
- Aucun fil Reddit (r/EnterpriseArchitecture, r/ITManagers) n'a pu être récupéré : deux requêtes n'ont renvoyé que des contenus éditeurs et des agrégateurs.
- Aucun retour d'expérience Cigref ou Club URBA-EA retrouvé.
- Pas d'avis utilisateurs documentés pour MEGA HOPEX, ADOIT, Orbus, Apptio, EGERIE, Tenacy, Planisware et Sciforma.
- Les agrégateurs (rfp.wiki, SelectHub) mélangent leurs sources : les constats sont directionnels, non quantifiés.

## 5. Quelles alternatives open source ou légères, et quel périmètre ?

### Takeaway
Les alternatives open source couvrent chacune une tranche étroite (cartographie pour Mercator, ITSM/CMDB pour iTop et GLPI, catalogue de services pour Backstage). Aucune source consultée ne décrit d'équivalent open source d'un EAM orienté portefeuille et décision.

### Cited Findings
- Mercator (Didier Barzin, GPL, Laravel/PHP) : cartographie du SI selon le guide ANSSI, alignée NIS 2 et ISO 27001 ; vues écosystème, métier, applications, administration, infrastructures logique et physique ; génération de représentations graphiques, rapport de cartographie, niveaux de maturité, suivi des changements ; utilisateurs cités dans le secteur hospitalier et les administrations ; plus de 500 étoiles GitHub et déploiement dans plus de 30 pays selon LinuxFr (chiffres à actualiser) ; fork référencé par la DSI de l'Université Rennes 2 sur code.gouv.fr. — [GitHub dbarzin/mercator](https://www.github.com/dbarzin/mercator) ; [LinuxFr](https://linuxfr.org/news/mercator-cartographie-de-si-open-source) ; [code.gouv.fr](https://data.code.gouv.fr/hosts/GitHub/repositories/DSI-Universite-Rennes2%2Fmercator)
- iTop : ITSM + CMDB open source aligné ITIL, édition Community gratuite, auto-hébergeable. GLPI : gestion de parc, projets, finances, open source GPL, on-premise ou SaaS. — [La Fabrique du Net](https://www.lafabriquedunet.fr/logiciel/itop) ; [SourceForge](https://www.sourceforge.net/software/compare/GLPi-vs-ITOP)
- Backstage : framework open source de portail développeur (catalogue logiciel), au prix d'un effort d'ingénierie plateforme dédié. — [Roadie](https://roadie.io/blog/backstage-alternatives/)
- Outils EA gratuits ou abordables cités : Revelation EA (gratuit, navigateur, pour équipes qui démarrent une fonction EA) ; ADOIT décrit comme option abordable pour les entreprises de taille moyenne. Sources de type listicles, faible fiabilité. — [G2, catégorie EA](https://g2.com/categories/enterprise-architecture-tools?page=2) ; [CloudEagle](https://www.cloudeagle.ai/blogs/best-leanix-alternatives-for-enterprise-architecture-management)

### Inferences
- Mercator est l'alternative la plus pertinente pour un public français (ANSSI, NIS 2, hôpitaux, administrations), mais son périmètre est la cartographie à finalité sécurité : pas de portefeuille de projets, de capacité, de finance ni de scénarios d'après les sources consultées.
- Un assemblage open source (Mercator + GLPI/iTop + outil projet) reproduit les silos reprochés aux suites commerciales, sans couche de consolidation décisionnelle.

### Gaps
- Non documentés lors de cette session : Archi (ArchiMate), Structurizr, OpenProject, Dependency-Track, eramba (une requête n'a rien renvoyé sur eramba), ainsi que tout projet « LeanIX-like » open source.
- État actuel (2026) du dépôt Mercator (étoiles, version, feuille de route) non vérifié directement.

## 6. Quels ordres de grandeur de prix et de taille de marché ?

### Takeaway
Le marché des outils EA est petit (environ 1,2 à 1,7 Md$ en 2025, croissance de 4,5 à 8 % par an), celui du SPM/PPM plusieurs fois plus grand (environ 5 à 10 Md$, croissance de 9 à 13 %). Les prix ne sont pas publics ; pour l'EA, la tarification à l'application place le ticket d'entrée à plusieurs dizaines de milliers de dollars par an.

### Cited Findings
- Marché des outils EA en 2025 : 1,23 Md$ (Fortune Business Insights), 1,17 Md$ (Spherical Insights), d'autres cabinets à 1,35, 1,6 ou 1,7 Md$ ; écarts dus aux périmètres (services inclus ou non). — [Fortune Business Insights](https://www.fortunebusinessinsights.com/enterprise-architecture-tools-market-116613) ; [Spherical Insights](https://www.sphericalinsights.com/reports/enterprise-architecture-tools-market) ; [Kings Research](https://www.kingsresearch.com/report/enterprise-architecture-tools-market-2612)
- Marché SPM en 2025 : 4,82 Md$ (9,47 Md$ en 2033, TCAC 8,9 %) selon un cabinet ; 6,82 Md$ (16,34 Md$ en 2035, TCAC 9,7 %) selon un autre. Marché PPM élargi : 8,64 Md$ en 2025 et 17,75 Md$ en 2031, TCAC 12,6 % (MarketsandMarkets) ; 10,05 Md$ en 2025, TCAC 11,46 % (Fortune Business Insights). — [DataHorizzon](https://datahorizzonresearch.com/strategic-portfolio-management-software-market-72994) ; [Custom Market Insights](https://www.custommarketinsights.com/press-releases/strategic-portfolio-management-market-size/) ; [MarketsandMarkets](https://www.marketsandmarkets.com/Market-Reports/project-portfolio-management-software-market-225932595.html) ; [Fortune Business Insights](https://www.fortunebusinessinsights.com/project-portfolio-management-software-market-116676)
- SAP LeanIX : prix « sur demande, par an » ; licence fondée sur le nombre d'applications ; un utilisateur rapporte 91 000 $/an pour 300 applications. — [G2 pricing](https://www.g2.com/products/leanix-enterprise-architecture-management/pricing) ; [PeerSpot](https://www.peerspot.com/questions/what-is-your-experience-regarding-pricing-and-costs-for-leanix)
- Ardoq : tarification au nombre d'applications gérées, utilisateurs illimités, pas de prix public. Le benchmark publié par Ardoq (source éditeur) situe un outil EA entre 50 et 100 k$/an pour une grande entreprise (1 000+ applications). — [Ardoq plans](https://ardoq.com/plans) ; [Ardoq, pricing breakdown 2025](https://www.ardoq.com/blog/enterprise-architecture-cost-in-2025)
- ServiceNow SPM : pas de prix catalogue, devis obligatoire, coût de mise en œuvre tiré par la complexité. — [rfp.wiki](https://www.rfp.wiki/project-management/servicenow-strategic-portfolio-management)
- CAST Highlight : par application, à partir d'environ 27 à 39 k$/an selon les sources. — [AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-rjrikuvzqawl6)
- iTop : édition Community gratuite ; GLPI : open source gratuit. — [europeanpurpose](https://europeanpurpose.com/tool/itop)

### Inferences
- Le chiffre de 91 k$/an pour 300 applications (un seul témoignage) est supérieur à la fourchette publiée par Ardoq pour 1 000+ applications : les deux sources ne sont pas cohérentes ; retenir « plusieurs dizaines de milliers à plus de 100 k$/an » comme ordre de grandeur, hors intégration.
- Une ETI gérant 100 à 300 applications fait face à un ticket annuel difficile à justifier pour un seul des silos (EA), alors qu'il lui faudrait en plus un outil SPM, un ITFM et un GRC : c'est l'argument économique d'un outil intégré et accessible.

### Gaps
- Aucun benchmark Vendr ni prix catalogue pour Planview, Planisware, Sciforma, Triskell, Apptio, EGERIE et Tenacy.
- Tailles de marché TBM/ITFM, GRC et portails développeurs non recherchées.
- Les chiffres de cabinets d'études de marché sont peu fiables (méthodologies opaques, écarts du simple au double).

## 7. Synthèse : axes transverses et besoins mal servis

### Takeaway
Par recoupement, une vingtaine d'axes fonctionnels reviennent dans les outils du marché ; les axes absents de la liste initiale de l'utilisateur sont notamment le patrimoine applicatif et technologique, les capacités métier, la finance SI, la demande et la priorisation, les fournisseurs/contrats, les données, la conformité, la gouvernance de l'IA, la qualité des données du référentiel et les scénarios. Les manques les plus nets sont la vue unifiée multi-domaines, l'aide à l'arbitrage, la production de supports de direction et l'accessibilité pour les organisations de taille moyenne.

### Cited Findings
- Axes attestés par les sources, avec leur catégorie d'origine : portefeuille applicatif, capacités métier, objectifs, initiatives, organisation, données, interfaces, composants techniques et fournisseurs (méta-modèle LeanIX) — [SAP LeanIX docs](https://docs-eam.leanix.net/docs/meta-model) ; demande, priorisation, capacité/ressources, budgets, temps passés, scénarios (Planisware, Sciforma, Triskell) — [La Fabrique du Net](https://www.lafabriquedunet.fr/logiciel/planisware), [Capterra](https://www.capterra.fr/reviews/18756/sciforma) ; mesure de la valeur et roadmapping stratégique (ServiceNow SPM) — [SoftwareReviews](https://www.softwarereviews.com/products/servicenow-strategic-portfolio-management) ; coûts, refacturation, prévisions, FinOps (Apptio, MagicOrange) — [Finout](https://www.finout.io/blog/8-apptio-competitors-to-know-in-2026) ; risques cyber, multi-conformité, indicateurs sécurité, risque fournisseurs, données personnelles (Tenacy, EGERIE) — [Tenacy](https://tenacy.io/p/webinar-management-cyber), [EGERIE](https://cybersecurity.egerie.eu/en/ciso) ; dette technique, préparation cloud, risques open source/SBOM, durabilité (CAST Highlight) — [CAST Highlight](https://casthighlight.com) ; maturité de service et ownership (Cortex, OpsLevel) — [OpsLevel](https://www.opslevel.com/resources/port-vs-cortex-whats-the-best-internal-developer-portal) ; inventaire et gouvernance des actifs IA (LeanIX) — [SAP LeanIX updates](https://updates.leanix.net/announcements/ann_Cfi5Rf9QFCfiJ) ; cartographie multi-vues et maturité (Mercator) — [LinuxFr](https://linuxfr.org/news/mercator-cartographie-de-si-open-source).
- Manques attestés : maintien de la qualité des données et mobilisation des contributeurs — [Communauté LeanIX](https://community.leanix.net/the-americas-user-group-47/navigating-data-quality-challenges-in-leanix-726) ; reporting aidant peu la décision et dépendant du paramétrage — [PeerSpot](https://www.peerspot.com/products/servicenow-it-business-management-reviews?company_size=A), [Gartner Peer Insights](https://external.pi.gpi.aws.gartner.com/reviews/product/servicenow-strategic-portfolio-management) ; prix prohibitif pour les organisations de taille moyenne — [fitgap](https://us.fitgap.com/products/sap-leanix), [rfp.wiki Planview](https://www.rfp.wiki/project-management/planview) ; complexité de mise en œuvre nécessitant un intégrateur — [rfp.wiki ServiceNow SPM](https://www.rfp.wiki/project-management/servicenow-strategic-portfolio-management).
- Souveraineté : Tenacy propose hébergement dédié et SecNumCloud ; iTop, GLPI et Mercator sont auto-hébergeables. — [Tenacy](https://tenacy.io/p/webinar-management-cyber) ; [europeanpurpose](https://europeanpurpose.com/tool/itop) ; [GitHub Mercator](https://www.github.com/dbarzin/mercator)

### Inferences

**Liste consolidée des axes fonctionnels (analyse du chercheur ; « + » = absent de la liste initiale de l'utilisateur)**
1. Stratégie et objectifs (OKR, alignement initiatives ↔ objectifs) — déjà identifié
2. + Capacités métier et processus (cartes de capacités, alignement SI ↔ métier) — précise l'axe « métiers »
3. + Patrimoine applicatif (inventaire, cycle de vie, rationalisation de type TIME/6R, propriétaires)
4. + Patrimoine technologique et obsolescence (composants, fin de support, standards technologiques)
5. Dette technique (code, architecture, obsolescence ; priorisation par criticité métier) — déjà identifié
6. + Données et flux (objets de données, interfaces, dépendances, analyse d'impact)
7. Feuilles de route et transformation (trajectoires, jalons, dépendances) — déjà identifié
8. + Demande et priorisation (collecte des demandes, scoring, arbitrage de portefeuille)
9. Portefeuille de projets/initiatives (avancement, santé, bénéfices, valeur) — partiellement couvert par « roadmaps »
10. Ressources et capacité (ETP, compétences, charge/capacité, staffing) — déjà identifié
11. + Finance SI (budgets, CAPEX/OPEX, coût par application/service, refacturation, FinOps, licences SaaS)
12. + Fournisseurs et contrats (dépendance, échéances, risque tiers)
13. Sécurité et risques cyber (analyses de risques, mesures, indicateurs) — déjà identifié
14. + Conformité réglementaire (NIS 2, DORA, RGPD, ISO 27001, EU AI Act ; multi-référentiels, audits)
15. + Continuité et criticité (criticité métier des applications, dépendances, résilience)
16. + Gouvernance de l'IA (inventaire agents/modèles/serveurs MCP, risques, valeur)
17. + Maturité d'ingénierie et de service (scorecards, ownership, indicateurs de delivery)
18. + Scénarios et simulation (what-if sur portefeuille, capacité, budget, trajectoire)
19. Reporting et tableaux de bord — déjà identifié
20. Rapports et présentations (supports de comités de direction) — déjà identifié
21. + Qualité, fraîcheur et gouvernance des données du référentiel (complétude, propriétaires, alimentation automatique, intégrations)
22. + Décisions et gouvernance d'architecture (traçabilité des décisions, principes, exceptions)
23. + Durabilité / numérique responsable (empreinte, « green »)
24. + Interrogation en langage naturel et ouverture (API, MCP)

**Matrice axe fonctionnel × catégorie d'outil** (appréciation du chercheur : ●  cœur de la catégorie, ◐ partiel/optionnel, vide = absent ou marginal. Les colonnes SaaS mgmt, Eng. intel., OKR et Roadmap produit reposent sur la connaissance générale, sans source consultée dans cette session.)

| Axe | EAM | SPM/PPM | TBM/ITFM/FinOps | GRC/cyber | ITSM/CMDB | SaaS mgmt | IDP/scorecards | Eng. intel. | OKR | Dette (code) | Roadmap produit | Carto. open source (Mercator) |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stratégie et objectifs | ◐ | ● | | | | | | | ● | | ◐ | |
| Capacités métier et processus | ● | ◐ | | ◐ | | | | | | | | ◐ |
| Patrimoine applicatif | ● | ◐ | ◐ | ◐ | ◐ | ◐ | ◐ | | | ◐ | | ● |
| Patrimoine technologique / obsolescence | ● | | | ◐ | ● | | ◐ | | | ◐ | | ● |
| Dette technique | ◐ | | | | | | ◐ | ◐ | | ● | | |
| Données et flux | ● | | | ◐ | ◐ | | ◐ | | | | | ● |
| Feuilles de route / transformation | ● | ● | | | | | | | | | ● | |
| Demande et priorisation | | ● | | | ◐ | | | | | | ● | |
| Portefeuille projets / valeur | ◐ | ● | ◐ | | | | | | ◐ | | | |
| Ressources et capacité (ETP) | | ● | ◐ | | | | | ◐ | | | | |
| Finance SI | ◐ | ● | ● | | ◐ | ● | | | | | | |
| Fournisseurs et contrats | ◐ | | ◐ | ● | ◐ | ● | | | | | | ◐ |
| Sécurité et risques cyber | ◐ | | | ● | ◐ | ◐ | ◐ | | | ◐ | | ◐ |
| Conformité réglementaire | ◐ | | | ● | | ◐ | ◐ | | | ◐ | | ◐ |
| Continuité / criticité | ◐ | | | ● | ◐ | | | | | | | ◐ |
| Gouvernance de l'IA | ● | | ◐ | ◐ | | ◐ | | | | | | |
| Maturité d'ingénierie / service | | | | | | | ● | ● | | ◐ | | |
| Scénarios / simulation | ◐ | ● | ◐ | | | | | | | | | |
| Reporting / tableaux de bord | ● | ● | ● | ● | ◐ | ● | ● | ● | ● | ● | ◐ | ◐ |
| Rapports / présentations de direction | ◐ | ◐ | ◐ | ◐ | | | | | | | ◐ | ◐ |
| Qualité des données du référentiel | ◐ | | | | ◐ | | ◐ | | | | | |
| Décisions d'architecture | ◐ | | | | | | ◐ | | | | | |
| Durabilité | ◐ | | ◐ | | | | | | | ◐ | | |
| Langage naturel / API / MCP | ● | ◐ | ◐ | | ◐ | | ◐ | | | | | |

Lecture : aucune colonne n'est « ● » à la fois sur dette, capacité ETP, finance et risque cyber ; les lignes « Rapports/présentations de direction », « Qualité des données » et « Décisions d'architecture » ne sont le cœur d'aucune catégorie.

**Besoins mal couverts / opportunités de différenciation pour Odin (analyse du chercheur, appuyée sur les constats cités)**
1. Vue unifiée dette + portefeuille + capacité ETP + risque + finance : chaque catégorie possède son objet pivot ; les convergences observées restent partielles (EA + SPM, ITFM + SPM) et excluent le risque cyber et la dette de code.
2. Aide à l'arbitrage plutôt que restitution : le reporting des outils SPM est jugé peu utile à la décision et dépendant du paramétrage ; les scénarios existent en SPM (projets, ressources, budget) mais pas en croisant dette, risque et capacité.
3. Production de supports de direction (COMEX, comités d'investissement) : aucune source consultée ne décrit de génération de présentations/rapports prêts à l'emploi ; c'est le cœur d'aucune catégorie.
4. Charge de saisie et fraîcheur des données : premier irritant documenté côté EA ; opportunité d'alimentation automatique et d'un indicateur explicite de confiance/fraîcheur par donnée.
5. Accessibilité ETI/PME : tarifs à l'application de plusieurs dizaines de k$/an pour un seul silo, déploiements SPM nécessitant un intégrateur ; les options légères ou gratuites ne couvrent qu'une tranche.
6. Souveraineté / hébergement européen : les leaders EA et SPM sont majoritairement des SaaS d'éditeurs américains ou rattachés à de grands groupes ; côté français/européen, l'offre souveraine documentée concerne surtout le cyber (Tenacy, SecNumCloud) et l'open source auto-hébergé (Mercator, GLPI, iTop), pas le pilotage stratégique intégré.
7. Public non architecte : les outils EA sont issus de la modélisation ; DSI, direction, RSSI et PMO utilisent chacun un outil distinct ; une restitution par rôle sur un référentiel commun n'est le cœur d'aucune catégorie.
8. Pont sécurité ↔ portefeuille : la sécurité dans les projets et le risque porté par les applications obsolètes sont traités dans des outils séparés (GRC d'un côté, EA/SPM de l'autre).
9. Gouvernance de l'IA reliée au reste : l'inventaire des actifs IA apparaît dans l'EA en 2026, mais son lien avec budget, capacité et risque reste à construire.

### Gaps
- La matrice est une appréciation qualitative du chercheur, non une donnée sourcée cellule par cellule ; les colonnes SaaS management, engineering intelligence, OKR et roadmapping produit n'ont fait l'objet d'aucune recherche dans cette session.
- Le manque de souveraineté chez les leaders EA/SPM (point 6) n'a pas été vérifié : une requête dédiée n'a rien renvoyé sur les options d'hébergement européen ou souverain des outils EA. Les localisations d'hébergement de LeanIX, Ardoq, Bizzdesign, MEGA et Planisware restent à vérifier.
- L'absence de génération de supports COMEX (point 3) est une absence de preuve dans les sources consultées, pas une preuve d'absence : à vérifier sur les notes de version 2026 d'Ardoq, LeanIX, Planview et Bizzdesign.
- Aucune étude quantifiant les besoins des DSI d'ETI (Cigref, Gartner) n'a été consultée pour hiérarchiser ces manques.
