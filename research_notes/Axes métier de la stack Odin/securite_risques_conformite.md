# Sécurité, risques, conformité, continuité, gouvernance données/IA et numérique responsable : axes d'Odin pour les organismes publics (état au 11 nov. 2026)

Note de méthode : recherche limitée (~18 appels). Les faits cités proviennent de résumés de résultats de recherche/pages récupérées ; les sources secondaires (cabinets, médias) sont signalées. Les éléments issus de connaissances générales non vérifiées dans cette session sont placés en « Inférences » ou « Gaps » et marqués « à vérifier ».

## 1. Obligations réglementaires fin 2026 : NIS2 / loi Résilience (état exact)

### Takeaway
Au 11 novembre 2026 la loi Résilience (transposition NIS2 + REC + volet DORA) n'est PAS promulguée : adoptée au Sénat en mars 2025, elle est en discussion en séance à l'Assemblée nationale depuis le 9 novembre 2026 (débats jusqu'au 13), après deux reports ; aucune obligation NIS2 n'est donc applicable en droit français, et la France est renvoyée devant la CJUE. Pour les collectivités : périmètre élargi mais amendes exclues.

### Cited Findings
- Texte examiné au Sénat en séance en mars 2025 ; discussion publique à l'AN à partir du lundi 9 novembre 2026 (texte de commission spéciale n°1779), débats prévus jusqu'au 13 novembre ; texte attendu en juillet 2026, reporté à octobre puis retiré de l'ordre du jour le 6 octobre 2026 ; CMP possible ensuite, sans date — [Leto](https://www.leto.legal/news/nis-2-projet-loi-resilience-assemblee-nationale-9-novembre-2026)
- Les obligations NIS2 ne s'appliquent pas en droit français tant que la loi n'est pas promulguée ; l'ANSSI envisage une conformité complète des entités vers fin 2028 ; Titre Ier : plans de résilience pour opérateurs et ~1 500 points d'importance vitale ; Titre II : NIS2 passe de 6 à 18 secteurs — [Leto](https://www.leto.legal/news/nis-2-projet-loi-resilience-assemblee-nationale-9-novembre-2026)
- Transposition due le 17 octobre 2024 ; la Commission a saisi la CJUE (8 juillet 2026 selon une source) — [Maire-info](https://www.maire-info.com/2026/cybermalveillance/directive-nis-2-deux-ans-retard-un-perimetre-dapplication-toujours-incertain-pour-les-collectivites-art26-31146) ; [IT-Connect](https://www.it-connect.fr/nis2-transposition-france-saisine-cjue/)
- Une page (Legiscope) affirme une adoption définitive en 2025 : contredite par toutes les autres sources, à écarter — [Legiscope](https://www.legiscope.com/blog/transposition-nis2-france.html)
- Collectivités « entités essentielles » : régions, départements, communes > 30 000 hab., communautés urbaines/d'agglomération, métropoles, SDIS, centres de gestion ; « importantes » : surtout communautés de communes et leurs établissements publics administratifs ; inscription auprès de l'ANSSI ; notification d'incident 24 h / 72 h / 1 mois ; collectivités expressément exclues des amendes ; l'AMF demande des ajustements ; périmètre final inconnu avant adoption — [Maire-info](https://www.maire-info.com/2026/cybermalveillance/directive-nis-2-deux-ans-retard-un-perimetre-dapplication-toujours-incertain-pour-les-collectivites-art26-31146)
- Sanctions : amende administrative pour entités essentielles/importantes hors administrations et collectivités ; pour les essentielles, interdiction temporaire d'exercer des fonctions dirigeantes en dernier recours ; le Conseil d'État a jugé l'exclusion difficilement admissible ; un amendement proposait plan de remédiation + amende plafonnée à 10 M€ (sort inconnu) — [Banque des Territoires](https://www.banquedesterritoires.fr/cybersecurite-le-senat-inscrit-laccompagnement-des-collectivites-dans-le-texte) (via recherche) ; [Maire-info](https://www.maire-info.com/cybersecurite-la-transposition-de-la-directive-nis-2-enfin-en-route-article2-29024)
- Fonds d'accompagnement des collectivités ajouté en commission AN mais non financé en 2027 selon la ministre — [Maire-info](https://www.maire-info.com/2026/cybermalveillance/directive-nis-2-deux-ans-retard-un-perimetre-dapplication-toujours-incertain-pour-les-collectivites-art26-31146)
- ReCyF (référentiel de cybersécurité de l'ANSSI, art. 14 du projet de loi) publié le 17 mars 2026 (v2.5 suivie du changelog 2.4→2.5), non obligatoire, utilisable par anticipation, proportionnalité selon la maturité ; comptage des objectifs divergent selon sources (15 + 5 supplémentaires pour essentielles vs « dix ») — [Next](https://next.ink/229605/nis-2-lanssi-publie-son-recyf-la-csnp-simpatiente-et-le-fait-savoir/) ; [ANSSI messervices](https://messervices.cyber.gouv.fr/documents-ressources/20260317_NIS_V2_Suivi%20des%20modifications%20ReCyF%20v2.4%20vers%20v2.5-vfinale.pdf)
- ANSSI annonce un référentiel de « mesures basiques » à venir sur MesServicesCyber — [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lireamp-l-anssi-publie-un-referentiel-accompagnant-la-conformite-nis2-99753.html)

### Inferences
- Odin doit modéliser NIS2 comme « obligation anticipée » (statut : non en vigueur, date d'application inconnue) avec mapping ReCyF ↔ mesures, plutôt qu'un statut de conformité légale ; prévoir un champ « statut juridique de l'obligation » mis à jour par veille.
- Objets à suivre : catégorie d'entité (essentielle/importante/hors champ, avec incertitude), enregistrement ANSSI, processus de notification 24h/72h/1 mois, désignation de la gouvernance (dirigeant responsable), écarts vs ReCyF.
- Spécificité publique : pas d'amende pour collectivités/administrations mais responsabilité politique/réputationnelle et suspension possible des dirigeants (essentielles) à vérifier dans le texte final.

### Gaps
- Texte final (vote AN, CMP, promulgation) inconnu à la date : à re-vérifier avant livraison ; périmètre exact des administrations de l'État (plutôt traité via la feuille de route État, voir §2), établissements publics et hôpitaux non détaillés.
- Plafonds de sanctions (10 M€/2 % etc.) non confirmés ici.

## 2. Référentiels de pilotage sécurité côté État et public (PSSIE, feuille de route, homologation, SecNumCloud, CaRE, MonServiceSécurisé)

### Takeaway
L'État pilote via la feuille de route annuelle 2026-2027 (publiée 9 avril 2026) qui prépare NIS2 : homologation prioritaire des SI à enjeux d'ici fin 2026, MFA admin au 31/12/2026, mise à jour de la PSSIE au plus tard T1 2027. SecNumCloud 3.2 a été formellement approuvé par arrêté du 12 août 2026. Les hôpitaux relèvent du programme CaRE, les collectivités du parcours ANSSI/MonServiceSécurisé.

### Cited Findings
- Feuille de route 2026-2027 publiée le 9 avril 2026 (cadre IGI n°1337, validée par COSINUS), prépare la conformité NIS2 des administrations ; ~10 axes ; homologation prioritaire des SI à enjeux d'ici fin 2026 ; PSSI de l'État à mettre à jour au plus tard T1 2027 ; MFA des comptes admin et postes d'administration dédiés au 31/12/2026 ; DNS avant 30/09/2026 ; « conseiller numérique » cyber dans les cabinets avant fin 2026 ; échéances jusqu'en 2030 ; les ministères déclinent leur propre feuille de route — [ANSSI](https://cyber.gouv.fr/actualites/feuille-de-route-des-efforts-prioritaires-en-matiere-de-securite-numerique-de-letat-2026-2027) (via recherche), [COMCYBER](https://www.defense.gouv.fr/comcyber/actualites/feuille-route-cyber-letat-2026-2027-renforcer-resilience-numerique), [Leto](https://www.leto.legal/news/cybersecurite-etat-feuille-route-nis2-2030). Divergences de décompte (40 actions vs 10 chantiers/100 échéances) ; EDR/XDR généralisé fin 2026 uniquement attesté par un blog de conseil (non confirmé).
- PSSIE v1.0 : circulaire PM n°5725/SG du 17 juillet 2014 ; cadre de 2022 : arrêté du 26 octobre 2022 approuvant l'IGI 1337/SGDSN/ANSSI (décret 2022-513) — [résultats de recherche PSSIE] ; pas de nouvelle PSSIE publiée confirmée à ce jour
- SecNumCloud : arrêté du 12 août 2026 (NOR PRMD2617964A) approuvant le référentiel v3.2 ; s'applique aux prestataires cloud servant l'État, ses administrations, opérateurs et GIP pour données particulièrement sensibles ; conformité par qualification ANSSI ou certification UE/EEE reconnue équivalente — [Landot Avocats](https://blog.landot-avocats.net/2026/08/17/important-notamment-pour-certains-marches-publics-evolution-du-referentiel-dexigences-relatif-aux-prestataires-de-services-dinformatique-en-nuage/amp/). Source tierce indique version 3.2 datée de mars 2022 sans version postérieure confirmée : divergence de dates (3.2 existait déjà en 2022 ; l'arrêté 2026 serait l'approbation formelle) — [Outscale/3DS](https://www.3ds.com/newsroom/press-releases/outscale-first-cloud-qualified-secnumcloud-32)
- Cloud au centre : circulaire PM de juillet 2021, renforcée en 2023, ancrée par loi SREN de mai 2024 — [AFNOR](https://www.afnor.org/en/news/secnumcloud-passport-for-trusted-cloud-offerings) (imprécis, à vérifier)
- MonServiceSécurisé (ANSSI) : outil gratuit pour entités publiques, surtout collectivités, pour homologuer sites, apps, API (parcours en 3 étapes, page d'homologation, synthèse PDF) ; guide d'homologation web (04/2025) — [Solutions Numériques](https://www.solutions-numeriques.com/?p=173699) ; [guide ANSSI](https://messervices.cyber.gouv.fr/documents-guides/guide-homologation-securite-web-04-2025.pdf)
- Parcours de cybersécurité ANSSI (France Relance, 2021) : 100 M€ sur 176 M€ ; ~75 % des bénéficiaires sont des collectivités — [Banque des Territoires](https://www.banquedesterritoires.fr/les-parcours-cyber-de-lanssi-lheure-du-bilan-75-des-beneficiaires-sont-des-collectivites)
- Stratégie nationale cybersécurité 2026-2030 présentée le 28 janvier 2026, avec guichet unique (absorbant à terme 17Cyber) — [Banque des Territoires](https://www.banquedesterritoires.fr/cybersecurite-le-gouvernement-lance-un-guichet-unique-sur-un-paysage-inchange)
- CaRE (santé) : lancé décembre 2023, pilotage DNS/ANS/ANSSI/DGOS, plan 2023-2027 ; 3e appel à financement lancé janvier 2026 ; guichet paiement D1 clos 30/06/2026 ; Conseil d'État rejette le recours FHP le 17/07/2026 ; enquête auprès de 719 directeurs sur perception du risque cyber ; kit d'exercice de crise cyber — [ANS esante.gouv.fr](https://esante.gouv.fr/strategie-nationale/cybersecurite) ; [FHF](https://www.fhf.fr/actualites/articles/cybersecurite-le-conseil-detat-conforte-des-financements-adaptes-aux-specificites-des-hopitaux)

### Inferences
- Objets Odin : SI « à enjeux », décision d'homologation (autorité, date, durée, risques résiduels acceptés, conditions), échéances de la feuille de route (31/12/2026), dérogations à la PSSI, maturité par domaine (CaRE/ReCyF/hygiène ANSSI).
- Les décisions : arbitrer budgets entre homologations prioritaires, MFA, EDR, migration SecNumCloud.

### Gaps
- Non vérifiés ici (connaissances générales, à vérifier) : ISO 27001:2022 (transition certifs achevée oct. 2025) / 27002:2022, NIST CSF 2.0 (fév. 2024), CIS v8.x, Guide d'hygiène ANSSI (42 mesures), RGS v2 (durée d'homologation usuelle liée à l'IGI/RGS), dispositif OSIIC (non trouvé), détail de l'arrêté PSSIE, nouvelle version SecNumCloud annoncée (v3.2 vs EUCS).

## 3. Analyse de risques (EBIOS RM, ISO 27005, ISO 31000, FAIR)

### Takeaway
Non recherché en profondeur (aucune source consultée). Le guide d'homologation ANSSI (04/2025) sert de base à la décision d'homologation.

### Cited Findings
- Le guide d'homologation de sécurité ANSSI (04/2025) existe et est lié à MonServiceSécurisé — [ANSSI](https://messervices.cyber.gouv.fr/documents-guides/guide-homologation-securite-web-04-2025.pdf)

### Inferences
- Modèle d'objets à confirmer (connaissances générales, à vérifier) : EBIOS RM = 5 ateliers (cadrage/socle de sécurité, sources de risque, scénarios stratégiques, scénarios opérationnels, traitement) ; objets : valeurs métier, biens supports, événements redoutés (gravité), sources de risque/objectifs visés, parties prenantes, scénarios, vraisemblance, risque résiduel, plan de traitement, acceptation par l'autorité d'homologation. Odin doit relier risque ↔ bien support (CMDB) ↔ application ↔ projet de roadmap, et offrir une quantification optionnelle (FAIR) et une cartographie vs appétence.

### Gaps
- Version courante d'EBIOS RM (v1.5 2018 ?), ISO 27005:2022, usage FAIR dans le public : non vérifiés.

## 4. Autres obligations : AI Act, CRA, Data Act, CSRD, RGPD, DORA, HDS, RGAA, REEN

### Takeaway
AI Act : l'omnibus IA (Règlement UE 2026/1744) est en vigueur depuis le 27 juillet 2026 ; haut risque Annexe III reporté au 2 déc. 2027, Annexe I au 2 août 2028. CRA : obligations de signalement actives depuis le 11 sept. 2026 (le reste au 11 déc. 2027). CSRD : omnibus 2026/470 réduit fortement le champ aux grandes entreprises.

### Cited Findings
- Omnibus IA = Règlement (UE) 2026/1744, publié au JOUE le 24 juillet 2026, en vigueur le 27 juillet 2026 — [White & Case](https://www.whitecase.com/insight-alert/eu-ai-omnibus-enters-force-amending-ai-act) ; [Lewis Silkin](https://www.lewissilkin.com/insights/2026/07/27/the-digital-omnibus-on-ai-enters-into-force-today)
- Annexe III : 2 déc. 2027 (au lieu du 2 août 2026) ; Annexe I : 2 août 2028 ; transparence Art. 50 reste au 2 août 2026, avec délai au 2 déc. 2026 pour le marquage 50(2) des systèmes déjà sur le marché ; littératie IA (Art. 4) applicable depuis le 2 févr. 2025 mais assouplie ; nouvelles interdictions à partir du 2 déc. 2026 — [Gibson Dunn](https://www.gibsondunn.com/eu-ai-act-omnibus-agreement-postponed-high-risk-deadlines-and-other-key-changes/) (accord provisoire) ; [Lewis Silkin](https://www.lewissilkin.com/insights/2026/07/27/the-digital-omnibus-on-ai-enters-into-force-today). Dates finales à confirmer sur EUR-Lex.
- CRA : signalement (Art. 14) des vulnérabilités exploitées/incidents graves en 24 h à ENISA/CSIRT depuis le 11 sept. 2026, y compris produits déjà sur le marché ; plateforme unique ENISA ; orientations Commission du 27 juil. 2026 ; autres obligations au 11 déc. 2027 — [McCann FitzGerald](https://www.mccannfitzgerald.com/knowledge/data-privacy-and-cyber-risk/cyber-resilience-act-reporting-obligations-apply-from-11-september-2026) ; [Travers Smith](https://www.traverssmith.com/knowledge/knowledge-container/the-eu-cyber-resilience-acts-vulnerability-and-incident-reporting-requirements-are-now-live/)
- CSRD : directive Omnibus I (UE) 2026/470 (adoptée 24/02/2026, JOUE 26/02, en vigueur 18/03/2026) ; seuils cumulatifs 1 000 salariés et 450 M€ de CA ; transposition avant le 19/03/2027 ; premiers rapports des nouvelles entités en 2028 sur l'exercice 2027 ; aucune source sur collectivités — [Deloitte Avocats](https://blog.avocats.deloitte.fr/la-directive-omnibus-csrd-cs3d-est-publiee/) ; [Lefebvre Dalloz](https://formation.lefebvre-dalloz.fr/actualite/directive-csrd-nouveaux-seuils-obligations-et-calendrier-actualise)
- REEN (loi du 15 nov. 2021) : une source commerciale affirme une obligation légale pour les collectivités concernées depuis 2025 (à vérifier au texte) — [Leto](https://www.leto.legal/news/numerique-responsable-loi-reen-csrd-conformite-si-2026)

### Inferences
- CSRD ne s'applique en principe pas directement aux entités publiques non commerciales ; reste pertinente pour opérateurs/EPIC (à vérifier). Odin : suivre le bilan carbone du SI plutôt que le reporting CSRD pour les administrations.
- Pour l'IA : registre des systèmes d'IA avec classification Annexe III (usage public : éducation, emploi, services essentiels, forces de l'ordre, migration) ; échéance 2027 laisse du temps mais prohibitions et transparence/littératie sont déjà d'actualité.
- Responsabilité dirigeants : NIS2 (suspension), RGPD (responsabilité du responsable de traitement), AI Act (déployeur) : champ « responsable désigné » par obligation.

### Gaps
- Non recherchés : RGPD (registre, AIPD, notifications 72 h), Data Act (applicable depuis 12 sept. 2025, switching cloud 2027), DORA (volet français du projet de loi), HDS (nouveau référentiel v2), RGAA (v4.1, obligation publique, déclaration d'accessibilité), LPM/OIV/OSE, clauses marchés publics. À compléter par connaissances ou nouvelle recherche.

## 5. Indicateurs de posture, baromètres, reporting aux dirigeants

### Takeaway
Les sources trouvées confirment des échéances mesurables de la feuille de route (MFA, homologation, postes d'admin dédiés, DNS) utilisables comme KPI de pilotage ; pas de baromètre public documenté dans cette session.

### Cited Findings
- Échéances mesurables État : homologation SI à enjeux (fin 2026), MFA comptes admin (31/12/2026), postes d'admin dédiés (31/12/2026), DNS sécurisés (30/09/2026) — [ANSSI](https://cyber.gouv.fr/actualites/feuille-de-route-des-efforts-prioritaires-en-matiere-de-securite-numerique-de-letat-2026-2027) (via recherche)
- Observatoire des signalements d'incidents de sécurité des SI de santé (CERT Santé) 2025 publié — [ANS](https://esante.gouv.fr/sites/default/files/media/document/ANS_CERTSante_Rapport_Public_Observatoire_Signalements_ISSIS_2025_VF_1.pdf)
- CaRE mesure la perception du risque par 719 directeurs (enquête) — [ANS](https://esante.gouv.fr/espace-presse/plus-de-700-directeurs-hospitaliers-mobilises-pour-mesurer-la-perception-du-risque-cyber)

### Inferences
- KPI/KRI proposés (à valider) : % SI critiques homologués (et homologation en cours de validité), % comptes admin sous MFA, couverture EDR, délai moyen de correction des vulnérabilités critiques, % actifs hors support, incidents notifiés et délais, couverture PCA/PRA testée, % tiers critiques évalués, maturité ReCyF/hygiène, risque résiduel accepté vs appétence, dérogations ouvertes.
- Format élus/dirigeants : vue unique, tendance, risques acceptés à signer, arbitrages budgétaires.

### Gaps
- Baromètres CESIN, ANSSI (panorama menace), Cigref, indicateurs DINUM (baromètre résultats numériques), recommandations de reporting aux élus : non recherchés.

## 6. Dette technique / obsolescence ↔ risque ; continuité ; tiers et cloud ; données et IA ; numérique responsable ; outils GRC

### Takeaway
Peu de sources spécifiques trouvées ; éléments utiles : doctrine cloud/SecNumCloud (tiers), RGESN (écoconception), CaRE (exercices de crise). Le reste relève de connaissances générales à valider.

### Cited Findings
- RGESN : version finale mai 2024, 78 critères en 8 familles ; Arcep/Arcom avec ADEME, DINUM, CNIL, Inria (attribution DINUM vs Arcep variable selon sources) ; outil d'auto-évaluation NumEcoDiag ; instance de dialogue pour évaluer l'adoption — [Arcep](https://www.arcep.fr/actualites/actualites-et-communiques/detail/n/environnement-rgesn-170524.html) ; [Leto](https://www.leto.legal/news/outils-referentiels-numerique-responsable-2026) ; [Acteurs Publics](https://acteurspublics.fr/articles/une-nouvelle-instance-de-dialogue-pour-evaluer-ladoption-du-referentiel-decoconception-des-services-numerique/)
- CaRE : kit d'exercice de crise cyber pour établissements sanitaires/médico-sociaux — [Seban](https://www.seban-associes.avocat.fr/e-sante-publication-dun-kit-dexercice-de-crise-cyber-en-etablissement-sanitaire-et-medico-social-programme-care/?idLAJ=125136)
- Commande publique : 55 M€ passés à des entreprises SecNumCloud (Acteurs Publics, titre seul) — [Acteurs Publics](https://acteurspublics.fr/articles/55-millions-deuros-de-commande-publique-passes-aux-entreprises-francaises-labellisees-secnumcloud/)

### Inferences
- Lien dette/risque : champs fin de support (date), SBOM, version, exposition, criticité métier ; priorisation du plan de remédiation par risque (valeur métier × obsolescence).
- Continuité : BIA par processus/service essentiel, RTO/RPO, lien application ↔ PCA/PRA, dates de derniers exercices (ISO 22301) ; indicateurs de couverture testée.
- Tiers : registre fournisseurs, criticité, localisation/extraterritorialité, qualification SecNumCloud, concentration, clauses cyber/RSE.
- Données/IA : registre RGPD, classification, registre IA (niveau AI Act, ISO 42001), liens vers actifs.
- GRC : périmètre type = registre de risques, référentiels/contrôles, preuves, audits/recommandations (Cour des comptes, inspections), dérogations, tiers, plans d'action ; Odin s'interface avec GRC plutôt que le remplacer.

### Gaps
- Non recherchés : doctrine IA de l'État, ISO 22301/42001, TPRM public, éditeurs GRC (EGERIE, Tenacy, ServiceNow IRM, Archer, OneTrust), contrôle interne IT, audit Cour des comptes, SBOM/CRA côté acheteur public. Tout ce qui précède dans cette section en « Inférences » est issu de connaissances générales et doit être vérifié.
