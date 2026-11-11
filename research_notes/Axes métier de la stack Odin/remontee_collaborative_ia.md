# Remontée collaborative de rapports par tous les agents + compréhension et production par IA (Odin, organismes publics français)

Date de rédaction : 2026-11-11. Méthode : 9 recherches web (cadre réglementaire, doctrine IA de l'État, éditeurs EA). Limite assumée : ma couverture est inégale ; les sections « typologie des rapports », « modèles de contribution » et « état de l'art IA documentaire » reposent surtout sur des inférences issues de pratiques connues, non sur des sources fraîches. Elles sont marquées comme telles. Les statuts d'adoption de textes récents doivent être revérifiés.

## 1. Typologie des rapports/contributions par rôle et gabarits

### Takeaway
Le périmètre « tous profils » mêle des documents libres (Word/PDF/mail/slides) et des signaux semi-structurés (tickets, CI). Je n'ai pas trouvé de source publique unique décrivant cette typologie ; la grille ci-dessous est une proposition de conception (inférence), à valider avec l'utilisateur.

### Cited Findings
- Le guide ANSSI sur l'IA générative s'adresse explicitement à des publics variés (développeurs, administrateurs, RSSI, DSI, utilisateurs), ce qui confirme que les contributeurs/utilisateurs d'un tel système sont de profils hétérogènes — [ANSSI, Recommandations de sécurité pour un système d'IA générative (29/04/2024)](https://cyber.gouv.fr/sites/default/files/document/Recommandations_de_s%C3%A9curit%C3%A9_pour_un_syst%C3%A8me_d_IA_g%C3%A9n%C3%A9rative.pdf)
- Le ServiceNow Now Assist for EA cible d'abord la synthèse des ADR (Architecture Decision Records), ce qui montre que l'ADR est un gabarit déjà exploité par IA dans l'offre du marché — [ServiceNow docs](https://www.servicenow.com/docs/r/application-portfolio-management/enterprise-architecture/now-assist-ea.html)

### Inferences
- Grille proposée par rôle (non sourcée, à valider) :
  - Agent métier : demande/besoin métier, signalement d'anomalie, rapport d'activité ; fréquence ad hoc/mensuelle ; formats mail, tableur, Word ; faible structuration.
  - Développeur : revue de code/dette (fiche de dette technique), ADR, post-mortem/RETEX blameless, tickets Jira/GitLab, rapports CI ; Markdown et tickets ; forte structuration native.
  - Chef de projet : flash report/rapport d'avancement (hebdo/mensuel), RAF, compte rendu de comité, bilan de projet, fiche risque ; Word/PPT/tableur ; structuration moyenne.
  - RSSI : rapports d'audit/pentest, fiches incident, tableaux de risques ; PDF ; diffusion restreinte.
  - DPO : analyses d'impact (AIPD), registre, avis ; Word/PDF ; contient des données personnelles.
  - Architecte : ADR, cartographies, notes de cadrage, revues d'architecture.
  - DSI : synthèses de pilotage, arbitrages, notes de décision, présentations aux instances.
  - Élu : lecture seule de synthèses, demandes de clarification ; consommateur plutôt que producteur.
- Un gabarit minimal commun (métadonnées : type, auteur, périmètre, objets SI rattachés, classification, date, statut) serait le point d'ancrage de tous les types, avec des sections spécifiques par gabarit.

### Gaps
- Aucune source trouvée sur les fréquences et formats réels en administration française ; à documenter par entretiens utilisateurs.
- Pas de source sur des gabarits de référence publics (ex. conventions DINUM de rapport de projet numérique) ; non recherché en profondeur.

## 2. Modèles de contribution, gouvernance, alerte et cycle de vie

### Takeaway
Le cadre légal de l'alerte impose de séparer nettement un canal de signalement protégé d'un simple « rapport de risque » dans Odin. Pour le reste (équilibre saisie/qualité, gamification, cycle de vie), je n'ai pas de sources et je livre des inférences.

### Cited Findings
- La loi du 21 mars 2022 (dite Waserman) transpose la directive européenne en conservant les garanties Sapin II et supprime la hiérarchie des canaux : le lanceur d'alerte choisit librement entre canal interne et externe ; la divulgation publique reste limitée à certains cas — [Vie-publique, loi du 21 mars 2022](https://www.vie-publique.fr/loi/282472-loi-21-mars-2022-waserman-protection-des-lanceurs-dalerte)
- Dans la fonction publique, la procédure interne relève de chaque employeur public (mutualisation possible, notamment via les centres de gestion) ; articles L.135-1 à L.135-4 du CGFP ; décret du 3 octobre 2022 pour les autorités externes — [Landot avocats](https://blog.landot-avocats.net/2022/10/04/lanceurs-dalerte-le-decret-est-publie-aux-employeurs-y-compris-publics-et-ou-aux-centres-de-gestion-de-le-mettre-en-oeuvre/) ; [Anticor](https://anticor.org/wp-content/uploads/2022/12/Anticor-lancer-lalerte-dans-la-fonction-publique-V3.pdf)

### Inferences
- Odin ne doit pas devenir le canal d'alerte officiel : un dépôt de « rapport » ne garantit ni confidentialité de l'identité ni les délais légaux. Prévoir un renvoi vers le dispositif d'alerte de l'organisme, et un avertissement si le contenu déposé ressemble à une alerte (détection IA possible, avec routage vers le référent).
- Modèle hybride recommandé (inférence de conception) : signaux automatiques (tickets, CI, ITSM) comme base, formulaires courts pour les faits structurés (statut, risque, jalon), documents libres pour le narratif, l'IA faisant le pont (pré-remplissage du formulaire à partir du document, validé par l'auteur). Réduit la charge de saisie, principal facteur d'abandon des outils EA (affirmation courante de la profession, non sourcée ici).
- Cycle de vie : brouillon, partagé, validé, publié, archivé, périmé, avec date de péremption par type (une fiche risque périme plus vite qu'un bilan de projet) et relance automatique à l'auteur.
- Boucle de rétroaction : montrer au contributeur ce que son rapport a produit (objets rattachés, indicateurs mis à jour) pour justifier l'effort ; éviter les classements individuels (voir section 5).

### Gaps
- Pas de retours d'expérience chiffrés sur l'adoption ni sur la gamification trouvés ; non étayé.
- Obligations précises de l'employeur public (seuils, délais d'accusé de réception) non confirmées : à lire dans le décret du 3 octobre 2022.

## 3. Compréhension IA des documents

### Takeaway
Les menaces et mesures de sécurité sont bien documentées (ANSSI, OWASP) ; l'état de l'art fin 2026 sur l'extraction/entity linking n'a pas été recherché avec des sources, je ne l'affirme donc pas. Principe structurant : tout fait extrait reste une proposition validée par un humain avant d'alimenter un indicateur.

### Cited Findings
- L'ANSSI classe les attaques en trois catégories : manipulation de l'IA, infection du jeu de données, exfiltration d'informations ; le guide compte 35 recommandations couvrant le cycle de vie, dont audit avant mise en production, journalisation des traitements, contrôle du code généré, et interdiction des outils d'IA générative publics pour les données sensibles — [ANSSI](https://cyber.gouv.fr/sites/default/files/document/Recommandations_de_s%C3%A9curit%C3%A9_pour_un_syst%C3%A8me_d_IA_g%C3%A9n%C3%A9rative.pdf) ; résumé secondaire : [Journal du Net](https://www.journaldunet.com/intelligence-artificielle/1530211-comment-securiser-son-ia-generative-les-conseils-de-l-anssi/)
- Le guide ANSSI exclut la protection des données personnelles, renvoyée à la CNIL — idem source ANSSI ci-dessus (selon résumé de recherche)
- OWASP Top 10 LLM 2025 : l'injection de prompt est LLM01 ; l'injection indirecte passe par des documents/pages lus par le modèle ; aucune prévention infaillible ; mesures : contrôle des privilèges, séparation du contenu externe et des instructions ; nouveautés 2025 : System Prompt Leakage et Vector and Embedding Weaknesses ; une édition 2026 existerait, à vérifier — [Deep dive OWASP LLM 2025](https://opensourcesecurity.substack.com/p/a-deep-dive-into-the-owasp-top-10) ; [HackerOne](https://www.hackerone.com/ai/owasp-top-10-llms-2025)
- Lucid a annoncé en juin 2026 des intégrations avec LeanIX et Ardoq pour préparer documentation et systèmes à l'usage de l'IA, signe que la qualité des données source est un frein reconnu — [IT Brief UK](https://itbrief.co.uk/story/lucid-adds-leanix-ardoq-links-for-enterprise-ai-rollouts)

### Inferences
- Tout document déposé est un vecteur d'injection indirecte : un rapport Word piégé pourrait pousser l'IA à fausser des extractions ou à exfiltrer des contenus d'autres périmètres. Exigences : traiter le contenu comme donnée, jamais comme instruction ; l'IA d'extraction n'a aucun outil d'écriture ni accès inter-périmètres ; filtrage des droits avant la recherche (pas après).
- Pipeline conseillé : dépôt, analyse antivirus et hygiène, extraction de texte/OCR, classification, extraction d'entités (projet, application, risque, budget, jalon, ETP, dépendance) avec score de confiance, rattachement au référentiel (entity linking avec candidats proposés), file de validation humaine, publication des faits validés.
- Détection d'écarts (statut « vert » déclaré vs signaux techniques : tickets bloquants, échecs CI, retards) : forte valeur, mais à présenter comme « signal à examiner », jamais comme verdict sur la personne ou l'équipe.
- RAG : citations obligatoires vers passage source, refus de répondre sans source, évaluation continue sur jeu de questions de référence (golden set).

### Gaps
- Aucune source datée fin 2026 sur la précision d'extraction, l'évaluation du RAG ou les graphes de connaissances : non recherché ; ne pas citer de chiffres.

## 4. Production par IA (synthèses, rapports de direction, présentations)

### Takeaway
Les éditeurs EA commencent par la synthèse de contenus existants ; la production traçable (chaque affirmation liée à sa source, chiffres verrouillés) est une exigence de conception d'Odin, justifiée par les obligations de transparence.

### Cited Findings
- Now Assist for EA : compétences IA générative dont synthèse d'ADR et agents IA pour tâches d'EA ; la v7.4.0 (juillet 2026) change le fournisseur de modèle par défaut de Now LLM à Azure OpenAI ; licence EA Pro plus requise — [ServiceNow docs](https://www.servicenow.com/docs/r/application-portfolio-management/enterprise-architecture/now-assist-ea.html) ; [agents](https://www.servicenow.com/docs/r/xanadu/application-portfolio-management/enterprise-architecture/using-na-ea-ai-agents.html)
- Le LeanIX AI Assistant a été annoncé en 2023, hébergé en privé sur Azure ; capacités en bêta (suggestion de successeurs d'applications) à l'époque — [LeanIX blog](https://www.leanix.net/en/blog/ai-future-enterprise) ; capacités actuelles non vérifiées
- Le Conseil d'État a publié en décembre 2025 une charte d'usage de l'IA dans la juridiction administrative, exemple de cadre interne public — [Conseil d'État](https://www.conseil-etat.fr/Media/actualites/documents/2025/decembre-2025/charte-d-utilisation-de-l-intelligence-artificielle-au-sein-de-la-juridiction-administrative)
- Article 50 de l'AI Act (transparence) s'appliquerait à partir d'août 2026 indépendamment du calendrier haut risque, selon une source secondaire — [Viso.ai](https://viso.ai/deep-learning/digital-omnibus-ai/) ; à confirmer sur le texte officiel

### Inferences
- Garde-fous de conception : mention « généré par IA » systématique ; chiffres injectés depuis les données (jamais écrits librement par le modèle) ; chaque phrase factuelle liée à une source cliquable ; relecture et validation humaine avant diffusion à la direction/aux élus ; versionnage et journal de génération (modèle, prompt, sources) ; génération PPTX par gabarit de l'organisme.
- Synthèses par audience (DSI, élus, comité) à partir des mêmes faits validés, pour éviter les versions contradictoires.

### Gaps
- Pas de retour d'expérience sourcé sur la qualité des rapports générés ni sur l'acceptation par les élus/directions.
- Capacités actuelles d'Ardoq (IA) : aucune information trouvée.

## 5. Confidentialité, contrôle d'accès, droits des agents, dialogue social, AI Act

### Takeaway
Risque principal : dérive vers la surveillance des agents. L'AI Act classe en haut risque l'IA appliquée à l'emploi et à la gestion des travailleurs (échéance reportée à fin 2027 par l'omnibus, sous réserve d'adoption), et le dialogue social (CSA/CST) est à anticiper.

### Cited Findings
- Omnibus numérique IA : accord provisoire du 7 mai 2026 reportant au 2 décembre 2027 les obligations des systèmes haut risque autonomes (annexe III, dont emploi/RH) et au 2 août 2028 celles de l'annexe I ; classification inchangée ; interdictions de l'art. 5 et règles GPAI maintenues ; enregistrement dans la base UE même pour systèmes estimés exemptés. Sources divergentes sur l'adoption formelle — [DLA Piper](https://knowledge.dlapiper.com/dlapiperknowledge/globalemploymentlatestdevelopments/2026/The-Digital-AI-Omnibus-Proposed-deferral-of-high-risk-AI-obligations-under-the-AI-Act) ; [IDTechWire](https://idtechwire.com/eu-moves-to-delay-high-risk-ai-act-compliance-to-december-2027/) ; [Viso.ai](https://viso.ai/deep-learning/digital-omnibus-ai/)
- CNIL : quand des données personnelles servent au développement d'un système d'IA, RGPD et AI Act s'appliquent ensemble ; fiches d'avril 2024, intérêt légitime (juin 2025), fiches du 22 juillet 2025 (applicabilité du RGPD aux modèles, sécurité, annotation) ; les recommandations couvrent le développement, pas le déploiement — [CNIL](https://cnil.fr/fr/developpement-des-systemes-dia-les-recommandations-de-la-cnil-pour-respecter-le-rgpd) ; [CNIL intérêt légitime](https://cnil.fr/fr/recommandations-developpement-ia-interet-legitime)
- Dialogue social public : les CSA connaissent des questions relatives au fonctionnement et à l'organisation des services (art. L.253-1 CGFP) ; l'autorité n'est pas tenue de suivre l'avis (source CST/F3SCT) ; je n'ai pas pu confirmer le texte précis imposant la consultation pour un outil d'IA — [Doctrine, CGFP](https://www.doctrine.fr/l/texts/codes/LEGITEXT000044416551/articles/LEGIARTI000052023412) ; [CDG33](https://www.cdg33.fr/wp-content/uploads/ressources/20230201_NIF_attributioncst.pdf)
- La DGAFP a publié un guide de stratégie d'usage de l'IA et une boîte à outils pour la GRH publique — [DGAFP guide](https://www.fonction-publique.gouv.fr/files/files/publications/publications-dgafp/guide-strategie-usage-intelligence-artificielle.pdf) ; [boîte à outils](https://www.fonction-publique.gouv.fr/files/files/publications/publications-dgafp/IA/Presentation-boite-a-outils-cadre-usage-IA-en-GRH_A.pdf)
- Un guide d'usage de l'IA pour agents publics de l'État (DINUM, juin 2026) est en circulation ; non lu en détail — [CFDT UFETAM (copie)](https://www.cfdt-ufetam.org/wp-content/uploads/2026/08/guide_usage_ia_pour_agents_publics_etat_dinum_juin_2026.pdf)
- Des négociations d'accord-cadre avec les syndicats de la fonction publique sur l'IA ont débuté le 16 avril 2026, signature visée à l'automne 2026 — [Banque des Territoires / presse](https://www.banquedesterritoires.fr/avec-le-plan-notre-ia-letat-accelere-sur-le-deploiement-des-outils-et-la-gouvernance) (chiffres variables selon sources)

### Inferences
- Si Odin sert, même indirectement, à évaluer des personnes (performance, répartition de tâches, surveillance d'activité), il entre dans le champ haut risque « emploi » ; le plus sûr est un choix de conception explicite : unité d'analyse = projet/application/équipe, jamais l'individu ; pas de métriques par agent ; masquer ou pseudonymiser les noms dans les extractions par défaut ; interdire les usages de classement de personnes.
- Classification par document (public, interne, diffusion restreinte, sensible/RH/sécurité) avec droits par rôle, périmètre et ligne hiérarchique, appliqués avant la recherche vectorielle (filtrage au niveau de l'index) ; cloisonnement fort des rapports sécurité/RH/disciplinaire (index séparés, IA dédiée ou exclusion par défaut) ; journalisation de toutes les consultations et requêtes IA.
- Pseudonymisation avant passage dans l'IA si le modèle n'est pas hébergé en environnement maîtrisé ; AIPD probable ; consultation du CSA/CST (et F3SCT) à prévoir avant déploiement, à confirmer avec le juriste de l'organisme ; droit d'accès des agents aux données les concernant dans les rapports (procédure à prévoir).

### Gaps
- Texte précis de la consultation obligatoire CSA/CST pour un outil d'IA : non confirmé.
- Position CNIL spécifique sur le RAG interne et la surveillance des agents : non trouvée ici.
- Adoption formelle finale de l'omnibus IA : à vérifier sur EUR-Lex/Journal officiel de l'UE.

## 6. IA dans le secteur public : doctrine, souveraineté, hébergement

### Takeaway
L'État a généralisé « L'Assistant » (DINUM + Mistral, hébergement qualifié SecNumCloud chez Outscale) via le plan « Notre IA » (16 juin 2026) ; une option crédible pour Odin est de s'appuyer sur ce socle ou sur des LLM open-weight on-premise, avec les chiffres de périmètre à vérifier.

### Cited Findings
- Le plan « Notre IA » a été présenté le 16 juin 2026 (David Amiel) ; il généralise « L'Assistant » développé par la DINUM avec Mistral AI, sur infrastructure qualifiée SecNumCloud chez Outscale ; ActuIA indique que l'hébergement peut varier selon les projets (Mistral, Outscale, centres propres) — [economie.gouv.fr](https://www.economie.gouv.fr/actualites/direct-video-lia-dans-letat-keynote-finale-et-annonces-de-david-amiel-mardi-16-juin) ; [ActuIA](https://www.actuia.com/en/news/mistral-ai-in-ministries-what-the-state-buys-for-eur6m/) ; [Banque des Territoires](https://www.banquedesterritoires.fr/avec-le-plan-notre-ia-letat-accelere-sur-le-deploiement-des-outils-et-la-gouvernance)
- Périmètre et montants divergent selon les sources (environ 1 million d'agents sur 2,6 millions, extension aux enseignants, 6 M€ de contrat Mistral 2026-2027 pour ingénieurs détachés, autres montants cités) : ne pas retenir de chiffre ferme — [ActuIA](https://www.actuia.com/en/news/mistral-ai-in-ministries-what-the-state-buys-for-eur6m/) ; [Economie Matin](https://www.economiematin.fr/?p=224810)
- Albert/Assistant IA : outil à destination des agents (pas des citoyens), usages visés rédaction, synthèse, OCR, traitement documentaire ; première version France Services non généralisée — [Weka](https://www.weka.fr/actualite/administration/article/albert-l-outil-d-ia-generative-experimente-a-france-services-ne-sera-pas-generalise-209194/) ; [Le Monde Informatique](https://www.lemondeinformatique.fr/actualites/lire-l-etat-accelere-la-diffusion-de-la-genai-aupres-des-agents-100462.html)
- La DSI de l'État met à disposition des ministères un socle commun d'IA clé en main — [Acteurs Publics](https://acteurspublics.fr/articles/la-dsi-de-letat-met-a-disposition-des-ministeres-un-socle-commun-dia-cle-en-main/)
- ANSSI : recommandations conjointes avec le BSI sur les assistants de programmation IA (octobre 2024) — [ANSSI](https://cyber.gouv.fr/actualites/lanssi-et-le-bsi-publient-leurs-recommandations-de-s%C3%A9curit%C3%A9-concernant-les-assistants-de-programmation-bas%C3%A9s-sur-lia/)

### Inferences
- Pour Odin : architecture « modèle interchangeable » (API compatible) permettant Assistant/Mistral hébergé SecNumCloud, ou LLM open-weight on-premise pour les périmètres sensibles ; aucun envoi vers des services IA publics hors UE (alignement ANSSI).
- Registre interne des usages IA de l'organisme et documentation de transparence à prévoir (exigences AI Act selon classification, calendrier ci-dessus).
- Offre souveraine applicable aux collectivités/opérateurs hors État : non établie (l'article Acteurs Publics sur la collaboration État-Banque des Territoires pour outiller les collectivités suggère un chantier, non détaillé ici).

### Gaps
- Statut exact (novembre 2026) du déploiement de l'Assistant et conditions d'accès pour des organismes hors administration d'État : à vérifier auprès de la DINUM.
- Guides ANSSI plus récents (2025-2026) sur les agents IA/RAG : non consultés.
- NIST AI RMF, ISO/IEC 42001, Gartner/Forrester : non recherchés.

## 7. Outils comparables et ce qui manque

### Takeaway
Les éditeurs EA (LeanIX, ServiceNow, Ardoq) ajoutent des assistants IA centrés sur leur propre référentiel ; je n'ai pas trouvé d'offre qui combine dépôt de rapports par tous les agents, extraction validée, rattachement au SI et production traçable pour le secteur public. Ce constat est une inférence limitée par ma recherche.

### Cited Findings
- ServiceNow, LeanIX : voir sections 3-4 (synthèse d'ADR, agents, assistant bêta hébergé Azure) — [ServiceNow](https://www.servicenow.com/docs/r/application-portfolio-management/enterprise-architecture/now-assist-ea.html) ; [LeanIX](https://www.leanix.net/en/blog/ai-future-enterprise)
- Les modèles par défaut de Now Assist EA dépendent de fournisseurs cloud (Azure OpenAI, Gemini, Claude sur AWS), ce qui pose la question SecNumCloud pour un organisme public — [ServiceNow release notes](https://www.servicenow.com/docs/r/application-portfolio-management/enterprise-architecture/now-assist-ea.html)

### Inferences
- Manques probables du marché : (1) ingestion de documents non structurés de tous profils vers le référentiel avec validation humaine ; (2) hébergement souverain sans dépendance à un fournisseur extra-européen ; (3) garde-fous contre la surveillance des agents ; (4) détection d'écarts entre déclaratif et signaux techniques. À vérifier par veille concurrentielle (Copilot, Glean, Atlassian Rovo, Planview non étudiés ici).

### Gaps
- Aucun retour d'expérience d'adoption/qualité de RAG d'entreprise sourcé ; Copilot/Glean/Rovo non couverts.

## 8. Liste consolidée de capacités, risques et questions ouvertes

### Capacités proposées pour Odin (inférence de conception, sauf mention)
1. Dépôt de rapports multi-format (Word, PDF, Markdown, tableur, mail, slides) pour tout profil, avec gabarits (flash report, RAF, RETEX blameless, ADR, fiche risque, fiche incident, compte rendu, bilan, fiche de dette).
2. Signaux automatiques (tickets Jira/GitLab, CI, ITSM) comme source complémentaire.
3. Extraction d'entités structurées avec scores de confiance et file de validation humaine avant alimentation des indicateurs.
4. Rattachement (entity linking) aux objets du référentiel SI, avec correction manuelle.
5. Détection d'écarts déclaré/technique et de signaux faibles, présentés comme alertes à examiner.
6. RAG avec citations obligatoires, filtré par droits avant récupération.
7. Génération de synthèses par audience, notes de décision, présentations PPTX ; chaque affirmation sourcée ; chiffres verrouillés sur les données ; mention « généré par IA » ; validation humaine avant diffusion.
8. Cycle de vie du rapport (brouillon à archivé/périmé) avec péremption et relances.
9. Classification et contrôle d'accès par rôle/périmètre/hiérarchie ; cloisonnement des contenus sensibles (sécurité, RH, disciplinaire) ; journal d'audit complet.
10. Pseudonymisation avant IA ; hébergement SecNumCloud ou on-premise ; modèle interchangeable.
11. Renvoi vers le dispositif d'alerte officiel de l'organisme ; détection et routage de contenus ressemblant à une alerte (sans traiter l'identité dans Odin).
12. Boucle de retour au contributeur (impact visible de sa contribution) sans classement individuel.
13. Évaluation continue de la qualité IA (jeu de référence, suivi des erreurs d'extraction).

### Risques majeurs
- Dérive de surveillance/évaluation des agents (AI Act haut risque emploi, RGPD, dialogue social).
- Injection de prompt indirecte via documents déposés, fuite inter-périmètres, empoisonnement des données (OWASP LLM01, ANSSI).
- Hallucinations et extractions erronées contaminant les indicateurs de pilotage.
- Données obsolètes et faible adoption (risque classique des outils EA ; non sourcé ici).
- Dépendance à un fournisseur de modèle non souverain.
- Non-conformité de calendrier (omnibus non confirmé, art. 50 transparence).
- Confusion entre rapport et alerte protégée (loi Waserman).

### Questions ouvertes à trancher avec l'utilisateur
- Odin évalue-t-il des personnes, ou uniquement projets/applications/équipes ? (conditionne la classification AI Act)
- Quel hébergement/modèle : Assistant DINUM, Mistral SecNumCloud, open-weight on-premise ? Pour quels périmètres sensibles ?
- Qui valide les faits extraits (auteur, chef de projet, référent SI) ?
- Quel niveau de classification maximal accepté dans Odin (exclure ou non les rapports sécurité/RH) ?
- Calendrier de consultation CSA/CST/F3SCT et d'AIPD ; DPO impliqué dès la conception.
- Cible : organismes de l'État uniquement ou collectivités/opérateurs aussi ?
- Faut-il intégrer le canal d'alerte interne ou seulement y renvoyer ?
