# Architecture d'entreprise, cartographie du SI, portefeuille applicatif et dette technique/obsolescence (secteur public, état fin 2026)

Note méthodo : 16 appels de recherche environ ; beaucoup de pages primaires (cyber.gouv.fr, numerique.gouv.fr, ccomptes.fr) n'ont pas été ouvertes directement, les faits viennent de résultats de recherche synthétisés et de presse spécialisée. Les éléments marqués [CG] sont de la connaissance générale du domaine, NON sourcés dans cette session : à vérifier avant publication. Marqueur [PUBLIC] = spécifique au secteur public.

## 1. Couches et objets d'une cartographie SI (urbanisation, ArchiMate, TOGAF, ANSSI/Mercator)

### Takeaway
La cartographie publique de référence côté sécurité est le guide ANSSI (vues métier/applicative/administration/infrastructure logique et physique, écosystème), outillé par l'open source Mercator ; côté urbanisation, l'État et la santé ont des cadres communs (cadre commun d'urbanisation, doctrine ANS). Odin doit modéliser un métamodèle unique pouvant alimenter à la fois la vue « décision » (EA) et la vue « sécurité » (ANSSI).

### Cited Findings
- Le guide ANSSI « Cartographie du système d'information » (guide d'élaboration en 5 étapes) est la méthode de référence ; Mercator (open source GPL, Laravel/PHP, auteur Didier Barzin) l'implémente, avec 7 vues : écosystème, métier/processus, applications, administration, logique, physique, etc. ; son métamodèle est dicté par le guide (entités métier, applications, serveurs logiques, réseaux) — [LinuxFR](https://linuxfr.org/news/mercator-la-cartographie-du-systeme-d-information), [SSTIC 2023](https://www.sstic.org/media/SSTIC2023/SSTIC-actes/mercator_-_la_cartographie_des_systmes_dinformatio/SSTIC2023-Slides-mercator_-_la_cartographie_des_systmes_dinformation-barzin.pdf), [dépôt](https://dbarzin.github.io/mercator)
- Mercator prévoit un lien avec MONARC (outil ANSSI d'analyse de risques) — [SSTIC 2023](https://www.sstic.org/media/SSTIC2023/SSTIC-actes/mercator_-_la_cartographie_des_systmes_dinformatio/SSTIC2023-Slides-mercator_-_la_cartographie_des_systmes_dinformation-barzin.pdf)
- Le guide d'homologation de sécurité ANSSI (avril 2025) inclut l'étape « Élaborer la cartographie du SI » ; la cartographie est la première règle du guide d'hygiène — [ANSSI](https://messervices.cyber.gouv.fr/documents-guides/guide-homologation-securite-web-04-2025.pdf)
- [PUBLIC] L'ANS (santé) publie un « Kit de cartographie d'un SI » pour les établissements — [ANS](https://cyberveille.esante.gouv.fr/sites/default/files/media/document/2023-12/ANS%20-%20Kit%20de%20Cartographie%20d%27un%20SI.pdf)
- [PUBLIC] Cadre commun d'urbanisation du SI de l'État, associé au cadre stratégique commun du SI de l'État (mars 2013) ; la doctrine d'urbanisation sectorielle santé (ASIP Santé/ANS) en dérive et s'inspire de l'EIF — [NIFO 2015](https://interoperable-europe.ec.europa.eu/sites/default/files/inline-files/NIFO%20-%20Factsheet%20France_12_2015.pdf), [ANS doctrine](https://esante.gouv.fr/documents/doctrine_2_2_urbanisation-des-si-de-sante.pdf)
- Métier d'« urbaniste des SI » reconnu dans la fonction publique — [Choisir le service public](https://choisirleservicepublic.gouv.fr/metiers/numerique/urbaniste-des-systemes-dinformation/)

### Inferences
- Objets/relations à modéliser (synthèse, [CG] pour ArchiMate/TOGAF/POS) : organisation/entités, politique publique/démarche, processus, capacité métier, application/composant, service applicatif, flux/interface/API, donnée/objet d'information, infrastructure (serveur, réseau, site, cloud), fournisseur/contrat, équipe/ETP, risque, projet. Vues : métier, fonctionnelle, applicative, technique (urbanisation française : zones-quartiers-îlots, POS) ; couches ArchiMate Business/Application/Technology + Strategy/Motivation/Implementation.
- Décisions éclairées : analyse d'impact (qui dépend de quoi), périmètre d'homologation, plan de continuité, qui impacte une réforme législative.
- Spécifique public : double cartographie (urbanisation + sécurité/homologation, OIV/OSE/NIS2 [CG]), rattachement à des politiques publiques et démarches (catalogue de démarches).

### Gaps
- Contenu exact et version actuelle du cadre commun d'urbanisation de l'État : non vérifié (sources anciennes ; à consulter sur numerique.gouv.fr).
- Aucune source ouverte sur ArchiMate/TOGAF/POS/Club URBA-EA dans cette session.

## 2. Business Capability Mapping et référentiels publics

### Takeaway
Les référentiels d'interopérabilité publics (RGI français, EIF européen) normalisent plutôt les échanges que les capacités ; il n'a pas été trouvé de cartographie de processus/capacités de l'État publiquement outillée. Les chantiers d'Odin doivent donc fournir un modèle de capacités importable (démarches, politiques publiques).

### Cited Findings
- RGI : publié le 12 mai 2009, ensemble de standards recommandés avec profils d'interopérabilité — [RGI V1](https://archive.numerique.gouv.fr/uploads/Referentiel_General_Interoperabilite_V1.pdf), [RGI Polynésie](https://www.service-public.pf/sipf/wp-content/uploads/sites/9/2020/04/14-Annexe7_RGI-PF.pdf)
- EIF révisé 2017 (COM(2017) 134, 23 mars 2017) : 4 niveaux (juridique, organisationnel, sémantique, technique), 12 principes, 47 recommandations, couche de gouvernance ; une nouvelle révision est en cours — [Interoperable Europe](https://interoperable-europe.ec.europa.eu/collection/iopeu-monitoring/european-interoperability-framework-eif), [EIF leaflet](https://ec.europa.eu/isa2/sites/isa/files/eif_leaflet_final.pdf)
- [PUBLIC] Briques mutualisées de l'État : FranceConnect, ProConnect (authentification), API Particulier/API Entreprise (équipe DINUM, jetons à renouveler tous les 18 mois sur demande ANSSI), DataPass — [Acteurs Publics](https://acteurspublics.fr/articles/stephanie-schaer-nous-avons-voulu-dans-notre-organisation-affirmer-notre-dynamique-de-mise-en-valeur-du-prive/), [Banque des Territoires](https://www.banquedesterritoires.fr/letat-enrichit-son-catalogue-de-connecteurs-de-donnees-pour-simplifier-les-formalites), [webinaire 2023](https://dev.entrouvert.org/attachments/download/76816/2023-06-13_Webinaire_API-Particulier.pdf)

### Inferences
- Capacité → application via une matrice avec heatmap (maturité fonctionnelle, criticité, couverture, redondance) ; permet de voir les capacités servies par N applications (doublons entre directions/opérateurs) ou sans application. Attribuer à chaque capacité une politique publique/démarche et un usager (citoyen, entreprise, agent).
- Indicateur : % de démarches s'appuyant sur briques mutualisées (FranceConnect, API Particulier) vs développements propres ; principe « Dites-le-nous une fois » (cf. [CG]).

### Gaps
- Modèles sectoriels sécurité sociale (GIE SESAM-Vitale, CNAM, etc.) et cartographie des processus de l'État : aucune source trouvée.
- Taxonomie de capacités standard publique (ex. référentiels de l'AMUE pour l'enseignement supérieur, trouvé seulement en titre : [AMUE](https://www.amue.fr:443/fileadmin/amue/systeme-information/documents-publications/urbanisation_ESR/groupeUrbaESR_SensibilisationUrbanisationGouvernance.pdf)) non exploitée.

## 3. Application Portfolio Management (TIME, 6R, mutualisation, SILL)

### Takeaway
TIME classe chaque application en Tolerate/Invest/Migrate/Eliminate selon valeur métier et adéquation technique ; il doit être continu. Côté public, s'ajoutent le réemploi (SILL, code.gouv.fr), les briques mutualisées et la souveraineté.

### Cited Findings
- TIME : 4 actions ; axes valeur métier × adéquation technique/fonctionnelle ; « Tolerate » provisoire ; processus continu ; variante « Modernize » pour Migrate — [LeanIX Tolerate](https://leanix.net/en/blog/gartner-time-tolerate), [LeanIX wiki](https://www.leanix.net/en/wiki/ea/gartner-time-model), [GetInSync](https://getinsync.ca/time-framework/)
- [PUBLIC] SILL (DINUM, code.gouv.fr/sill) : liste de logiciels libres recommandés ; environ 530 logiciels en 2025 (292 en 2022 ; ordre de grandeur fluctuant selon les éditions) ; critère de licence libre FSF/OSI ; mis à jour en continu — [Blog du Modérateur](https://www.blogdumoderateur.com/logiciels-libres-recommandes-etat-2025/), [it-connect 2022](https://www.it-connect.fr/sill-2022-voici-les-logiciels-libres-recommandes-par-le-gouvernement/), [data.gouv](https://data.gouv.fr/en/datasets/socle-interministeriel-de-logiciels-libres)
- [PUBLIC] DINUM propose « La Suite » (outils open source pour agents) et la plateforme IA « Albert » (juillet 2024) — [Wikipedia DINUM](https://en.wikipedia.org/wiki/DINUM)
- [PUBLIC] Doctrine « cloud au centre » (circulaire 6282-SG du 5 juillet 2021, mise à jour 2023, renforcée par la loi SREN de mai 2024) : hébergement des données sensibles en cloud interministériel ou qualifié SecNumCloud ; commandes sur le marché interministériel « Nuage Public » +62 % en 2025 ; PREMI3NS (S3NS) qualifié SecNumCloud fin 2025 ; les opérateurs de l'État sont un angle mort et il manque des indicateurs d'application — [Acteurs Publics](https://acteurspublics.fr/articles/les-operateurs-de-letat-angle-mort-de-la-doctrine-cloud-au-centre/), [Solutions Numériques](https://www.solutions-numeriques.com/?p=246326), [circulaire](https://www.transformation.gouv.fr/files/presse/Circulaire-n6282-SG-5072021-doctrineuutilisation-informatique-en-nuage-Etat.pdf)
- [PUBLIC] La Cour des comptes pousse à sortir de la dépendance à Microsoft en bureautique (octobre 2026) et dénonce un pilotage fragmenté de la souveraineté (octobre 2025) — [Banque des Territoires](https://www.banquedesterritoires.fr/bureautique-la-cour-des-comptes-enjoint-letat-sortir-de-sa-dependance-microsoft), [Solutions Numériques](https://www.solutions-numeriques.com/?p=242059)

### Inferences
- Attributs APM à porter : criticité (RTO/RPO, SIIV/OIV), valeur métier, adéquation technique, coût RUN/BUILD, ETP, licences/contrats et échéances, hébergeur et qualification (SecNumCloud), statut de souveraineté/extraterritorialité, statut de réutilisation (SILL, interne, interministériel), cycle de vie. Stratégies 6R/7R [CG] : rehost, replatform, refactor, rearchitect, rebuild, replace, retire (+ retain) ; en public ajouter « mutualiser/adopter une brique ».
- Décisions : où arrêter, fusionner entre directions, adopter une brique existante, sortir d'un éditeur.

### Gaps
- 6R/7R : aucune source ; définition issue de [CG].
- Chiffres complets du portefeuille applicatif de l'État : aucun consolidé trouvé.

## 4. Dette technique : définition, typologie, mesure, SI hérités publics

### Takeaway
Il n'existe pas de chiffrage consolidé de la dette technique de l'État ; seules des mesures partielles (DGFiP, grands projets, valeur comptable). Le besoin Odin est précisément de produire cette vue (inventaire, coût de remédiation, risque).

### Cited Findings
- ISO/IEC 5055:2021 (CISQ/OMG) : mesure automatisée de fiabilité, sécurité, efficacité de performance et maintenabilité, 138 faiblesses ; spécification CISQ « Automated Technical Debt Measure » v2 (nov. 2023) estime le temps de réparation de chaque faiblesse pour chiffrer la dette. Source : le consortium lui-même, sans validation indépendante trouvée — [CISQ](https://www.it-cisq.org/standards/code-quality-standards/), [CISQ 2021](https://www.it-cisq.org/2021/09/iso-5055-automated-source-code-quality-measures-the-first-standard-of-its-kind/), [OMG 2023](https://www.omg.org/news/releases/pr2023/11-07-23.htm)
- McKinsey (2020) : les DSI estiment la dette à 20-40 % de la valeur du parc technologique (avant amortissement), enquête de 50 DSI de services financiers/tech > 1 Md$ de CA, donc estimation déclarative, non mesurée et hors secteur public ; le « Tech Debt Score » est relié à plus de projets de modernisation abandonnés (+40 % pour les 20 % les moins bien notés) — [McKinsey](https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/tech-debt-reclaiming-tech-equity), [McKinsey TDS](https://www.mckinsey.com/it/our-insights/demystifying-digital-dark-matter-a-new-standard-to-tame-technical-debt)
- [PUBLIC] Cour des comptes (2019, DGFiP/douanes) : SI fiables mais en sédimentation de couches technologiques remontant aux années 1970 ; 700 applications à la DGFiP, 200 aux douanes ; recommandation d'investir pour résorber la dette — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-la-cour-des-comptes-pointe-des-faiblesses-des-si-des-dgfip-et-des-douanes-75485.html)
- [PUBLIC] Cour des comptes, 10 juillet 2024 (pilotage de la transformation numérique par la DINUM) : 13 recommandations ; l'obsolescence matérielle et logicielle conduit l'État à accumuler une dette technique « susceptible à terme de mettre en risque ses capacités opérationnelles » ; absence de vision consolidée de la dépense numérique — [Solutions Numériques](https://www.solutions-numeriques.com/?p=228889), [Acteurs Publics](https://acteurspublics.fr/articles/la-cour-des-comptes-sagace-de-ne-pas-pouvoir-evaluer-les-depenses-numeriques-de-letat)
- [PUBLIC] Valeur comptable nette des logiciels en service fin 2018 : 2,9 Md€ (État) et 3,2 Md€ (opérateurs) ; flux d'investissement 2019 d'environ 380 M€ (~3 % de l'investissement de l'État) ; pas de chiffrage du RUN ; pas de montant de dette technique — [Acteurs Publics, 09/09/2026](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)
- [PUBLIC] DGFiP : l'IGF (bilan du COM 2020-2022) relève des marges de progrès dans le pilotage de la dette technique, recommande cartographie et indicateurs d'évolution et de soutenabilité, et constate que les indicateurs illustrent au mieux une stabilisation ; crédits informatiques 450 M€ en 2023 (+40 % vs 2022) ; stratégie COBOL « en continuité » (socle de gestion de plus de 2 M de lignes, compilateur COBOL-IT ; TVA : renouvellement de plus de 600 serveurs ; application REC de GCOS vers z/OS) ; un rapport parlementaire de 2025 recommande de doubler les moyens de résorption pour 90 % de conformité aux besoins des agents en 2030 — [IGF](https://www.igf.finances.gouv.fr/files/live/sites/igf/files/contributed/Rapports%20de%20mission/2022/2022-M-034-05_Rapport_COM_DGFIP.pdf), [Sénat](https://www.senat.fr/rap/l23-128-315-1/l23-128-315-14.html), [Acteurs Publics](https://acteurspublics.fr/articles/lobsolescence-informatique-point-de-vulnerabilite-de-la-dgfip/), [Solutions Numériques](https://www.solutions-numeriques.com/?p=2292)
- [PUBLIC] Justice : rapport de la Cour sur le numérique du ministère, infrastructures vieillissantes, applications obsolètes — [Acteurs Publics](https://acteurspublics.fr/articles/un-rapport-accablant-de-la-cour-des-comptes-sur-la-transformation-numerique-de-la-justice)
- [PUBLIC] Panne Hélios (DGFiP), incident hors norme — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-panne-de-helios-a-la-dgfip-retour-sur-un-incident-hors-norme-100097.html) (détails non vérifiés)
- [PUBLIC] Le DSI de l'État Jacques Marzin parlait déjà de « dette technique de l'État » — [Acteurs Publics](https://acteurspublics.fr/articles/jacques-marzin-il-existe-une-dette-technique-de-letat/)

### Inferences
- Typologie à modéliser [CG] : code, architecture, infrastructure, tests, documentation, sécurité, données, fonctionnelle, organisationnelle/compétences (COBOL : départs en retraite), contractuelle (verrou éditeur). SQALE et Fowler (dette prudente/imprudente) non sourcés ici.
- Indicateurs : ratio dette/valeur, ratio RUN/BUILD, % applications hors support, âge médian, couverture de tests, part du budget consacrée à la remédiation, risque de panne × impact usagers.
- Décisions : financer remédiation vs projets neufs, arrêt de lignes de code, plan de départ de compétences, valoriser le risque à présenter à la tutelle/Parlement (LOLF, PLF).

### Gaps
- Pas de chiffrage global de la dette technique de l'État, ni de la proportion d'applications obsolètes : non trouvés.
- Aucune donnée sur collectivités, sécurité sociale, hôpitaux ; rapports DINUM sur le sujet non retrouvés.
- SQALE, Fowler quadrant, Sonar : non sourcés.

## 5. Obsolescence, cycle de vie, SBOM, marchés publics

### Takeaway
Les dates de fin de support doivent venir de sources externes (endoflife.date) rapprochées des composants du SBOM, car CycloneDX ne porte pas de champ EOL ; côté public, durée des marchés et dépendance éditeur sont des facteurs de risque à suivre.

### Cited Findings
- CycloneDX 1.6 n'a pas de champ de fin de vie/support ; les données EOL s'obtiennent par jointure externe (ex. endoflife.date, licence MIT, correspondance par package URL) — [endoflife.ai](https://endoflife.ai/article-sbom-end-of-life), [Mend](https://docs.mend.io/platform/latest/sbom-field-coverage-spdx-cyclonedx)
- CycloneDX 1.5 (juin 2023), 1.6 (avril 2024) (source tierce) — [Versio.io](https://www.versio.io/en/product-release-end-of-life-eol-owasp-foundation-cyclonedx.html)
- [PUBLIC] Bureautique Microsoft : la Cour presse l'État de sortir de la dépendance — [Banque des Territoires](https://www.banquedesterritoires.fr/bureautique-la-cour-des-comptes-enjoint-letat-sortir-de-sa-dependance-microsoft)
- [PUBLIC] 17 août 2026 : communiqué du Premier ministre, 5 % du budget numérique de chaque ministère à la cybersécurité dès 2027 ; annonce (30 avril 2026) d'une « Autorité numérique de l'État » à créer avant le 1er janvier 2027 — [Acteurs Publics](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)

### Inferences
- Objets : catalogue de standards/tech radar [CG], versions et dates de fin de support, composants SBOM, vulnérabilités (CVE/KEV), échéances de contrat, clauses de réversibilité.
- Décisions : prioriser montées de version avant EOL, négocier le support étendu, alerter 12/24 mois avant, intégrer l'obsolescence dans les renouvellements de marchés (UGAP, accords-cadres).

### Gaps
- Aucune source sur UGAP, durée des marchés, ni sur la réglementation (CRA, NIS2) dans cette session ; endoflife.date lui-même non consulté.

## 6. Priorisation du remboursement et justification budgétaire

### Takeaway
La dette est mal visible budgétairement : le RUN n'est pas consolidé, et un programme d'investissement numérique central (P352) a été supprimé dans le PLF 2025 ; il faut des outils pour présenter coûts et risques aux tutelles.

### Cited Findings
- Budget : le RUN relève du titre 3 et l'investissement du titre 5 ; le programme 352 a été supprimé du PLF 2025 et ses crédits transférés au programme 129 ; aucun des 15 documents de politique transversale du PLF 2026 ne porte sur le numérique — [Acteurs Publics](https://acteurspublics.fr/articles/numerique-public-le-run-cette-depense-que-letat-ne-veut-pas-voir/)
- Panorama DINUM des grands projets numériques (données ouvertes) : écart budgétaire moyen de 10,8 % en décembre 2023 contre 24 % un an plus tôt et 32 % en 2016 ; engagement budgétaire total en hausse d'environ 500 M€ avec 6 projets de moins — [data.gouv](https://www.data.gouv.fr/fr/datasets/panorama-des-grands-projets-numeriques-de-letat/), [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-le-cout-des-grands-projets-it-de-l-etat-un-peu-mieux-maitrise-97718.html)
- Cour des comptes (2020) : projets IT de l'État jugés peu productifs — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-la-cour-des-comptes-juge-peu-productifs-les-projets-it-de-l-etat-95971.html) (détail non vérifié)
- Santé : priorités numériques 2027 fondées sur des « petits pas » contre l'effet tunnel — [Acteurs Publics](https://acteurspublics.fr/articles/les-nouvelles-priorites-du-numerique-en-sante-pour-2027)

### Inferences
- Modèle de décision : score = risque évité (probabilité × impact usagers/continuité) + coût de ne rien faire (RUN croissant) + alignement stratégique ; comparer avec projets métier sous contrainte de budget ; exports pour dossiers de tutelle (COM/CPOM, PLF/RAP, avis DINUM sur projets > 9 M€ [CG]).
- Indicateur de pilotage : trajectoire RUN/BUILD, dette en jours-homme et en €, nombre d'applications critiques hors support.

### Gaps
- Méthodes de justification budgétaire standard (ex. cadre de valeur, modèle de coût de la DINUM) : non trouvées.

## 7. Pratiques d'architecture (cible vs existant, trajectoires, ADR, principes, dérogations)

### Takeaway
Aucune source primaire n'a été trouvée dans cette session ; les pratiques ci-dessous sont [CG] ou inférées.

### Cited Findings
- Le cadre commun d'urbanisation et la doctrine sectorielle santé incarnent des principes et règles d'urbanisation applicables aux projets — [ANS](https://esante.gouv.fr/documents/doctrine_2_2_cadre_urbanisation-sectorielle-sante.pdf)
- [PUBLIC] IGF : recommande un pilotage haut niveau de la résorption de dette avec indicateurs — [IGF](https://www.igf.finances.gouv.fr/files/live/sites/igf/files/contributed/Rapports%20de%20mission/2022/2022-M-034-05_Rapport_COM_DGFIP.pdf)

### Inferences
- Objets : état actuel/cible/transition, roadmaps de migration, principes d'architecture, registre de décisions (ADR), registre de dérogations (écarts à la doctrine, par exemple cloud), analyses d'impact, comités d'architecture/revue de projets.
- Décisions : trajectoire d'urbanisation par îlot, séquencement des décommissionnements, arbitrage entre cible et dérogation temporaire.

### Gaps
- TOGAF ADM, ADR (Nygard), pratiques de comités d'architecture publics : non recherchés.

## 8. Objets oubliés : données, API, shadow IT, SaaS, licences, environnements, IA

### Takeaway
Plusieurs objets sont partiellement couverts par des initiatives publiques (API, SILL, Albert, doctrine cloud) mais n'ont pas de cartographie standard ; Odin doit les inclure comme objets de premier rang.

### Cited Findings
- API Particulier/Entreprise comme catalogue d'API certifiées à usage des administrations, accès par DataPass — [Gazette des communes](https://www.lagazettedescommunes.com/754302/les-api-ces-ponts-de-donnees-certifiees-qui-facilitent-la-vie/), [data.gouv](https://www.data.gouv.fr/fr/dataservices/api-particulier/)
- Albert, plateforme d'inférence IA de la DINUM (juillet 2024) — [Wikipedia DINUM](https://en.wikipedia.org/wiki/DINUM)
- Open source : la DGFiP a ouvert le code source du calcul de la taxe foncière — [next.ink](https://next.ink/6661/108152-bercy-ouvre-code-source-taxe-fonciere/) (titre seulement)
- La doctrine cloud manque d'indicateurs centralisés pour mesurer son application (revue DINUM janvier 2026) — [Solutions Numériques](https://www.solutions-numeriques.com/?p=248194)

### Inferences
- À ajouter au métamodèle : jeux de données et obligations d'ouverture (loi République numérique 2016 [CG], non sourcée ici), flux/API (catalogue, versions, SLA), dépendances entre applications et entre administrations, shadow IT et SaaS non référencés (détectés par finance/SSO), licences et contrats (échéances, audits éditeurs), environnements (prod/préprod/test), modèles IA et jeux d'entraînement (AI Act [CG], registre des systèmes IA), compétences/ETP par technologie.

### Gaps
- Aucune source sur shadow IT public, gestion des licences, loi République numérique, AI Act : à compléter.
- Chiffres 2026 du SILL non obtenus (dernier chiffre trouvé : environ 530 en 2025).
