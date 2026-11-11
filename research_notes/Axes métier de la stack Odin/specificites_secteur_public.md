# Spécificités du pilotage SI dans les organismes publics français (impacts sur Odin)

Date de rédaction : 2026-11-11. Méthode : recherches web (presse spécialisée, data.gouv, sites officiels) ; les rapports primaires (Cour des comptes, JO, Légifrance) n'ont pas tous été ouverts : les faits issus de la presse sont signalés comme tels et à vérifier. Les éléments non sourcés (connaissance générale du cadre LOLF, M57, marchés publics, etc.) sont placés en « Inférences » ou « Gaps », pas en « Cited Findings ».

## 1. Typologie des organismes publics clients et différences de besoins

### Takeaway
Le secteur public n'est pas un bloc : l'État (cadre décret 2019-1088 + DINUM), les collectivités (maturité très hétérogène, mutualisation via syndicats/EPCI) et la santé (programme CaRE, GHT, HDS) ont des cadres, des financeurs et des maturités différents. Odin doit être configurable par « profil d'organisme » (gabarits) plutôt que modélisé sur un seul type.

### Cited Findings
- La maturité cyber des collectivités est très inégale (grandes métropoles vs petites communes) et l'architecture locale de cybersécurité reste largement à construire (Cour des comptes, juin 2025, via presse) — [Banque des Territoires](https://www.banquedesterritoires.fr/les-cyberattaques-ciblent-de-plus-en-plus-les-collectivites-alerte-un-rapport-de-la-cour-des)
- La FNCCR estime que les structures de mutualisation informatique (syndicats, EPCI à fiscalité propre) auront un rôle clé dans la transformation numérique des petites collectivités ; un baromètre 2025 de France Urbaine pointe un besoin accru de mutualisation, notamment en cybersécurité — [Maire-info](https://www.maire-info.com/cybermalveillance/cybersecurite-une-strategie-en-direction-collectivites-mieux-structurer-selon-la-cour-comptes-article-29805) ; [Baromètre France Urbaine 2025](https://franceurbaine.org/app/uploads/2025/09/Barometre-de-maturite-numerique-2025.pdf)
- Quatre opérateurs publics de services numériques territoriaux ont annoncé vouloir mutualiser leurs forces dans les territoires — [Acteurs publics](https://acteurspublics.fr/articles/numerique-quatre-operateurs-publics-de-services-numeriques-veulent-mutualiser-les-forces-dans-les-territoires/)
- Santé : le programme CaRE (Cybersécurité, accélération et résilience des établissements) s'adresse aux GHT, établissements publics hors GHT et privés ; objectif d'investissement de 750 M€ d'ici 2027 dont 250 M€ jusqu'en 2025 ; 1 167 candidats au 2e appel (domaine 2, continuité/reprise d'activité) en novembre 2025 ; financement conditionné à l'atteinte d'objectifs par domaine et à un bilan financier — [ANS/esante.gouv.fr](https://esante.gouv.fr/espace-presse/cybersecurite-en-sante-1-167-candidats-au-deuxieme-appel-financement-du-programme-care) ; [ARS ARA](https://www.auvergne-rhone-alpes.ars.sante.fr/programme-care-en-auvergne-rhone-alpes)
- Mercator (cartographie SI open source, GPL) est déjà utilisé par des centres hospitaliers et des communes (chiffres auto-déclarés, SSTIC 2023) — [SSTIC 2023](https://www.sstic.org/media/SSTIC2023/SSTIC-actes/mercator_-_la_cartographie_des_systmes_dinformatio/SSTIC2023-Slides-mercator_-_la_cartographie_des_systmes_dinformation-barzin.pdf)

### Inferences
- Gabarits de profil suggérés : (a) ministère/direction centrale ; (b) opérateur de l'État ; (c) région/département/métropole (DSI structurée) ; (d) commune/EPCI sans architecte, souvent adhérente d'un syndicat mutualisé (le « client » est alors le syndicat, avec des dizaines/centaines de membres : besoin multi-entités/multi-tenant et refacturation) ; (e) organisme de sécurité sociale (cadre COG, pilotage par la caisse nationale) ; (f) GHT/hôpital (SI convergent, HDS, CaRE) ; (g) université (autonomie budgétaire, RCE).
- Une collectivité petite n'a pas de portefeuille de projets formalisé : Odin doit offrir un mode « léger » (checklist, questionnaires guidés) sans exiger un référentiel d'architecture.
- Mutualisation : modèle de données « entité utilisatrice / entité mutualisatrice » (services socle partagés, convention, quote-part) à prévoir.

### Gaps
- Tailles typiques de DSI (ETP) par catégorie d'organisme : non trouvées dans des sources fiables lors de cette recherche.
- Chiffres de maturité DSI hospitalière/GHT hors cyber (convergence SI) : non sourcés ici.

## 2. Cadre budgétaire et financier (LOLF, plafond d'emplois, collectivités, ETPT)

### Takeaway
Dans l'État, la ressource RH est contrainte par un plafond d'emplois exprimé en ETPT (moyenne annualisée) et un schéma d'emplois mesuré en ETP à fin d'année : les deux unités diffèrent, et un outil ETP « générique » est insuffisant. Les budgets sont annuels, structurés par programme (LOLF), avec des règles distinctes (M57, AP/CP) pour les collectivités.

### Cited Findings
- L'ETPT sert de base au calcul des plafonds d'emplois LOLF ; la consommation annuelle est la moyenne annualisée des ETPT mensuels, donc un mois peut dépasser le plafond sans le violer — [Assemblée nationale (rapport MEC)](https://www.assemblee-nationale.fr/13/pdf/cr-mec/10-11/c1011020.pdf) ; [AMUE glossaire LOLF](https://www.amue.fr/fileadmin/amue/ressources-humaines/documents-publications/lolf-gpems/glossaire_V2.pdf)
- Le plafond d'emplois (en ETPT) constitue l'autorisation parlementaire, propre à chaque ministère ; le schéma d'emplois est mesuré en ETP au 31 décembre — [Assemblée nationale](https://www.assemblee-nationale.fr/13/pdf/cr-mec/10-11/c1011020.pdf) ; [CFDT-UFETAM (exemple Cerema)](https://www.cfdt-ufetam.org/wp-content/uploads/2021/04/cerema_effectifs_reactualises_par_dt_31-12-20.pdf)
- Cour des comptes (2024) : il n'existe pas de vision consolidée de la dépense numérique de l'État, ce qui nuit au pilotage ; elle recommande de consolider les dépenses numériques sous l'égide de la DINUM — [Acteurs publics](https://acteurspublics.fr/articles/la-cour-des-comptes-sagace-de-ne-pas-pouvoir-evaluer-les-depenses-numeriques-de-letat) ; [Banque des Territoires](https://www.banquedesterritoires.fr/transformation-numerique-de-letat-la-dinum-doit-clarifier-son-assise-et-affirmer-sa-legitimite)
- L'ONP (opérateur national de paye) a coûté 346 M€ pour une valeur d'usage nulle (abandon) ; Louvois : gaspillage estimé 150-200 M€ — [Acteurs publics](https://acteurspublics.fr/articles/346-millions-deuros-investis-en-pure-perte-pour-le-logiciel-de-paie-des-fonctionnaires)

### Inferences
- (Connaissance générale, non sourcée dans cette session) LOLF : mission > programme > BOP > UO ; titres 2 (personnel), 3 (fonctionnement), 5 (investissement) ; AE/CP ; Chorus ; contrôleur budgétaire. Odin devrait permettre d'imputer chaque projet/service sur : programme/BOP/UO, titre, AE vs CP, et suivre l'échéancier de CP pluriannuel (un projet SI se pilote en AE engagées vs CP décaissés).
- Collectivités : sections fonctionnement/investissement, nomenclature M57 (généralisée), autorisations de programme/crédits de paiement (AP/CP), PPI (plan pluriannuel d'investissement), fonds de compensation TVA, subventions (ANCT, DETR/DSIL, France Relance). À valider par une source (M57/DGCL).
- Modélisation RH : stocker le même effectif sous trois mesures (ETP, ETPT, et ETP « prestataires ») ; suivre plafond d'emplois vs consommation, titulaires/contractuels/prestataires, et « arbitrage T2/T3 » (substituer des prestataires aux agents quand le plafond est atteint, ce qui masque le coût réel).
- Indicateurs de dérive : écart budgétaire et calendaire par projet (reprendre les définitions du Panorama DINUM).

### Gaps
- Textes officiels LOLF/M57/AP-CP/Chorus non consultés (définitions précises BOP/UO non obtenues) ; à compléter avec budget.gouv.fr et collectivites-locales.gouv.fr.
- Contrôle financier (contrôleur budgétaire et comptable ministériel) : non documenté ici.

## 3. Commande publique, logiciel libre, souveraineté des achats

### Takeaway
La commande publique est un objet de pilotage à part entière (échéances, centrale d'achat UGAP, contrôle DINUM sur les achats numériques, dépendance fournisseur). Le SILL et la doctrine open source structurent le choix des solutions.

### Cited Findings
- Un décret de mars 2026 donne à la DINUM un droit de regard sur les contrats SaaS des ministères ; les achats via l'UGAP sont concernés — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-les-contrats-saas-des-ministeres-sous-surveillance-de-la-dinum-99748.html) ; [Acteurs publics](https://acteurspublics.fr/articles/la-plupart-des-achats-numeriques-de-letat-devront-desormais-etre-controles-par-la-dinum/) ; [Acteurs publics](https://acteurspublics.fr/articles/le-gouvernement-officialise-les-nouveaux-pouvoirs-de-controle-de-la-dsi-de-letat/) (seuil SaaS corrigé par LMI : à vérifier)
- Marché « Nuage public » de l'UGAP : 84 M€ de commandes en 2025, dont 22 M€ sur offres SecNumCloud (+62 % en un an) ; 70 % des commandes vont à des acteurs européens référencés — [Acteurs publics](https://acteurspublics.fr/articles/letat-a-passe-84-millions-deuros-de-commandes-sur-le-marche-cloud-public-en-2025/)
- Cour des comptes (octobre 2026, via presse) : recommande une migration en 3-4 ans de la bureautique vers des logiciels libres en cloud pour réduire la dépendance à Microsoft ; les deux clouds interministériels de la DINUM (~55 M€ en neuf ans) restent peu utilisés ; marché UGAP Microsoft courant jusqu'en 2028 (source ancienne, à vérifier) ; marché Oracle UGAP restreint au support — [Techniques de l'Ingénieur/AFP](https://www.techniques-ingenieur.fr/actualite/breves-afp/la-cour-des-comptes-appelle-letat-a-reduire-sa-dependance-a-microsoft-165198/) ; [Banque des Territoires](https://www.banquedesterritoires.fr/souverainete-numerique-letat-victime-de-dependances-quil-lui-meme-creees) ; [LMI](https://www.lemondeinformatique.fr/actualites/lire-l-ugap-cantonne-le-marche-oracle-au-support-100260.html)
- SILL : liste de logiciels libres recommandés (depuis 2013, mise à jour en continu, ~530 logiciels selon une source 2025), publiée par la mission logiciels libres de la DINUM ; critères : code publié sous licence autorisée et déploiement par une DSI publique ; base légale citée : article 16 de la loi pour une République numérique (2016) — [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/socle-interministeriel-de-logiciels-libres/) ; [Blog du Modérateur](https://www.blogdumoderateur.com/logiciels-libres-recommandes-etat-2025/)

### Inferences
- Objets à modéliser : marché / accord-cadre / bon de commande UGAP, titulaire, date de notification, durée, reconductions, date limite de non-reconduction, préavis, seuil procédure, date cible de relance de la mise en concurrence (rétro-planning), montant engagé vs maximum de l'accord-cadre, clauses (RSE, sécurité, réversibilité, localisation données).
- Alertes : marché arrivant à échéance sans plan de remise en concurrence ; concentration fournisseur (part de budget par éditeur/ESN) ; logiciel hors SILL alors qu'un équivalent libre existe ; SaaS soumis à contrôle DINUM.
- Seuils de procédure (MAPA, formalisée) : à sourcer (code de la commande publique, seuils mis à jour par arrêté) ; non vérifié ici.

### Gaps
- Textes du code de la commande publique, seuils 2026 et durée maximale des marchés : non consultés.
- Politique de sobriété numérique (RGESN, loi REEN 2021) : non recherchée.
- Détail du décret de mars 2026 (références exactes, seuils) : non confirmé par source primaire.

## 4. Cadre stratégique et réglementaire spécifique

### Takeaway
Un socle réglementaire dense et daté s'impose : décret 2019-1088 (avis DINUM ≥ 9 M€), doctrine « cloud au centre » devenue obligation légale (SREN), NIS2 en cours de transposition. Odin doit porter ces règles comme des contrôles et des échéances.

### Cited Findings
- Décret 2019-1088 : les projets SI de l'État et des organismes sous tutelle dont le montant prévisionnel est ≥ 9 M€ TTC (arrêté du 5 juin 2020) nécessitent un avis conforme du directeur de la DINUM, saisi par le secrétaire général du ministère ; 30 jours calendaires si dossier complet ; évaluation sur 5 axes (stratégie, finances, gouvernance, réalisation, planning) ; les projets avisés sont suivis dans le Panorama semestriel — [Démarche DINUM](https://demarche.numerique.gouv.fr/commencer/demande-d-avis-conforme-dinum) ; [data.gouv.fr (avis DINUM)](https://www.data.gouv.fr/datasets/publication-des-avis-dinum-articles-3-et-7/) ; [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-3-8-mdeteuro-investis-dans-les-plus-grands-projets-it-de-l-etat-95550.html) ; [Landot Avocats](https://blog.landot-avocats.net/2020/07/26/quels-sont-les-systemes-dinformation-et-de-communication-qui-doivent-donner-lieu-a-avis-du-directeur-interministeriel-du-numerique/)
- Certains ministères ne sollicitent pas l'avis ou le font trop tard (Cour des comptes) — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-3-8-mdeteuro-investis-dans-les-plus-grands-projets-it-de-l-etat-95550.html)
- Doctrine « cloud au centre » : circulaire n° 6282-SG du 5 juillet 2021, mise à jour du 31 mai 2023 (clarification des données sensibles) ; données particulièrement sensibles → clouds internes de l'État ou offre qualifiée SecNumCloud — [Acteurs publics](https://acteurspublics.fr/articles/letat-affine-sa-doctrine-cloud-pour-sortir-du-flou-sur-la-definition-des-donnees-sensibles) ; [NumSpot](https://numspot.com/wp-content/uploads/2023/12/NumSpot-Ce-quil-faut-retenir-de-Cloud-au-centre.pdf)
- Loi SREN n° 2024-449 du 21 mai 2024 (art. 31) inscrit l'exigence SecNumCloud dans la loi pour les administrations ; décret d'application publié au JO le 16 avril 2026 (selon Acteurs publics) ; extension aux collectivités > 30 000 habitants évoquée en commission, adoption non confirmée — [Acteurs publics](https://acteurspublics.fr/articles/pour-les-administrations-lobligation-du-referentiel-secnumcloud-desormais-inscrite-dans-le-droit) ; [Acteurs publics](https://acteurspublics.fr/articles/letat-clarifie-enfin-la-liste-des-entites-concernees-par-la-loi-sren/)
- NIS2 : le projet de loi « résilience » n'est pas promulgué à la date de recherche ; renvoi de la France devant la CJUE le 9 juillet 2026 ; retour à l'Assemblée annoncé le 9 novembre 2026 ; périmètre pour les collectivités incertain ; sources divergent sur certaines dates — [Leto](https://www.leto.legal/news/nis-2-projet-loi-resilience-assemblee-nationale-9-novembre-2026) ; [Maire-info](https://www.maire-info.com/2026/cybermalveillance/directive-nis-2-deux-ans-retard-un-perimetre-dapplication-toujours-incertain-pour-les-collectivites-art26-31146) ; [it-connect](https://www.it-connect.fr/nis2-transposition-france-saisine-cjue/)
- Cour des comptes (juillet 2024) : instabilité organisationnelle du pilotage numérique de l'État, DINUM à légitimer ; la Cour plaidait pour un droit de veto de la DINUM, non repris dans la révision du décret — [Banque des Territoires](https://www.banquedesterritoires.fr/transformation-numerique-de-letat-la-dinum-doit-clarifier-son-assise-et-affirmer-sa-legitimite) ; [Acteurs publics](https://acteurspublics.fr/articles/la-cour-des-comptes-voudrait-que-la-dsi-de-letat-pese-davantage-sur-les-grands-projets-informatiques-des-ministeres)
- ANSSI : le guide de cartographie du SI est le cadre de référence de Mercator ; un projet de référentiel « Cyber France » ferait de la cartographie un prérequis NIS2 (source secondaire) — [GitHub Mercator](https://github.com/dbarzin/mercator) ; [Legiscope](https://www.legiscope.com/blog/category/cybersecurity.html)

### Inferences
- Objets réglementaires à porter dans Odin : « obligation » (texte, date, périmètre applicable selon type d'organisme) -> « contrôle/exigence » -> « statut de conformité par système/projet » -> « échéance ». Les textes cités par l'utilisateur (RGS, PSSIE, RGI, RGAA, DSFR, loi République numérique, SDG, « Dites-le-nous une fois », FranceConnect, eIDAS 2, Data Act) n'ont pas été sourcés ici : voir Gaps.
- Applicabilité différenciée : ce qui s'applique à l'État (décret 2019-1088, PSSIE) ne s'applique pas automatiquement aux collectivités/hôpitaux ; chaque exigence doit porter son périmètre.
- Une « jauge de seuil 9 M€ » (alerte quand le coût prévisionnel d'un projet d'une tutelle État approche ou dépasse le seuil TTC) est une fonction concrète.

### Gaps
- Non vérifiés faute de sources dans cette session : RGS (version en vigueur), PSSIE (2014, mises à jour), RGI, RGAA 4.x et obligations de publication (loi 2005, directive accessibilité), DSFR, article 6 loi République numérique (algorithmes/ open data), Data Governance Act/Data Act, SDG (« Once-Only »), eIDAS 2 / portefeuille EUDI, FranceConnect/ « Dites-le-nous une fois ». À compléter via legifrance.gouv.fr, numerique.gouv.fr, cyber.gouv.fr.
- Texte consolidé actuel du décret 2019-1088 et modifications 2026 : non consulté.

## 5. Pilotage par les démarches et services publics

### Takeaway
Les SI publics se justifient par des démarches et des politiques publiques : l'Observatoire de la qualité des démarches en ligne (DINUM) suit les démarches essentielles avec des critères publics. Odin doit pouvoir lier SI, démarches, missions et criticité par continuité de service.

### Cited Findings
- L'observatoire « Vos démarches essentielles » (DINUM, lancé juin 2019) suit environ 250 démarches les plus utilisées, bilan trimestriel, huit critères initiaux (satisfaction, niveau de service, accessibilité...), refonte ultérieure à 5 critères clés ; l'observatoire a été renommé sans changement d'objectif (nouveau nom non vérifié) — [data.gouv.fr](https://www.data.gouv.fr/datasets/observatoire-de-la-qualite-des-demarches-en-ligne/informations) ; [Sénat r24-895](https://www.senat.fr/rap/r24-895/r24-89510.html) ; [Banque des Territoires](https://www.banquedesterritoires.fr/la-dinum-detaille-sa-feuille-de-route-pour-les-formalites-essentielles-dici-2026) ; [Acteurs publics](https://acteurspublics.fr/articles/dematerialisation-des-demarches-une-nouvelle-methode-devaluation-pour-gagner-en-qualite%C2%A0)
- L'accessibilité des démarches est qualifiée de « gros point noir » de la dématérialisation — [Acteurs publics](https://acteurspublics.fr/articles/laccessibilite-des-demarches-reste-le-gros-point-noir-de-la-dematerialisation/)
- Note DINUM sur la qualité des services numériques (juillet 2023) — [Système de design de l'État](https://www.systeme-de-design.gouv.fr/uploads/3_Note_DINUM_qualite_des_services_numeriques_17_07_2023_9bd158313d.pdf)

### Inferences
- Chaîne de valeur à modéliser : politique publique/mission -> démarche/service -> applications/composants -> infrastructure/fournisseurs ; chaque démarche a un indicateur de qualité (satisfaction, taux de dématérialisation, accessibilité, délai) rattaché.
- Criticité = continuité du service public (RTO/RPO par démarche, usagers concernés, obligations légales de service), distincte de la criticité technique ; elle alimente priorisation de la dette et PCA/PRA.
- Service-Public+ : non documenté ici (voir Gaps).

### Gaps
- Service-Public+ (indicateurs, périmètre), nom actuel de l'observatoire, indicateurs précis : non confirmés.
- Lien officiel démarches essentielles ↔ SI de support : non trouvé.

## 6. Gouvernance politique et contrôle externe

### Takeaway
Les arbitrages dépendent des élus, du calendrier électoral et de contrôleurs externes (Cour des comptes, DINUM, CNIL, ANSSI) ; Odin doit tracer les décisions, les avis obligatoires et le suivi des recommandations de contrôle.

### Cited Findings
- Les ministères contestent par évitement le contrôle DINUM (avis tardifs ou non demandés) ; la Cour juge le pilotage organisationnellement instable — voir §4.
- Les rapports du Panorama sont transmis semestriellement au Premier ministre : suivi de 54 projets pour ~4 Md€ (chiffre non daté dans la source) ; écart budgétaire moyen 10,8 % en décembre 2023 contre 24 % un an plus tôt et 32 % en 2016 — [Assemblée nationale (QE)](https://www.assemblee-nationale.fr/dyn/16/questions/QANR5L16QE6412.pdf) ; [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lireamp-le-cout-des-grands-projets-it-de-l-etat-un-peu-mieux-maitrise-97718.html)
- Rapport de la Cour des comptes sur le pilotage de la DINUM : 10 juillet 2024 — [Acteurs publics](https://acteurspublics.fr/articles/la-direction-du-numerique-de-letat-un-chef-dorchestre-des-ministeres-en-mal-dassise)

### Inferences
- Le calendrier électoral (municipales mars 2026 déjà passées ; présidentielle 2027 ; départementales/régionales à venir) conditionne : gel de lancement, restitution de mandat, rapport de fin de mandat, nouvelles priorités d'élus. Odin devrait gérer des « mandats/législatures » comme jalons de roadmap, avec scénarios avant/après échéance.
- Objets : décision/arbitrage (qui, quand, motif, instance : COMEX, comité de pilotage, commission d'élus), avis obligatoires (DINUM, CNIL/DPO, RSSI), recommandations de contrôle (Cour, CRC, IGA, IGF) avec suivi de mise en oeuvre.
- Calendrier électoral et rôle des élus : non sourcés dans cette session.

### Gaps
- Mécanismes CRC/IGF/IGA/CNIL et calendrier électoral précis : non recherchés avec sources.

## 7. Ressources humaines publiques

### Takeaway
Les référentiels de métiers ont changé (RIME remplacé par le RMFP) ; la filière numérique de l'État a un référentiel de rémunération de 55 métiers (circulaire du 3 janvier 2024). La dépendance aux prestataires et le plafond d'emplois imposent un suivi spécifique.

### Cited Findings
- Circulaire n° 6434/SG du 3 janvier 2024 : politique salariale interministérielle de la filière numérique, référentiel de rémunération de 55 métiers, élaboré par DINUM, DGAFP et direction du budget ; plafonds remplacés par des fourchettes ; alignement sur le répertoire commun aux trois versants — [Fonction publique](https://www.fonction-publique.gouv.fr/files/files/actualites/circulaire_numero_6434-sg_referentiel_numerique.pdf) ; [Fonction publique (actualité)](https://www.fonction-publique.gouv.fr/index%2Ephp/toutes-les-actualites/le-referentiel-de-remuneration-des-metiers-du-numerique-est-mis-jour)
- Le RMFP (répertoire des métiers de la fonction publique, en place depuis septembre 2023) remplace le RIME pour l'État et couvre les trois versants — [Weka](https://www.weka.fr/actualite/?p=176584) ; [Fonction publique](https://www.fonction-publique.gouv.fr/files/files/ArchivePortailFP/www.fonction-publique.gouv.fr/biep/referentiel-des-metiers-de-la-fonction-publique.html)
- Un référentiel de compétences numérique écoresponsable couvre 56 métiers du numérique (fin 2024) ; écart 55/56 non expliqué dans les sources — [Acteurs publics](https://acteurspublics.fr/articles/un-referentiel-pour-identifier-et-valoriser-les-competences-numerique-durable-des-agents/)
- Étude sur métiers/contrats/répartition des forces vives numériques de l'État — [Acteurs publics](https://acteurspublics.fr/articles/metiers-contrats-repartition-les-forces-vives-du-numerique-de-letat-a-la-loupe) ; politique salariale pour attirer et fidéliser — [Acteurs publics](https://acteurspublics.fr/articles/letat-muscle-sa-politique-salariale-pour-attirer-et-fideliser-les-forces-vives-du-numerique)
- Surcoût et dépendance aux prestataires : un rapport sénatorial décrit une forte dépendance aux prestataires et une opacité croissante des dépenses — [Sénat r16-076](https://www.senat.fr/rap/r16-076/r16-0761.html)

### Inferences
- Modèle : poste/ETP rattaché à un code métier RMFP (et CNFPT pour la territoriale, non sourcé), statut (titulaire/contractuel CDD-CDI/prestataire/apprenti), catégorie A/B/C, vacance de poste, ancienneté de vacance, rémunération vs fourchette (écart d'attractivité), taux de rotation, ratio agents/prestataires par domaine, compétences rares (cyber, data, architecture).
- GPEEC : projection départs en retraite, besoins par métier à 3 ans.
- Les codes de la nomenclature interministérielle DINUM ne doivent pas être codés en dur ; prévoir un référentiel paramétrable versionné.

### Gaps
- Référentiel CNFPT (RMM/FPT) non vérifié ; règles précises contractuels/titulaires, « article 4/6 loi 84-16 » : non consultées.
- Données chiffrées sur le recours aux ESN dans la fonction publique : absentes.

## 8. Contraintes d'exploitation et non fonctionnelles structurantes (souveraineté, hébergement, accessibilité, licence)

### Takeaway
Pour être déployable chez des organismes publics, Odin doit viser : hébergement qualifié SecNumCloud (ou on-premise) quand il traite des données sensibles, accessibilité RGAA, DSFR, licence ouverte et réversibilité. Ces points sont des critères d'éligibilité, pas des options.

### Cited Findings
- Doctrine « cloud au centre » et loi SREN : SecNumCloud obligatoire pour les données particulièrement sensibles des administrations (§4).
- Marché UGAP Nuage public : 22 M€ SecNumCloud en 2025 (§3), preuve que les offres qualifiées sont achetées.
- Mercator, concurrent/complément open source GPL, offre une base interopérable avec le guide ANSSI — [GitHub](https://github.com/dbarzin/mercator) ; [LinuxFr](https://linuxfr.org/news/mercator-cartographie-de-si-open-source)
- Santé : le programme CaRE conditionne ses financements à des objectifs de sécurité ; hébergement HDS (non sourcé ici) — [ANS](https://esante.gouv.fr/espace-presse/cybersecurite-en-sante-1-167-candidats-au-deuxieme-appel-financement-du-programme-care)

### Inferences
- Modes de déploiement à prévoir : SaaS souverain qualifié SecNumCloud, on-premise/cloud privé, mode déconnecté (import/export de fichiers) pour réseaux restreints (diffusion restreinte, IGI 1300 : non sourcé ici).
- Les données d'Odin (cartographie, vulnérabilités, plans de continuité, effectifs) sont elles-mêmes sensibles -> chiffrement, cloisonnement par entité, journalisation, droit à l'effacement, gestion des habilitations ; l'outil doit éviter d'être un « risque concentré » (agrégation d'informations de sécurité).
- Interface utilisateur : conformité RGAA et DSFR (si utilisateurs agents de l'État) ; obligation légale de déclaration d'accessibilité (non sourcé).
- Licence ouverte (copyleft ou permissive) et inscription possible au SILL ; réversibilité et export de données (formats ouverts, API) alignés sur le référentiel de clauses marché.
- Authentification : ProConnect/agents (non sourcé), SSO SAML/OIDC, annuaires AD/LDAP.

### Gaps
- Exigences exactes HDS, IGI 1300, II 901, RGAA 4.1, DSFR : non vérifiées. Texte de qualification SecNumCloud 3.2 : non consulté.

## 9. Écosystème d'outils publics existants (interfaçage / concurrence)

### Takeaway
Mercator (cartographie, open source, ANSSI-aligné), le Panorama DINUM (data.gouv.fr), l'Observatoire des démarches, le SILL et les outils de la DINUM sont les références publiques réellement vérifiées ; « Mon Suivi Grands Projets » n'a pas été retrouvé.

### Cited Findings
- Mercator : web app Laravel/PHP, licence GPL, développée par Didier Barzin, alignée sur le guide de cartographie ANSSI ; vues : écosystème, processus métiers, applications, administration, infrastructure logique, etc. ; Meilleur projet open source OW2 2024 (déclaratif) — [LinuxFr](https://linuxfr.org/news/mercator-cartographie-de-si-open-source) ; [dbarzin.github.io/mercator](https://dbarzin.github.io/mercator) ; [Hack.lu 2024](https://archive.hack.lu/media/hack-lu-2024/submissions/TNXGJL/resources/20241025_Merc_8kHmyX4.pdf)
- Panorama des grands projets numériques de l'État : jeu de données sur data.gouv.fr (fichier ouvert incomplet : écarts de coûts/planning absents selon un commentaire) ; publication DINUM semestrielle — [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/panorama-des-grands-projets-si-de-letat-1/) ; [discussions](https://www.data.gouv.fr/datasets/panorama-des-grands-projets-numeriques-de-letat/discussions)
- Publication des avis DINUM (art. 3 et 7) en open data — [data.gouv.fr](https://www.data.gouv.fr/datasets/publication-des-avis-dinum-articles-3-et-7/)
- Observatoire de la qualité des démarches en ligne en open data — [data.gouv.fr](https://www.data.gouv.fr/datasets/observatoire-de-la-qualite-des-demarches-en-ligne/informations)
- SILL en open data — [data.gouv.fr](https://www.data.gouv.fr/fr/datasets/socle-interministeriel-de-logiciels-libres/)

### Inferences
- Intégrations possibles : import Mercator (export/API) pour objets de cartographie ; ingestion open data Panorama/avis DINUM comme benchmark de dérive ; import SILL pour qualifier le portefeuille logiciel ; connecteurs vers Chorus, SIRH, ITSM (non sourcés).
- Odin ne doit pas dupliquer Mercator (cartographie technique détaillée) mais exploiter son modèle comme source ; son créneau est la décision stratégique (dette, portefeuille, ressources, conformité) au-dessus de la cartographie.

### Gaps
- Non vérifiés : « Mon Suivi Grands Projets » (aucune trace), LASUITE numérique (suite collaborative, rapport Cour octobre 2026 sur bureautique mentionné), annuaires, « Cartographie des SI ministériels », offres d'éditeurs collectivités (Berger-Levrault, Cosoluce, JVS, Ciril, etc.) et leurs fonctions de pilotage SI : aucune source consultée.

## 10. Retours sur échecs et réussites de grands projets SI publics

### Takeaway
Les causes récurrentes sont organisationnelles plus que techniques : absence de responsable unique, gouvernance éclatée, pilotes sans expérience, dépendance prestataires, avis tardif ou évité. Le suivi des écarts s'est amélioré (écart budgétaire moyen de 32 % en 2016 à 10,8 % fin 2023).

### Cited Findings
- Cour des comptes sur Louvois/ONP/Cassiopée : 11 recommandations (rapport à la demande de la commission des finances du Sénat) ; causes : défaut d'organisation (ceux qui maîtrisent les leviers ne portent pas la responsabilité budgétaire), absence d'autorité centrale responsable, chef de mission préparatoire sans expérience des grands projets — [Vie-publique](https://www.vie-publique.fr/rapport/276699-la-conduite-des-grands-projets-numeriques-de-l-etat) ; [Acteurs publics](https://acteurspublics.fr/articles/onp-louvois-sirhen-pourquoi-matignon-peine-a-controler-les-projets-informatiques-de-letat)
- ONP : 346 M€ investis pour une valeur d'usage nulle — [Acteurs publics](https://acteurspublics.fr/articles/346-millions-deuros-investis-en-pure-perte-pour-le-logiciel-de-paie-des-fonctionnaires) ; [LMI](https://www.lemondeinformatique.fr/actualites/lire-si-paye-de-l-etat-346-meteuro-pour-une-valeur-d-usage-nulle-60217.html)
- Scribe (ministère de l'Intérieur) : « naufrage financier » selon la presse — [LMI](https://www.lemondeinformatique.fr/actualites/lire-le-naufrage-financier-du-projet-xpn-scribe-du-ministere-de-l-interieur-98731.html)
- Sénat : portefeuille d'applications fragmenté, forte dépendance aux prestataires, opacité des dépenses — [Sénat](https://www.senat.fr/rap/r16-076/r16-0761.html)
- Panorama : projets plus longs/coûteux avant amélioration ; écart budgétaire moyen 10,8 % (déc. 2023) — [Acteurs publics](https://acteurspublics.fr/articles/des-projets-informatiques-de-letat-toujours-plus-longs-et-couteux/) ; [LMI](https://www.lemondeinformatique.fr/actualites/lireamp-le-cout-des-grands-projets-it-de-l-etat-un-peu-mieux-maitrise-97718.html)
- Cybersécurité hospitalière : réponse jugée tardive et incomplète par la Cour — [Banque des Territoires](https://www.banquedesterritoires.fr/cybersecurite-des-etablissements-de-sante-une-reponse-tardive-et-incomplete-juge-la-cour-des)

### Inferences
- Signaux d'alerte à encoder (inspirés des causes) : absence de sponsor/responsable unique nommé ; avis DINUM/CNIL/RSSI manquant ou tardif ; écart budget/planning > seuil ; dépendance prestataire (% effort externe) ; reforme concomitante (collision de projets sur même périmètre métier) ; dette technique sur le SI cible ; manque de compétences clés (vacance de postes sur projets critiques).
- Louvois/ONP : projets de paie/RH – l'impact sur les agents (continuité de service) illustre le lien criticité–service public.
- Cheops, France Identité, SI Sécurité sociale : non documentés ici (voir Gaps).

### Gaps
- Rapports primaires de la Cour (Louvois référé 2014, ONP 2015, SI Sécurité sociale, Cheops, France Identité) non ouverts ; chiffres et causes à confirmer à la source.

## 11. Capacités propres au secteur public à intégrer dans Odin (liste consolidée)

Légende : [S] = appuyé par une source citée ci-dessus ; [I] = inférence/à valider.

1. Profils d'organisme (État, opérateur, collectivité, EPCI/syndicat mutualisé, sécu, hôpital/GHT, université) avec gabarits d'objets, d'indicateurs et de contrôles ; mode léger pour petites collectivités et mode multi-entités pour structures mutualisatrices [S/I §1].
2. Registre réglementaire daté et paramétrable (texte, date d'entrée en vigueur, périmètre applicable par type d'organisme, statut de conformité, échéance) : décret 2019-1088, cloud au centre, SREN/SecNumCloud, NIS2 (statut en transposition), RGS/PSSIE/RGAA/RGI [S §4, I pour le reste].
3. Suivi des avis obligatoires et de la jauge de seuil 9 M€ TTC (avis conforme DINUM, délai de 30 jours, 5 axes de lecture) et des avis CNIL/ANSSI/DPO [S §4].
4. Benchmark de dérive des projets (écart budget/planning) calibré sur le Panorama DINUM ; alertes précoces issues des causes d'échec (sponsor, gouvernance, dépendance prestataires, avis tardif) [S §10].
5. Imputation budgétaire publique : LOLF (programme/BOP/UO, titres, AE/CP) pour l'État ; M57, sections, AP/CP, PPI pour les collectivités ; vision consolidée de la dépense numérique (manque relevé par la Cour) [S/I §2].
6. Modèle RH public : ETP vs ETPT vs schéma d'emplois vs plafond d'emplois ; statuts (titulaires, contractuels, prestataires) ; codes métiers RMFP (RIME obsolète) ; fourchettes de rémunération ; vacance de postes ; GPEEC [S/I §2, §7].
7. Suivi de la dépendance aux prestataires/ESN et aux éditeurs (concentration, part régie vs forfait) [S/I §3, §7].
8. Module commande publique : calendrier des marchés/accords-cadres/commandes UGAP, échéances et rétro-planning de remise en concurrence, clauses RSE/sécurité/réversibilité, contrôle DINUM des contrats SaaS [S/I §3].
9. Qualification du portefeuille logiciel : statut SILL/libre, souveraineté (SecNumCloud, juridiction), dépendance Microsoft/Oracle, scénarios de sortie [S §3].
10. Lien services publics : politique publique -> démarche -> application ; indicateurs de qualité (observatoire des démarches : satisfaction, accessibilité, etc.) ; criticité par continuité du service public (RTO/RPO) [S/I §5].
11. Gouvernance politique : instances, arbitrages tracés, jalons de mandat/calendrier électoral, scénarios de roadmap, reporting aux tutelles (rapports/présentations pour élus, comité de direction) [I §6].
12. Suivi des recommandations de contrôle externe (Cour des comptes, CRC, IGA/IGF, CNIL, ANSSI) avec plans d'action [I §6].
13. Santé : suivi des domaines et jalons de financement CaRE, convergence SI de GHT, HDS [S/I §1].
14. Interfaces publiques : import Mercator, ingestion open data (Panorama, avis DINUM, SILL, observatoire), export vers formats ouverts [S §9].
15. Exigences non fonctionnelles structurantes : hébergement SecNumCloud ou on-premise, mode déconnecté, cloisonnement/chiffrement des données sensibles, RGAA/DSFR, licence ouverte/SILL, réversibilité et export, intégration SSO publique [I, §8].
16. Gestion de la mutualisation (syndicats informatiques, DSI communes) : services partagés, quote-parts, convention, refacturation [I §1].

Points de vigilance globaux : chiffres de presse à recouper avec rapports primaires ; NIS2/loi résilience non promulguée à la date de recherche ; plusieurs textes cités par la demande (RGS, PSSIE, RGI, RGAA, DSFR, eIDAS 2, Data Act, SDG, FranceConnect, IGI 1300, HDS, M57, seuils marchés) restent à sourcer.
