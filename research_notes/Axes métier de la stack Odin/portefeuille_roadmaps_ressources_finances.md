# Portefeuille, roadmaps, capacité/ressources (ETP) et pilotage financier de la DSI — axes métier pour Odin

> Convention de lecture. Les « Cited Findings » sont sourcés par une recherche web faite le 11/11/2026. Les « Inferences » regroupent (a) mes déductions et (b) des connaissances de métier courantes que je n'ai PAS re-vérifiées sur une source pendant cette recherche : elles sont marquées **[non sourcé]** et doivent être traitées comme telles par le rédacteur. Beaucoup de sources primaires (Gartner, PMI, AXELOS, Avasant, Cigref payant) sont derrière paywall : je n'ai eu accès qu'à des résumés ou à des pages tierces, c'est signalé au cas par cas.

## 1. PPM et SPM : cycle demande → qualification → business case → priorisation → arbitrage → suivi → bilan ; méthodes de priorisation

### Takeaway
Le marché est passé du PPM (suivi de projets) au SPM (Gartner) : relier la stratégie d'entreprise à un portefeuille d'options qui concentre des ressources finies. Les référentiels (PMI, MoP, SAFe LPM) convergent sur les mêmes blocs : alignement stratégique, gouvernance, capacité, valeur/bénéfices, risque, finances ; les méthodes de scoring (WSJF, RICE) ne sont que l'outil de classement à l'intérieur de ce cadre.

### Cited Findings
- Définition Gartner du SPM telle que citée par des pages éditeurs : « a set of business capabilities, processes and supporting portfolio management technology to create a portfolio of strategic options that focus an organization's finite resources to execute the enterprise-wide business strategy ». Le marché SPM couvre des applications cloud et on-premises de planification et d'exécution stratégiques à l'échelle de l'entreprise. Formulation rapportée par des tiers, à confirmer sur le rapport Gartner. — [Planview blog](https://blog.planview.com/?p=24915) ; [Clarity/itdesign](https://clarity.itdesign.de/en/blog/news/clarity-leader-in-gartner-magic-quadrant-2025-for-strategic-portfolio-management/)
- Magic Quadrant SPM 2025 : publié le 4 août 2025 (ID G00818813) ; trois Leaders seulement : Bizzdesign (Alfabet), Broadcom (Clarity), Planview. Le fait qu'un outil d'architecture d'entreprise (Alfabet) soit Leader du SPM est notable pour Odin. — [Gartner, abstract](https://www.gartner.com/en/documents/6807234) ; [Business Wire / Planview](https://www.businesswire.com/news/home/20250807268238/en/Planview-Again-Named-by-Gartner-as-a-Leader-in-Strategic-Portfolio-Management) ; [Alfabet](https://alfabet.com/resources/analyst-reports/see-how-strategic-portfolio-management-spm-platforms-stack-up)
- PMI, *Standard for Portfolio Management*, 4e édition (2017, 189 pages), fondé sur des principes et indépendant du mode de delivery. Chapitres listés : cycle de vie du portefeuille, management stratégique, gouvernance, **gestion de la capacité et des capabilités**, engagement des parties prenantes, **gestion de la valeur**, gestion des risques. — [PMI](https://www.pmi.org/pmbok-guide-standards/foundational/standard-for-portfolio-management) ; [IPG, table des matières](https://www.ipgbook.com/the-standard-for-portfolio-management-products-9781628251975.php)
- AXELOS MoP (Management of Portfolios) : deux cycles liés. Cycle de **définition** (5 pratiques, plutôt séquentielles) dont les sorties sont la *stratégie de portefeuille* et le *plan de livraison* (calendrier, jalons, risques, coûts, ressources). Cycle de **livraison** (pratiques menées en parallèle) : contrôle de gestion, gestion des bénéfices, gestion financière, gestion des risques, engagement des parties prenantes, gouvernance organisationnelle, gestion des ressources. Documents clés : stratégie de portefeuille, plan de livraison, plan de réalisation des bénéfices, tableau de bord, planning des ressources. Sources = wiki et organisme de formation, pas le manuel officiel. — [mop.wiki, cycles](https://mop.wiki/management-cycles/) ; [mop.wiki, documents clés](https://mop.wiki/key-documents/) ; [QA](https://info.qa.com/PBPMOPF)
- SAFe Lean Portfolio Management : le *participatory budgeting* est un processus collaboratif d'allocation du budget du portefeuille aux chaînes de valeur (value streams). Les *Lean budget guardrails* fixent les règles de budgétisation, de dépense et de gouvernance ; l'allocation de capacité est le 2e garde-fou ; les Epics de portefeuille peuvent agir comme une « taxe » transverse sur le financement des value streams. — [Scaled Agile, participatory budgeting](https://scaledagileframework.com/participatory-budgeting-understanding-color-of-money-and-other-constraints) ; [SAFe v5, guardrails](https://v5.scaledagileframework.com/?p=43915)
- WSJF (SAFe) : coût du retard relatif divisé par la durée/taille relative du travail. Entrées du coût du retard : valeur utilisateur et métier, criticité temporelle, réduction de risque et/ou ouverture d'opportunité. — [Scaled Agile, WSJF](https://framework.scaledagile.com/wsjf)
- Articulation capacité/WSJF : l'allocation de capacité fixe un pourcentage par type de travail, et WSJF classe à l'intérieur de chaque enveloppe, ce qui évite de comparer des natures de travail hétérogènes ; pas de formule de répartition universelle. Source = guide d'étude tiers. — [open-exam-prep](https://open-exam-prep.com/study-guides/safe-popm/ch04-prioritization-kanban/capacity-allocation)
- RICE (Intercom, Sean McBride) : score = (Reach × Impact × Confidence) / Effort. Impact sur échelle 3 / 2 / 1 / 0,5 / 0,25 ; confiance en pourcentages discrets ; effort en personnes-mois (0,5 en dessous d'un mois). — [Intercom](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/)

### Inferences
- Axe « Portefeuille (projets/produits/initiatives) » pour Odin :
  - **Définition** : ensemble des investissements de changement du SI, gérés comme un tout pour maximiser la contribution aux objectifs sous contrainte de budget, de capacité et de risque.
  - **Objets métier** : demande/idée, fiche de qualification, business case, initiative/projet/programme/produit/epic, portefeuille et sous-portefeuilles, critères et grille de scoring, scénario de portefeuille, décision d'arbitrage (go / no-go / différé / arrêt) avec son instance (comité) et sa date, jalon/stage gate, bilan de projet, bénéfice.
  - **Indicateurs** : nombre et montant d'initiatives par statut et par objectif stratégique, part du portefeuille alignée sur chaque objectif, répartition par nature (réglementaire, obsolescence, métier, innovation), écarts coût/délai/périmètre, taux d'engagement de la capacité, taux de projets arrêtés, délai demande → décision.
  - **Décisions éclairées** : lancer, différer, arrêter, fusionner ; où placer la ligne de coupe budgétaire ; quel scénario de portefeuille retenir.
- **[non sourcé]** Le cycle classique est : collecte de la demande → qualification (opportunité, macro-chiffrage en coût et en charge) → business case → scoring → arbitrage en comité (souvent annuel, avec revues trimestrielles) → suivi d'exécution (stage gates, météo projet) → clôture → bilan et suivi des bénéfices post-projet. Aucune source lue ne décrit ce cycle de bout en bout ; il est cohérent avec les chapitres PMI et les cycles MoP.
- **[non sourcé]** Autres méthodes de priorisation à couvrir, non vérifiées ici : MoSCoW (Must/Should/Could/Won't, issu de DSDM), matrice valeur/effort, matrice valeur/risque (diagramme à bulles), scoring multicritère pondéré, coût du retard chiffré en euros par semaine (CD3), modèle de Kano, frontière efficiente, catégories d'obligation (réglementaire/obsolescence « hors classement »).
- Le positionnement d'Alfabet (outil d'architecture d'entreprise) en Leader SPM suggère que le rapprochement portefeuille ↔ cartographie applicative ↔ capacités métier est un différenciateur reconnu : c'est précisément l'angle d'Odin.
- Un outil d'aide à la décision doit conserver la **trace des arbitrages** (qui, quand, sur quels critères, quelles alternatives écartées) : c'est un objet métier à part entière, rarement bien traité.

### Gaps
- Texte exact de la définition Gartner et critères d'évaluation du MQ 2025 : paywall, seules des citations d'éditeurs ont été obtenues.
- Domaines de performance du standard PMI et statistiques *Pulse of the Profession* récentes : non trouvés.
- Modèles de données détaillés des éditeurs (ServiceNow SPM, Planisware, Sciforma, Triskell, Jira Align, Aha!, Productboard) : non consultés faute de budget de recherche.
- Aucune source francophone lue sur le rôle MOA/MOE dans la qualification de la demande.

## 2. Types de roadmaps dans un SI, objets constitutifs, dépendances, scénarios et replanification

### Takeaway
La recherche n'a pas produit de source dédiée aux typologies de roadmaps ; seuls les éléments MoP (plan de livraison) et SAFe (epics, value streams) sont sourcés. Le contenu ci-dessous relève donc surtout de la pratique courante et doit être présenté comme tel.

### Cited Findings
- Le plan de livraison MoP agrège calendrier, jalons, risques, coûts et ressources du portefeuille : c'est l'équivalent normatif d'une roadmap de portefeuille. — [mop.wiki, cycle de définition](https://mop.wiki/management-cycles/definition-cycle/)
- Dans SAFe, les Epics de portefeuille traversent les value streams et sont séquencés dans un Kanban de portefeuille (WSJF surtout à l'état « Analyzing »). Source tierce. — [agility-at-scale](https://agility-at-scale.com/safe/lpm/lpm-implementation-guide/)
- Hausses éditeurs anticipées de 10 à 15 % par an entre 2025 et 2028 et bascule de plus de 80 % des éditeurs vers l'abonnement (cabinet Elée) : les échéances contractuelles et de fin de support deviennent des jalons structurants des roadmaps technologiques. — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)

### Inferences
- **[non sourcé]** Typologie à couvrir dans Odin :
  - roadmap **stratégique / schéma directeur SI** (3 à 5 ans, par objectifs) ;
  - roadmap de **transformation** (programmes, trajectoire cible, états intermédiaires de l'architecture) ;
  - roadmap **produit** (thèmes → epics → releases) ;
  - roadmap **applicative** (cycle de vie par application : investir / tolérer / migrer / éliminer, décommissionnements) ;
  - roadmap **technologique / obsolescence** (fins de support, montées de version, sorties de datacenter) ;
  - roadmap **sécurité** (plan de remédiation, mise en conformité) ;
  - roadmap **par capacité métier** (carte de chaleur des capacités × investissements) ;
  - roadmap **réglementaire** (échéances légales, non négociables) ;
  - roadmap **sourcing/contrats** (renouvellements, réversibilités).
- **[non sourcé]** Objets constitutifs : horizon (now/next/later ou trimestres/années), thème/axe stratégique, objectif/OKR, initiative, epic, livrable, jalon, release, dépendance (typée : technique, fonctionnelle, ressource, contractuelle, réglementaire ; durcie ou souple), hypothèse, niveau de confiance, version de référence (baseline) et scénario.
- **[non sourcé]** Le format now/next/later (attribué à Janna Bastow, ProdPad) remplace les dates par des horizons de certitude décroissante ; la recherche lancée sur ce point n'a rien renvoyé.
- **Indicateurs** : glissement de jalons par rapport à la baseline, nombre de replanifications, dépendances critiques non sécurisées, part de la roadmap « subie » (réglementaire + obsolescence) contre « choisie », taux de livraison par horizon, jalons en collision sur une même équipe ou un même métier.
- **Décisions éclairées** : séquencement, gel ou décalage d'une initiative, effet domino d'un retard, choix entre scénarios (ambitieux / nominal / contraint), date d'engagement communicable à la direction.
- La valeur d'Odin est dans le **croisement** des roadmaps (une fin de support + un renouvellement de contrat + un projet métier sur la même application) plus que dans leur dessin ; cela suppose un référentiel d'objets commun avec la cartographie applicative.

### Gaps
- Aucune source consultée sur les typologies de roadmaps, la gestion formelle des dépendances inter-projets, ni les pratiques de replanification (rolling wave, PI planning). À compléter si le rapport doit sourcer cette section.
- Pas de source sur l'origine et la définition exacte de now/next/later.

## 3. Capacity planning en ETP : capacité vs demande, run/build/transformation, plan de charge, scénarios

### Takeaway
Les référentiels font de la capacité un domaine de premier rang (PMI : « capacity and capability management » ; MoP : « resource management » ; SAFe : allocation de capacité comme garde-fou budgétaire), mais je n'ai trouvé aucune source chiffrée ou méthodologique francophone sur le plan de charge en ETP.

### Cited Findings
- PMI consacre un chapitre à la gestion de la capacité et des capabilités du portefeuille ; MoP a une pratique de gestion des ressources et un document « resource schedule ». — [IPG, table des matières PMI](https://www.ipgbook.com/the-standard-for-portfolio-management-products-9781628251975.php) ; [mop.wiki, documents clés](https://mop.wiki/key-documents/)
- SAFe : chaque value stream fixe ses propres règles explicites d'allocation de capacité et peut adapter ses catégories ; la répartition doit évoluer selon le stade du cycle de vie, le marché et la santé technique. — [SAFe v5, guardrails](https://v5.scaledagileframework.com/?p=43915) ; [open-exam-prep](https://open-exam-prep.com/study-guides/safe-popm/ch04-prioritization-kanban/capacity-allocation)
- SAFe finance des chaînes de valeur (équipes stables) plutôt que des projets. Source tierce. — [agility-at-scale, Lean budgets](https://agility-at-scale.com/safe/lean-budgets/)
- Structure moyenne d'un budget de DSI en France selon Forrester France (Stéphane Roger) : masse salariale 35 %, prestations externes 25 %, logiciel 23 %. Soit environ 60 % du budget constitué de travail humain interne ou externe. — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- Hypothèse de productivité à intégrer aux scénarios : l'IA pourrait augmenter la productivité des développeurs d'environ 15 à 20 % (estimation Forrester, formulée au conditionnel). — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- TBM 5.0 fusionne les anciens pools « Internal Labor » et « External Labor » en un pool unique « Staffing » ; 28 % des organisations FinOps commencent à inclure les coûts de main-d'œuvre. — [TBM Council](https://www.tbmcouncil.org/the-tbm-practice-leads-guide-to-the-tbm-taxonomy/) ; [Serviceware, citant State of FinOps](https://serviceware-se.com/en/blog/it-financial-management/it-budget-as-percent-of-revenue-benchmarks-and-how-to-set-yours)

### Inferences
- Axe « Capacité et plan de charge » :
  - **Définition** : confrontation, par période, de la capacité disponible (ETP nets) et de la demande (charge du run + charge des initiatives), par équipe, rôle et compétence.
  - **Objets métier** : personne/poste, équipe, rôle, compétence, statut (interne, prestataire en régie, forfait, alternant), calendrier de disponibilité, affectation (% ou jours-homme par période), demande de ressource, réservation ferme ou prévisionnelle, hypothèses de capacité, scénario.
  - **Indicateurs** : capacité brute vs nette, taux d'occupation/de charge, sur- et sous-charge par compétence, répartition run/build/transformation en ETP, ratio internes/externes, capacité libre à 3/6/12 mois, part de capacité « non planifiable » (support, incidents), écart charge prévue/consommée.
  - **Décisions éclairées** : combien d'initiatives lancer en parallèle, lesquelles décaler, recruter ou recourir à la prestation, internaliser, réaffecter une équipe, plafonner le travail en cours.
- **[non sourcé]** Hypothèses usuelles : passage ETP brut → net (congés, RTT, formation, absences, temps transverse), de l'ordre de 200 à 215 jours ouvrés par an en France ramenés à moins en capacité projet ; taux d'occupation cible volontairement inférieur à 100 % pour absorber l'imprévu. Ordres de grandeur non vérifiés.
- **[non sourcé]** Deux granularités coexistent : planification nominative à court terme (qui fait quoi) et planification par rôle/compétence à moyen terme (profils génériques). Un outil stratégique vise plutôt la seconde.
- **[non sourcé]** *Team Topologies* (Skelton & Pais : équipes stream-aligned, platform, enabling, complicated-subsystem ; charge cognitive) et le principe des équipes stables conduisent à « amener le travail aux équipes » : la capacité devient une donnée fixe et c'est le flux de demande qu'on régule. Non vérifié dans cette recherche.
- Puisque masse salariale + prestations ≈ 60 % du budget (Forrester France), plan de charge et budget sont deux vues de la même réalité : Odin doit pouvoir valoriser un scénario de capacité en euros (taux journalier moyen, coût chargé) et inversement.
- La distinction régie/forfait change la nature de la capacité : la régie est une capacité pilotable, le forfait est un engagement de résultat dont la charge n'est pas visible côté DSI.

### Gaps
- Aucune source trouvée sur les pratiques françaises de plan de charge, les taux d'occupation de référence, ni les ratios internes/externes de marché.
- Team Topologies non sourcé.
- Répartition run/build/transformation en ETP : pas de benchmark trouvé (voir section 5 pour le budget).

## 4. Compétences et GPEC/GEPP côté SI : référentiels, personnes clés, turnover, internes/externes

### Takeaway
Trois référentiels structurent le sujet et sont complémentaires : la nomenclature Cigref décrit des **métiers** (une cinquantaine, 9 familles), l'e-CF des **compétences** (41, 5 niveaux), SFIA des **compétences et niveaux de responsabilité** (7 niveaux). Ils ne s'alignent pas un pour un.

### Cited Findings
- Nomenclature des profils métiers du SI du Cigref : mise à jour environ tous les deux ans ; version 2022 passée de 7 à 9 familles avec une cinquantaine de métiers ; version 2024 : 2 nouveaux profils (familles management de projet et données). Le décompte varie selon les sources : 54 métiers (présentation ANDOR 2024) contre 52 fiches (communiqué en anglais). Une édition 2025 est également signalée. — [Solutions Numériques](https://www.solutions-numeriques.com/?p=100004) ; [ANDOR 2024](https://andor2024.sciencesconf.org/data/pages/27_03_Metiers_comp.pdf) ; [communiqué Cigref 2024](https://windpress.info/press-release/390542/it-job-profiles-nomenclature-2024-version-cigref)
- Les 9 familles : pilotage et organisation de l'évolution du SI ; management de projet ; cycle de vie des applications ; mise à disposition et maintenance des infrastructures ; support aux utilisateurs ; sécurité ; management opérationnel ; données ; relations fournisseurs. Le profil de Chief Digital Officer a disparu du référentiel. — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-le-chief-digital-officer-disparait-du-referentiel-rh-du-cigref-98307.html)
- e-CF, norme EN 16234-1:2019 (remplace l'édition 2016) : langage commun européen pour les compétences TIC ; 41 compétences de référence ; 5 niveaux e-1 à e-5 reliés aux niveaux 3 à 8 du CEC/EQF ; la plupart des compétences ne définissent que deux ou trois niveaux. — [iTeh Standards](https://standards.iteh.ai/catalog/standards/cen/7e895d4e-0eb0-49b4-972f-1f6b202ea400/en-16234-1-2019) ; [BSI](https://knowledge.bsigroup.com/products/e-competence-framework-e-cf-a-common-european-framework-for-ict-professionals-in-all-sectors-framework)
- SFIA 9 : 7 niveaux de responsabilité (1 Follow, 2 Assist, 3 Apply, 4 Enable … 7 Set strategy, inspire, mobilise), caractérisés par des attributs génériques dont autonomie, influence et complexité. — [SFIA Foundation](https://sfia-online.org/en/sfia-9/responsibilities)
- Comparaison SFIA / e-CF (rapport de 2016, antérieur à SFIA 9) : la couverture de SFIA est plus large ; les niveaux ne s'alignent pas un pour un ; une compétence e-CF peut recouvrir plusieurs compétences SFIA. — [SFIA, rapport de mapping](https://sfia-online.org/fr/assets/documents/e-cf/sfia-e-cf-comparison-mapping-report-v1-0.pdf)
- Référentiels publics français utiles : référentiel des métiers et compétences SIC de l'État (jeu de données 2016) et panorama des métiers de la cybersécurité de l'ANSSI. — [data.gouv.fr](https://www.data.gouv.fr/datasets/5796275a88ee3831d77d97c2) ; [ANSSI](https://cyber.gouv.fr/sites/default/files/2021/10/anssi-panorama_metiers_cybersecurite-2020.pdf)

### Inferences
- Axe « Compétences et GEPP du SI » :
  - **Définition** : connaissance des compétences détenues et requises, aujourd'hui et à l'horizon de la roadmap, et plan pour combler l'écart (recruter, former, sous-traiter, internaliser).
  - **Objets métier** : métier/emploi-type (Cigref), compétence et niveau (e-CF/SFIA), profil d'une personne, niveau requis par poste ou par application, personne clé, plan de succession, action de formation, besoin de recrutement, contrat de prestation rattaché à une compétence.
  - **Indicateurs** : matrice de couverture compétences × équipes, écart requis/détenu, nombre de compétences ou d'applications portées par une seule personne (« bus factor » = 1), part de compétences critiques détenues uniquement par des externes, turnover, ancienneté, pyramide des âges et départs prévisibles, délai moyen de recrutement, budget et jours de formation par ETP, ratio internes/externes par famille.
  - **Décisions éclairées** : quelles compétences internaliser (cœur stratégique) ou externaliser, plan de recrutement et de formation, faisabilité d'une trajectoire technologique au regard des compétences, risque de continuité sur une application héritée.
- Les trois référentiels ne se remplacent pas : Odin a intérêt à permettre un référentiel paramétrable (métiers Cigref en entrée « RH », e-CF ou SFIA en entrée « compétence ») plutôt que d'en imposer un.
- Le risque « personne clé » relie trois axes d'Odin : dette (application héritée que plus personne ne maîtrise), capacité (goulot) et sécurité/continuité. C'est un bon exemple d'indicateur transverse.
- **[non sourcé]** En France, la GPEC a été renommée GEPP (gestion des emplois et des parcours professionnels) par les ordonnances de 2017, avec obligation de négociation pour les entreprises d'au moins 300 salariés. Non vérifié ici.

### Gaps
- Aucune donnée chiffrée trouvée sur le turnover IT, les tensions de recrutement ou le ratio internes/externes en France.
- Pas de source sur le « bus factor » comme indicateur formalisé en DSI.
- Nombre exact de profils de la nomenclature Cigref 2024/2025 non tranché (52 ou 54) ; le document officiel n'a pas été consulté.
- Contenu de SFIA 9 au niveau des compétences (nombre, catégories) non vérifié.

## 5. Pilotage financier IT : CAPEX/OPEX, run/build, TBM, coûts par application/service, TCO, refacturation, FinOps, benchmarks

### Takeaway
TBM fournit le modèle d'objets pour passer des comptes à la valeur (cost pools → tours technologiques → solutions → consommateurs) et FinOps s'étend désormais bien au-delà du cloud (IA, SaaS, licences, datacenter). En revanche, les ratios de référence (IT en % du CA, part du run) sont derrière paywall : je n'ai obtenu aucun chiffre primaire récent et fiable, et il ne faut pas en avancer.

### Cited Findings
- Taxonomie TBM : quatre couches reliées — **cost pools** (nature de dépense, raccordée au grand livre), **technology resource towers**, **solutions**, **consumers**. Trois vues : Finance (cost pools + tours), Technologie (tours + solutions), Métier (solutions + consommateurs). — [TBM Council, taxonomie](https://www.tbmcouncil.org/taxonomy) ; [TBM Council, guide du practice lead](https://www.tbmcouncil.org/the-tbm-practice-leads-guide-to-the-tbm-taxonomy/)
- Changements de la version 5.0 : « Staffing » remplace Internal/External Labor ; « Cloud Services » devient un cost pool de premier niveau ; tours « Platform » et « Output » retirées ; ajout de « Smart Devices » et « Data » (avec sous-tours du type ML Engineering, Model Hosting). Une version 5.0.1 ajoutant le support de l'IA est citée par une source tierce. — [TBM Council](https://www.tbmcouncil.org/the-tbm-practice-leads-guide-to-the-tbm-taxonomy/) ; [Finout](https://www.finout.io/blog/technology-business-management)
- Le rattachement des coûts aux tours est un exercice de mapping distinct : les coûts classés en cost pools ne s'écoulent pas automatiquement vers les tours. Les règles d'allocation sont donc un objet métier en soi. — [TBM Council, mapping](https://www.tbmcouncil.org/learn-tbm/tbm-modeling/mapping-to-resource-towers/)
- Modèle Cigref d'analyse et de benchmarking des coûts informatiques : fondé sur la méthode ABC (Activity Based Costing), vise des coûts complets comparables entre entreprises (y compris internalisation vs externalisation) et sert aussi à refacturer les services de la DSI à partir d'un catalogue. Je n'ai pas pu confirmer la date ni le contenu de la dernière édition. — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-un-guide-pour-bien-comparer-les-prix-des-prestations-it-59211.html) ; [KPMG, benchmarking des coûts IT](https://kpmg.com/fr/fr/insights/it/benchmarking-couts-it.html)
- FinOps Framework : phases Inform / Optimize / Operate ; quatre domaines (Understand Usage & Cost, Optimize Usage & Cost, Quantify Business Value, Manage the FinOps Practice), le mot « cloud » ayant été retiré des intitulés en 2025 ; ajout des **Scopes** en 2025 (ex. IA, licences). Mise à jour 2026 présentée en mars 2026 : nouvelle capacité « Executive Strategy Alignment ». Une source tierce parle de six domaines en 2026, en contradiction avec les quatre : non vérifié. — [FinOps Foundation, 2025](https://finops.org/insights/2025-finops-framework) ; [FinOps Foundation, 2026](https://www.finops.org/insights/2026-finops-framework/)
- Périmètre réel des équipes FinOps (6e rapport State of FinOps, cité par un tiers) : 98 % gèrent la dépense IA (63 % un an plus tôt, 31 % deux ans plus tôt), 64 % les licences, 57 % le cloud privé, 48 % le datacenter. — [Serviceware](https://serviceware-se.com/en/blog/it-financial-management/it-budget-as-percent-of-revenue-benchmarks-and-how-to-set-yours)
- Gaspillage cloud : la part estimée de dépense IaaS/PaaS gaspillée remonte à 29 % en 2026 après cinq années de baisse (estimation déclarative ; 753 répondants, dont 62 % aux États-Unis). Causes avancées : nouveaux modèles de prix, complexité des coûts IA, remises d'engagement sous-utilisées. — [Flexera, communiqué](https://www.flexera.com/about-us/press-center/flexera-finds-cloud-value-is-rising-while-ai-waste-grows) ; [TechInformed](https://techinformed.com/ai-workloads-drive-estimated-cloud-waste-to-29/)
- Gain FinOps cité en France : jusqu'à 7 % d'économies par an (cabinet Elée). — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- Inflation : étude Asterès pour le Cigref (relayée fin mai 2026) — hausse moyenne déclarée de 8,7 % par an des coûts cloud et logiciels sur trois ans, 12 % par an attendus sur cinq ans, surcoût annuel jusqu'à 140 Md€ pour les organisations européennes à l'horizon 2030. Chiffres issus de la presse, rapport non consulté. — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-l-inflation-gonfle-la-facture-cloud-et-logicielle-de-140-mdeteuro-par-an-100293.html) ; [ActuIA](https://www.actuia.com/actualite/cigref-140-mdeur-de-surcouts-cloud-en-europe-lia-en-bundle-en-deuxieme-cause/)
- Budgets 2026 : un peu plus d'un tiers des responsables IT prévoient une hausse de budget pour 2026, contre neuf sur dix un an plus tôt pour 2025 (Experio). — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- Benchmarks disponibles mais payants : Gartner *IT Key Metrics Data 2026* (publié le 11/12/2025 ; 4 939 DSI et responsables IT ; plus de 625 Md$ de dépense IT) ; Avasant/Computer Economics *IT Spending and Staffing Benchmarks* (plus de 750 dirigeants IT, États-Unis et Canada ; édition Europe distincte). — [Gartner](https://www.gartner.com/en/documents/7253830) ; [Avasant](https://avasant.com/research/it-spending-staffing-study/) ; [Avasant Europe](https://avasant.com/research/it-spending-and-staffing-study-europe/)
- IT en % du CA, éléments partiels : services financiers de 4,4 % (25e centile) à 11,4 % (75e centile) selon Avasant (note non datée) ; Avasant rappelle que la moyenne est très supérieure à la médiane. Des sources secondaires donnent 3,1–3,6 % ou 3,6–5 % en moyenne tous secteurs, d'environ 1 % (construction) à plus de 10 % (finance) : **non vérifié sur source primaire**. — [Avasant](https://avasant.com/it-spending-as-a-percentage-of-revenue-by-industry-company-size-and-region/) ; [The Network Installers](https://thenetworkinstallers.com/blog/it-budget-statistics/)
- Run vs change : la répartition 70 % run / 30 % change est donnée comme un **exemple illustratif**, pas comme un benchmark, et « peut signaler une inertie opérationnelle ou une complexité réglementaire » ; il n'existe pas de ratio IT/CA universel. — [Serviceware](https://serviceware-se.com/en/blog/it-financial-management/it-budget-as-percent-of-revenue-benchmarks-and-how-to-set-yours)
- Secteur public français : les montants publiés sur l'investissement numérique de l'État ne couvrent que le build, et seulement le build capitalisé ; le run n'apparaît pas (article de septembre 2026). — [Acteurs publics](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)
- L'ITFM est présenté comme le moyen d'objectiver les arbitrages entre build et run. — [KPMG, ITFM](https://kpmg.com/fr/fr/insights/it/itfm-gestion-depenses-technologique.html)

### Inferences
- Axe « Pilotage financier du SI » :
  - **Définition** : construction, suivi et explication du coût du SI selon plusieurs axes d'analyse simultanés, pour arbitrer et rendre des comptes.
  - **Objets métier** : exercice et version budgétaire (budget initial, reprévisions, réalisé, engagé), ligne budgétaire, nature (CAPEX/OPEX), destination (run / build / transformation), cost pool, tour technologique, solution/application/service, consommateur (direction métier, capacité métier), règle d'allocation, unité d'œuvre et prix unitaire, contrat et commande, immobilisation et amortissement, scénario budgétaire.
  - **Indicateurs** : budget IT en % du CA et par utilisateur/ETP, part run/build, part CAPEX/OPEX, écart budget/réalisé/atterrissage, coût complet et TCO par application et par capacité métier, coût unitaire des services, part des dépenses fixes vs variables, part cloud et taux de couverture par engagements, taux de dépense allouée, inflation subie par fournisseur, part de l'IA.
  - **Décisions éclairées** : niveau et répartition du budget, plan d'économies, rationalisation applicative (coût vs valeur vs dette), internaliser/externaliser, migrer vers le cloud ou en sortir, refacturer ou seulement montrer (showback), marge de manœuvre réellement disponible pour la transformation.
- **[non sourcé]** Notions non vérifiées ici : TCO (acquisition + exploitation + évolution + sortie sur la durée de vie), distinction showback (information) / chargeback (refacturation effective), activation en immobilisation des développements, impact du passage à l'abonnement qui déplace du CAPEX vers l'OPEX.
- L'inflation éditeur à deux chiffres comprime mécaniquement le build à budget constant : un outil d'aide à la décision doit projeter le run **à périmètre constant** sur plusieurs années pour montrer l'érosion de la marge de transformation. C'est une déduction à partir des chiffres Asterès/Elée.
- L'extension de TBM (pool « Staffing » unique, pool « Cloud Services », tour « Data ») et de FinOps (IA, licences, main-d'œuvre) montre une convergence ITFM/TBM/FinOps : Odin peut traiter « finances » comme un axe unique plutôt que trois.
- Le constat d'Acteurs publics (run invisible) illustre un besoin d'Odin : rendre visible la part non discrétionnaire de la dépense.

### Gaps
- **Ratios chiffrés demandés non obtenus de source primaire** : part du run dans le budget (le « 70/30 » circule mais aucune étude datée n'a été trouvée), budget IT en % du CA par secteur pour 2025/2026 (Gartner ITKMD et Avasant sont payants). Ne pas citer de chiffre précis sans accès à ces rapports.
- Édition courante du modèle de benchmarking Cigref (date, structure, périmètre) non confirmée.
- Contenu détaillé de TBM 5.0 (liste des cost pools et des tours) non extrait.
- Rapport State of FinOps 2026 non consulté directement ; nombre de domaines du framework 2026 incertain.
- Aucune source sur les pratiques de refacturation interne en France.

## 6. Fournisseurs, contrats, licences et sourcing

### Takeaway
La dépendance fournisseur est devenue un sujet stratégique et chiffré en Europe (inflation, cas Broadcom/VMware, part des acteurs américains) et, dans la finance, une obligation réglementaire (DORA : registre des contrats TIC, risque de concentration, stratégie de sortie). C'est un axe à part entière, à l'intersection des finances, du risque et de la sécurité.

### Cited Findings
- 83 % du marché européen du cloud et du logiciel B2B revient à des entreprises américaines, soit 54 Md€ par an pour la France et 330 Md€ pour l'UE (étude d'avril 2025 pour le Cigref, rapportée par la presse). — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-l-inflation-gonfle-la-facture-cloud-et-logicielle-de-140-mdeteuro-par-an-100293.html)
- Le pouvoir de négociation des clients est limité par les coûts de migration, l'intégration étroite logiciel/infrastructure et l'absence d'alternatives crédibles sur certains segments. — [ActuIA](https://www.actuia.com/actualite/cigref-140-mdeur-de-surcouts-cloud-en-europe-lia-en-bundle-en-deuxieme-cause/)
- À 15 % de hausse par an, les coûts logiciels doublent en huit ans (Henri d'Agrain, Cigref). — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- Broadcom/VMware : hausses de 800 à 1 500 % rapportées par l'observatoire ECCO (initiative du CISPE ; estimation d'observatoire, non vérifiée indépendamment), liées à la fin des licences perpétuelles ; le Cigref qualifie ces pratiques d'« inacceptables » ; Orange et Thales ont engagé des actions en justice. — [IT-Connect](https://www.it-connect.fr/broadcom-vmware-des-hausses-de-tarifs-de-800-a-1-500-sur-le-tarif-des-licences/) ; [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-emmanuel-sardet-cigref--les-pratiques-de-broadcom-sont-inacceptables-96945.html) ; [Next](https://next.ink/brief-article/la-grogne-monte-contre-vmware-broadcom-att-orange-et-thales-vont-en-justice/)
- Leviers et retours d'expérience : négociation concentrée sur les éditeurs représentant 80 % de la dépense, réduction d'un tiers des licences contre engagements de 2 à 5 ans (Aesio) ; suivi des usages logiciels coûtant 3 à 4 % du budget logiciel ; Microsoft Copilot doublant à peu près le coût de licence par utilisateur (Elée) ; proposition de pondérer la souveraineté numérique à 10–15 % dans les appels d'offres (Urssaf). — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- SaaS : la dépense gaspillée continue d'augmenter d'une année sur l'autre (Flexera, State of ITAM 2026, 512 répondants ; pourcentage non obtenu). — [Flexera](https://www.flexera.com/blog/it-asset-management/state-of-itam-2026/)
- DORA : le registre d'informations recense tous les accords contractuels avec les prestataires TIC tiers ; il conditionne l'évaluation du risque de concentration, la définition des fonctions critiques ou importantes et la stratégie de sortie ; il permet d'identifier les prestataires non substituables et les concentrations géographiques. — [Bastion](https://bastion.tech/learn-fr/dora/register-of-information) ; [Paperjam](https://paperjam.lu/article/le-registre-dinformations-dora-maillon-faible-de-la-conformite)
- À peine 10 % des institutions évalueraient systématiquement le risque de concentration pour chaque accord contractuel (chiffre d'un seul article, non recoupé). — [Paperjam](https://paperjam.lu/article/le-registre-dinformations-dora-maillon-faible-de-la-conformite)
- DORA art. 28(8) : stratégie de sortie exigée pour les services TIC soutenant des fonctions critiques ou importantes ; périmètre exact à vérifier dans le règlement (UE) 2022/2554, les sources secondaires divergent. — [Orbiq](https://www.orbiqhq.com/fr/modeles/modele-strategie-sortie-dora) ; [Ayinedjimi](https://ayinedjimi-consultants.fr/glossaire/strategie-de-sortie-dora)
- La nomenclature Cigref comporte une famille « relations fournisseurs » : le sourcing est un métier reconnu du SI. — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-le-chief-digital-officer-disparait-du-referentiel-rh-du-cigref-98307.html)

### Inferences
- Axe « Fournisseurs, contrats et sourcing » :
  - **Définition** : connaissance du portefeuille de fournisseurs et d'engagements contractuels, de leurs échéances, de leur coût et du degré de dépendance qu'ils créent.
  - **Objets métier** : fournisseur (et groupe d'appartenance), contrat, avenant, échéance (renouvellement, préavis, fin de support), métrique de licence et droits détenus vs déployés vs utilisés, prestation (régie/forfait/centre de services), engagement de volume, clause de réversibilité, plan de sortie, lien contrat ↔ application ↔ fonction critique.
  - **Indicateurs** : dépense par fournisseur et concentration (part des 5 ou 10 premiers), échéancier des renouvellements à 6/12/24 mois, taux d'utilisation des licences, exposition au risque d'audit, hausse tarifaire subie, nombre de fonctions critiques dépendant d'un fournisseur unique, existence d'une alternative et d'un plan de sortie, localisation/juridiction.
  - **Décisions éclairées** : renouveler, renégocier, sortir ; engager une migration avant une échéance ; diversifier ; internaliser ; fixer le calendrier d'un projet en fonction d'un préavis.
- Les échéances contractuelles sont des **jalons de roadmap** à part entière : une date de préavis manquée verrouille une décision d'architecture pour plusieurs années. D'où l'intérêt de relier contrats, applications et roadmaps.
- DORA ne s'applique qu'au secteur financier, mais son modèle (registre, criticité, concentration, sortie) est transposable comme structure de données générique pour Odin.
- La souveraineté (juridiction du fournisseur, part de dépense extra-européenne) est un critère de décision émergent en France qui peut être traité comme un attribut du fournisseur et un critère de scoring.

### Gaps
- Pratiques SAM (Software Asset Management) et coûts d'audit éditeur : aucune donnée chiffrée obtenue.
- Texte de DORA non consulté directement ; équivalent hors finance (NIS 2, chaîne d'approvisionnement) hors de mon périmètre.
- Pas de source sur les modèles de sourcing (centres de services, offshore) ni sur leurs indicateurs.

## 7. Réalisation des bénéfices et valeur

### Takeaway
Les référentiels placent la valeur au centre (PMI : chapitre « value management » ; MoP : pratique de gestion des bénéfices et plan de réalisation des bénéfices), mais la recherche n'a livré presque aucune donnée fiable sur le taux de réalisation effectif.

### Cited Findings
- MoP inscrit la gestion des bénéfices dans le cycle de livraison du portefeuille, avec un plan de réalisation des bénéfices parmi les documents clés. — [mop.wiki, cycle de livraison](https://mop.wiki/management-cycles/delivery-cycle/) ; [mop.wiki, documents clés](https://mop.wiki/key-documents/)
- Le standard PMI comporte un chapitre de gestion de la valeur du portefeuille. — [IPG, table des matières](https://www.ipgbook.com/the-standard-for-portfolio-management-products-9781628251975.php)
- FinOps comporte un domaine « Quantify Business Value » : la mesure de valeur entre aussi par la porte financière. — [FinOps Foundation](https://finops.org/insights/2025-finops-framework)
- « Environ 33 % seulement des projets de transformation digitale atteignent leurs bénéfices de revenus visés » : affirmation d'un blog éditeur **sans source ni date**, à ne pas reprendre telle quelle. — [Serviceware](https://serviceware-se.com/en/blog/it-financial-management/it-budget-as-percent-of-revenue-benchmarks-and-how-to-set-yours)
- Plus de 82 % des entreprises interrogées déclarent avoir dépassé le budget initial de leur transformation (étude NTT DATA et Natuvion ; échantillon et date non vérifiés). — [ActuIA](https://www.actuia.com/actualite/transformation-digitale-plus-de-82-des-entreprises-depassent-le-budget-initial/)

### Inferences
- Axe « Valeur et bénéfices » :
  - **Définition** : suivi, de l'engagement au constat, des gains attendus d'un investissement, au-delà de la livraison du projet.
  - **Objets métier** : bénéfice (type : financier, non financier, évitement de coût, conformité, réduction de risque), mesure de référence, cible, propriétaire **métier** du bénéfice, date de constat, hypothèses, lien bénéfice ↔ objectif stratégique ↔ initiative, bilan post-projet.
  - **Indicateurs** : bénéfices prévus / reprévus / constatés, taux de réalisation, délai de retour (payback), VAN/NPV, TRI, ROI, part des initiatives dotées d'un business case mesurable, part des bilans réellement réalisés.
  - **Décisions éclairées** : poursuivre ou arrêter une initiative dont le cas d'affaires s'est dégradé, recalibrer les estimations futures, réallouer vers les types d'investissement qui tiennent leurs promesses.
- **[non sourcé]** Définitions financières non vérifiées ici : VAN = somme actualisée des flux nets ; payback = délai pour que les gains cumulés couvrent l'investissement ; ROI = (gains − coûts) / coûts. MSP (AXELOS) traite la gestion des bénéfices au niveau programme.
- **[non sourcé]** Le suivi post-projet est le maillon le plus souvent absent : l'équipe projet est dissoute à la mise en service, alors que les bénéfices apparaissent 6 à 24 mois plus tard et appartiennent au métier. Un outil doit donc porter un objet « bénéfice » dont la durée de vie dépasse celle du projet.
- Pour un outil stratégique, la valeur ne se réduit pas au ROI : réduction de risque, conformité et réduction de dette doivent pouvoir être exprimées et comparées (d'où le scoring multicritère de la section 1).

### Gaps
- Aucune statistique fiable et datée sur le taux de réalisation des bénéfices (PMI Pulse of the Profession non trouvé).
- MSP et la littérature spécialisée en benefits realization management (Bradley, Ward & Daniel) non consultées.

## 8. Axes souvent oubliés

### Takeaway
Rien dans la recherche ne documente directement les « angles morts » ; cette section est une synthèse raisonnée à partir des sections précédentes. Les candidats les plus solides à ajouter à la liste de l'utilisateur sont : **finances**, **fournisseurs/contrats/sourcing**, **compétences**, **valeur/bénéfices**, **gestion de la demande**, **décisions/arbitrages** et **capacité d'absorption du changement**.

### Cited Findings
- Les référentiels traitent comme domaines distincts des sujets absents de la liste initiale d'Odin : gestion financière, gestion des bénéfices, gestion des risques du portefeuille, engagement des parties prenantes, gouvernance (MoP) ; gestion de la valeur, gestion des risques, engagement des parties prenantes (PMI). — [QA, pratiques MoP](https://info.qa.com/PBPMOPF) ; [IPG, table des matières PMI](https://www.ipgbook.com/the-standard-for-portfolio-management-products-9781628251975.php)
- Le coût de l'inaction est chiffrable sur au moins un poste : une inflation logicielle de 15 % par an double la facture en huit ans à périmètre constant. — [Le Monde Informatique, 26/09/2025](https://www.lemondeinformatique.fr/actualites/lire-les-recettes-des-dsi-face-au-casse-tete-du-budget-it-2026-97982.html)
- Le run est structurellement moins visible que le build dans les restitutions budgétaires (cas de l'État). — [Acteurs publics](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)
- L'IA est devenue un poste de dépense piloté par 98 % des équipes FinOps et une cause identifiée de remontée du gaspillage cloud : c'est un objet de portefeuille et de budget à part. — [Serviceware](https://serviceware-se.com/en/blog/it-financial-management/it-budget-as-percent-of-revenue-benchmarks-and-how-to-set-yours) ; [Flexera](https://www.flexera.com/about-us/press-center/flexera-finds-cloud-value-is-rising-while-ai-waste-grows)

### Inferences
Axes ou sous-axes manquants par rapport à la liste de l'utilisateur (dette, roadmaps, objectifs, sécurité, reporting, ressources/ETP, métiers, rapports, présentations), dans mon périmètre :
- **Finances** (section 5) : absent de la liste alors que c'est le premier langage de la direction générale.
- **Fournisseurs, contrats, licences, sourcing** (section 6) : absent ; porteur d'échéances dures et de risque de dépendance.
- **Portefeuille et gestion de la demande** : la liste contient « roadmaps » (le résultat) mais pas l'entonnoir amont (demandes métier, qualification, file d'attente, refus). Indicateurs : volume et âge des demandes, taux d'acceptation, demande non servie par direction métier.
- **Compétences / GEPP** (section 4) : distinct de la simple capacité en ETP ; deux ETP ne sont pas interchangeables.
- **Valeur et bénéfices** (section 7) : la liste a « objectifs » mais pas la boucle de vérification.
- **Décisions et arbitrages** : registre des décisions, hypothèses et alternatives écartées ; c'est le produit même d'un outil d'aide à la décision.
- **Scénarios / what-if** : capacité transverse (portefeuille, capacité, budget) plutôt qu'un axe, mais à spécifier explicitement.
- **Dépendances inter-projets** et **risques du portefeuille** (risques agrégés, pas seulement risques projet).
- **Conduite du changement et capacité d'absorption des métiers** : **[non sourcé]** la contrainte n'est pas seulement la capacité de la DSI à livrer mais celle des métiers à absorber (formations, déploiements simultanés sur une même population, périodes de gel comme les clôtures comptables ou les pics saisonniers). Objets : population impactée, calendrier d'impacts, périodes de gel. Indicateur : nombre de changements simultanés par population et par période.
- **Coût de l'inaction / scénario « ne rien faire »** : à exiger dans tout business case (inflation subie, risque d'obsolescence, pénalité réglementaire).
- **Obligations réglementaires et échéances légales** comme catégorie de portefeuille non arbitrable.
- **IA** comme catégorie transverse de dépense, de demande et de compétences.
- **Référentiel organisationnel** (équipes, value streams, directions métier) : prérequis commun à la capacité, aux finances et au portefeuille.

### Gaps
- Aucune source consultée sur la capacité d'absorption du changement, la gestion de la demande métier, ni les risques de portefeuille : les éléments ci-dessus sont des inférences à valider.
- Pas de retour d'expérience de DSI francophones (blogs, Cigref) sur les angles morts de leurs outils de pilotage.
- Hors périmètre mais à croiser avec les autres chercheurs : RSE/numérique responsable (le Cigref a publié en 2023 un outil de critères RSE dans les projets IT, et GreenIT.fr un benchmark annuel, vus dans les résultats mais non lus).
