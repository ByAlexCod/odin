# 05. Exigences fonctionnelles par module

Chaque exigence est numérotée `EX-<module>-nn`, formulée du point de vue de l'utilisateur ou de l'organisme, sans solution technique.
**Priorité** : M indispensable · S important · C souhaitable · W reporté. **Lot** : voir fichier 10 (L1 à L6).
Les règles de gestion `RG-nn` sont au fichier 08 ; les règles IA `IA-nn` au fichier 06.

Modules : ACC accès · RAP rapports · IAF faits et compréhension · REF référentiel du SI · OBJ objectifs · POR demandes et portefeuille · ROA roadmaps et scénarios · DET dette et obsolescence · RSR ressources · FIN finances · FOU fournisseurs et contrats · SEC sécurité et risques · REG contraintes et échéances · ALI alimentations · DEC décisions et comités · TDB tableaux de bord et alertes · RST restitutions · ASS assistant · QUA qualité des données · NOT notifications et collaboration · ADM administration · AUD audit.

---

## ACC. Accès, comptes, rôles

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-ACC-01 | Tout agent de l'organisme peut se connecter avec son identité professionnelle et obtient le rôle Contributeur par défaut. | M | L1 |
| EX-ACC-02 | Des prestataires peuvent être autorisés avec le rôle Contributeur externe, limité à des périmètres et à une durée. | M | L1 |
| EX-ACC-03 | Un utilisateur peut cumuler plusieurs rôles ; ses vues s'adaptent à ses rôles (navigation simplifiée pour le contributeur). | M | L1 |
| EX-ACC-04 | Les droits sont attribués à un rôle sur un périmètre (équipe, direction, application, projet, domaine). | M | L1 |
| EX-ACC-05 | Les délégations temporaires de validation sont possibles, tracées et expirent automatiquement. | S | L1 |
| EX-ACC-06 | À l'arrivée d'un agent, Odin propose son équipe et ses objets de référence ; à son départ, Odin impose la réattribution de ses objets (P-27). | M | L1 |
| EX-ACC-07 | L'utilisateur peut consulter la liste des droits dont il dispose et leur origine. | S | L1 |
| EX-ACC-08 | Les accès aux contenus N4 sont soumis à une habilitation explicite par le rôle responsable du domaine. | M | L1 |
| EX-ACC-09 | Un message d'information expliquant ce qu'Odin fait et ne fait pas (dont « n'évalue pas les personnes ») est présenté à la première connexion et reste accessible. | M | L1 |
| EX-ACC-10 | Les contributeurs externes ne voient aucun contenu N1 à N4 hors de leur périmètre explicitement ouvert. | M | L1 |

## RAP. Rapports

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-RAP-01 | Depuis n'importe quel écran, un utilisateur peut **partager un rapport** en glissant un document, en collant un texte ou en transférant un message. | M | L1 |
| EX-RAP-02 | Le dépôt nécessite au plus un clic de validation ; type, rattachements, période et niveau sont proposés et modifiables. | M | L1 |
| EX-RAP-03 | Les types de documents bureautiques courants (texte, tableur, présentation, document portable, texte brut, courriel) sont acceptés ; une indication claire est donnée en cas de format illisible. | M | L1 |
| EX-RAP-04 | L'utilisateur peut rédiger un rapport dans Odin avec un **gabarit guidé** (bibliothèque de gabarits, fichier 09), préremplie depuis les faits validés. | M | L1 |
| EX-RAP-05 | Les brouillons sont enregistrés automatiquement et repris ultérieurement. | M | L1 |
| EX-RAP-06 | Chaque rapport a une version ; un nouveau dépôt peut **remplacer** une version, l'historique des versions reste consultable. | M | L1 |
| EX-RAP-07 | Un rapport a un type, une période couverte, un auteur, des rattachements (applications, projets, équipes, services rendus), un niveau de classification et un statut de cycle de vie (fichier 03 §5.1). | M | L1 |
| EX-RAP-08 | Un rapport « officiel » (par ex. rapport d'avancement) peut être soumis à **validation** d'un responsable avant d'être marqué officiel. | S | L1 |
| EX-RAP-09 | L'utilisateur dispose d'une **bibliothèque de rapports** filtrable (type, période, objet, auteur, statut, niveau) limitée à ses droits. | M | L1 |
| EX-RAP-10 | Le texte intégral des rapports accessibles est **recherchable**. | M | L1 |
| EX-RAP-11 | Les rapports ont une durée de validité par type ; à expiration ils passent à *périmé* ; ils peuvent être archivés. | M | L1 |
| EX-RAP-12 | L'auteur peut **retirer** un rapport, sous les règles de conservation et de traçabilité (RG-20, RG-21). | M | L1 |
| EX-RAP-13 | Une détection de **doublons** propose de remplacer ou de rattacher plutôt que de dupliquer. | S | L1 |
| EX-RAP-14 | L'auteur voit **ce que son rapport a changé** (faits utilisés, objets mis à jour, décisions citant) dans les limites de ses droits. | M | L1 |
| EX-RAP-15 | Des **demandes de rapport** peuvent être émises (par un PMO, un responsable) vers un auteur ou une équipe, avec échéance et gabarit. | S | L1 |
| EX-RAP-16 | Des **rappels de dépôt périodique** (rapport mensuel) sont envoyés avec le gabarit prérempli. | S | L1 |
| EX-RAP-17 | Les rapports peuvent être **commentés** (fil de discussion lié) par les personnes autorisées. | C | L2 |
| EX-RAP-18 | Le **signalement court** (risque, problème, dette, idée, besoin) est possible en moins de 30 secondes, avec option de visibilité restreinte (P-04). | M | L1 |
| EX-RAP-19 | Un message dirigeant vers la **procédure d'alerte protégée** de l'organisme est affiché lorsque le contenu relève de ce cadre (RG-24). | M | L1 |
| EX-RAP-20 | Le contributeur peut **exporter** ses propres rapports et leur historique. | S | L1 |

## IAF. Compréhension IA et faits

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-IAF-01 | À chaque dépôt, Odin analyse le rapport et propose : type, résumé court, rattachements, niveau de classification, faits extraits. | M | L1 |
| EX-IAF-02 | Les faits extraits suivent le catalogue des natures de faits (fichier 06 §3) : avancement, jalon, risque, incident, dépendance, besoin ou capacité en ressources, budget, dette, sécurité, contrainte externe, bénéfice, fournisseur, décision. | M | L1 |
| EX-IAF-03 | Chaque fait proposé indique son **extrait source**, sa **valeur**, son **objet rattaché**, sa **date de validité** et un niveau de **confiance**. | M | L1 |
| EX-IAF-04 | Un fait est d'abord **proposé (F0)** et ne peut alimenter un indicateur de direction qu'après confirmation et validation (RG-05). | M | L1 |
| EX-IAF-05 | L'auteur peut **confirmer, corriger, rejeter** chaque fait, individuellement ou en lot, depuis un écran à deux volets document/faits (E-06). | M | L1 |
| EX-IAF-06 | Le responsable de l'objet (application, projet…) et les curateurs peuvent **valider** (F2) les faits d'un objet ; les faits issus de plusieurs rapports sont présentés ensemble. | M | L1 |
| EX-IAF-07 | Les faits sont **historisés** : chaque valeur garde sa date, ses sources, ses validations et ses remplacements. | M | L1 |
| EX-IAF-08 | Odin détecte les **contradictions** entre faits (deux dates différentes, deux statuts, un statut déclaré incompatible avec des signaux) et génère un **signal** puis, si nécessaire, une **demande de précision**. | M | L1 |
| EX-IAF-09 | Odin détecte des **signaux faibles** (mêmes difficultés signalées dans plusieurs rapports, dérive progressive, dépendance répétée) et les propose au référent du domaine. | S | L2 |
| EX-IAF-10 | Odin signale les **données personnelles** et **contenus sensibles** détectés avant publication et propose masquage ou restriction (IA-07, IA-08). | M | L1 |
| EX-IAF-11 | L'IA ne crée aucun fait évaluatif portant sur une personne identifiable (RG-01, IA-08). | M | L1 |
| EX-IAF-12 | Les contenus déposés sont traités comme des données, jamais comme des instructions ; les tentatives sont consignées (IA-12). | M | L1 |
| EX-IAF-13 | Les utilisateurs peuvent donner un **retour qualité** sur chaque fait et chaque réponse (exact, inexact, incomplet). | M | L1 |
| EX-IAF-14 | Le rattachement d'un fait à plusieurs objets est possible ; un rattachement ambigu est proposé à un curateur. | S | L1 |
| EX-IAF-15 | Un fait peut aussi être **saisi directement** sans rapport (avec rattachement et justification) ; il est alors marqué « saisie manuelle ». | M | L1 |
| EX-IAF-16 | Les faits peuvent être **rapprochés de sources objectives** (alimentations automatiques, pièces) pour atteindre le niveau F3. | S | L3 |
| EX-IAF-17 | Une **synthèse multi-rapports** (par objet, par période, par thème) est disponible avec citations. | M | L1 |
| EX-IAF-18 | Les analyses sont **refaisables** (nouveau gabarit, évolution du catalogue de faits) sans perdre les validations existantes. | S | L2 |

## REF. Référentiel du SI

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-REF-01 | Gérer les **applications** avec leur fiche (OBJ-12), responsable, équipe, services rendus servis, criticité, cycle de vie. | M | L1 |
| EX-REF-02 | Gérer les **équipes** : rattachement, applications portées, **membres**, effectif par profil. | M | L1 |
| EX-REF-03 | Gérer les **services rendus** et leurs liens avec applications et processus ; calculer la criticité de continuité. | M | L1 |
| EX-REF-04 | Gérer les **technologies** avec dates de fin de support et lien vers les applications. | S | L2 |
| EX-REF-05 | Gérer **données** et **flux** à un niveau utile à la décision (nature, sensibilité, criticité). | C | L3 |
| EX-REF-06 | La **fiche application** présente une synthèse (santé calculée, fraîcheur, faits à valider) et des onglets (rapports, dette, risques, technologies, contrats, coûts, équipe, historique). | M | L1 |
| EX-REF-07 | Le référentiel se **met à jour par les faits validés** (pas de ressaisie par fiche). | M | L1 |
| EX-REF-08 | Une application sans responsable, sans équipe ou sans rapport récent est signalée « orpheline » ou « périmée ». | M | L1 |
| EX-REF-09 | Une **vue cartographique** (applications × services rendus × équipes) est disponible avec filtres. | S | L2 |
| EX-REF-10 | Analyse d'**impact** : pour un objet (application, technologie, contrat, contrainte externe), lister les objets dépendants. | S | L2 |
| EX-REF-11 | **Import initial** du patrimoine existant (listes d'applications, organisation) depuis des fichiers ou sources de l'organisme. | M | L1 |
| EX-REF-12 | Détection de **doublons** et de **chevauchements** fonctionnels entre applications (aide à la rationalisation). | S | L3 |
| EX-REF-13 | Statut de cycle de vie des applications (en projet → retirée) modifié via décisions tracées. | M | L1 |
| EX-REF-14 | Rapprochement avec des **solutions déjà disponibles** (applications existantes, solutions mutualisées ou libres connues de l'organisme) lors de l'instruction d'une demande. | C | L3 |
| EX-REF-15 | Gérer une **fiche initiative légère** (nom, responsable, équipe, applications liées, dates, statut, santé calculée et déclarée) pour permettre le rattachement des rapports de projet dès le lot 1 ; la gestion complète du portefeuille reste au lot 2. | M | L1 |
| EX-REF-16 | Gérer un **annuaire minimal des personnes** (nom, équipe, profil optionnel, rôles dans Odin) issu de l'identité de l'organisme ; quotités, affectations et temps sont du lot 3. | M | L1 |

## OBJ. Objectifs et stratégie

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-OBJ-01 | Gérer une **cascade d'objectifs** (stratégie de l'organisme → objectifs SI → initiatives → indicateurs). | M | L2 |
| EX-OBJ-02 | Un objectif a un responsable, une échéance, une cible, des indicateurs ; sa progression est calculée à partir de faits et d'initiatives. | M | L2 |
| EX-OBJ-03 | Un **indicateur** a une définition, une formule, des sources de faits, des seuils, une fréquence ; il est consultable par tous ceux qui le voient (définition transparente). | M | L2 |
| EX-OBJ-04 | Les objectifs peuvent être rattachés à des **orientations externes** saisies par l'organisme (plan de la tutelle, contrat d'objectifs) avec suivi de contribution. | S | L2 |
| EX-OBJ-05 | Une initiative sans objectif est marquée « hors stratégie » et visible comme telle. | M | L2 |
| EX-OBJ-06 | Les **revues d'objectifs** périodiques sont préparées automatiquement (état, écarts, décisions proposées). | S | L2 |
| EX-OBJ-07 | Les objectifs peuvent être **révisés** avec historique et motif. | M | L2 |
| EX-OBJ-08 | Un objectif peut être **atteint, abandonné ou reporté** avec justification. | M | L2 |

## POR. Demandes, portefeuille, initiatives

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-POR-01 | Tout agent peut **exprimer une demande** avec service rendu concerné, urgence, échéance, valeur attendue. | M | L2 |
| EX-POR-02 | Odin propose les **demandes similaires**, initiatives en cours et applications existantes avant l'envoi. | S | L2 |
| EX-POR-03 | Le demandeur **suit sa demande** et reçoit le motif de toute décision. | M | L2 |
| EX-POR-04 | Une **file de qualification** permet au PMO de compléter, demander des avis, fusionner, différer, refuser, instruire. | M | L2 |
| EX-POR-05 | Les demandes liées à une **contrainte externe à échéance ferme** sont marquées « non arbitrables » (RG-13) avec l'échéance. | M | L2 |
| EX-POR-06 | Le **portefeuille** liste toutes les initiatives (candidates et en cours) avec valeur, coût, ETP, risque couvert, dette traitée, dépendances. | M | L2 |
| EX-POR-07 | La **priorisation multicritère** est paramétrable (critères, pondérations) et **explicable** (contribution de chaque critère). | M | L2 |
| EX-POR-08 | Des **contraintes** (budget (nomenclature de l'organisme), capacité par profil, plafond d'effectifs éventuel, échéances) sont intégrées au calcul. | M | L3 |
| EX-POR-09 | La santé d'une initiative est **calculée** par règles paramétrables (délai, budget, risques, rapports) et comparée à la santé déclarée ; tout écart est signalé. | M | L2 |
| EX-POR-10 | Les **dépendances** entre initiatives, applications, fournisseurs, échéances sont gérées et visualisées. | M | L2 |
| EX-POR-11 | Les **bénéfices attendus** sont renseignés à l'engagement et **mesurés** au bilan. | S | L2 |
| EX-POR-12 | Le **coût du retard** et le **coût de l'inaction** sont estimés pour chaque initiative candidate (ou signalés comme non estimables). | S | L2 |
| EX-POR-13 | Les **jalons** et leur suivi (prévu/réel) sont gérés ; les dérives sont comparées à une cible paramétrable. | M | L2 |
| EX-POR-14 | Des **étapes d'avis ou de validation** (sécurité, finances, architecture, protection des données…) peuvent être **définies par l'organisme** (déclenchées par seuil, nature ou périmètre) ; Odin n'en impose aucune (RG-14). | S | L2 |
| EX-POR-15 | La clôture d'une initiative déclenche un **bilan** (réalisé vs prévu, bénéfices, enseignements). | M | L2 |
| EX-POR-16 | Les **enseignements** des bilans sont capitalisés et consultables (initiatives comparables). | C | L5 |

## ROA. Roadmaps et scénarios

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-ROA-01 | Gérer plusieurs **feuilles de route** (stratégique, de transformation, technologique/obsolescence, sécurité, par service rendu). | M | L2 |
| EX-ROA-02 | Affichage par **horizons** (maintenant / prochainement / plus tard) et en **calendrier**, avec filtres (objectif, équipe, application, service rendu, contrainte externe). | M | L2 |
| EX-ROA-03 | Une **vérification de cohérence** continue signale conflits de capacité, de budget, de dépendance, de fin de support, d'échéance légale. | M | L3 |
| EX-ROA-04 | Les roadmaps sont **versionnées** ; une version publiée est liée à une décision ; deux versions peuvent être comparées. | M | L2 |
| EX-ROA-05 | Des **scénarios** (hypothèses sur budget, ressources, calendrier, périmètre) sont comparés à la référence sans la modifier. | M | L3 |
| EX-ROA-06 | Un scénario affiche : initiatives qui tiennent, retardées, abandonnées ; effets en chaîne ; coût du report ; tensions de capacité. | M | L3 |
| EX-ROA-07 | **Analyse de sensibilité** des pondérations et hypothèses. | S | L5 |
| EX-ROA-08 | Des **vues de diffusion** (pour la direction, les tutelles) masquent automatiquement les éléments non autorisés. | S | L5 |
| EX-ROA-09 | Un scénario peut être **converti en proposition de décision** (note) ou **adopté** comme nouvelle version de référence après décision. | M | L3 |
| EX-ROA-10 | Les **échéances calendaires externes** (calendrier budgétaire, électoral, doctrinal) sont affichables en couche sur la roadmap. | S | L5 |

## DET. Dette et obsolescence

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-DET-01 | Tenir un **registre de dette** (typologie : code, architecture, infrastructure, tests, documentation, sécurité, données, fonctionnelle, organisationnelle). | M | L2 |
| EX-DET-02 | Les éléments de dette se créent par **signalement, faits extraits** ou saisie directe, avec responsable. | M | L2 |
| EX-DET-03 | Chaque élément porte **intérêt** (coût ou risque annuel, en fourchette si besoin), **effort**, **échéance critique** et **fiabilité de l'estimation**. | M | L2 |
| EX-DET-04 | Une **priorisation** proposée (intérêt/effort, urgence, criticité du service rendu, lien sécurité) est expliquée. | M | L2 |
| EX-DET-05 | Un élément est **planifié** dans une initiative, **accepté** avec justification et date de revue, ou **remboursé**. | M | L2 |
| EX-DET-06 | Suivi de la **dette globale** (par application, type, domaine) et de sa **tendance** ; suivi de la **part de capacité** consacrée à la dette face à l'objectif paramétré. | M | L2 |
| EX-DET-07 | **Obsolescence** : alertes sur les technologies en fin de support avec applications exposées et échéance. | M | L2 |
| EX-DET-08 | Le **lien dette ↔ risque de sécurité** est explicite (une dette peut créer ou aggraver un risque). | M | L4 |
| EX-DET-09 | La dette est présentée à la direction en **langage de décision** : coût, risque, délai, service rendu menacé. | M | L2 |
| EX-DET-10 | Les éléments acceptés sont **réévalués** à leur date de revue. | S | L2 |
| EX-DET-11 | Les **indicateurs de dette issus d'outils de mesure** (qualité de code, vulnérabilités) peuvent alimenter des faits F3. | C | L6 |

## RSR. Ressources (équipes, profils, ETP)

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-RSR-01 | Gérer un **référentiel de profils** (familles et profils de métiers du numérique, D2, D12), de **compétences** et les **personnes** (nom, équipe, profil, statut, quotité, compétences déclarées). | M | L3 |
| EX-RSR-02 | Gérer la **capacité par équipe et par profil** (internes titulaires, contractuels, prestataires) en ETP, avec hypothèses explicites (congés, part de run, productivité). | M | L3 |
| EX-RSR-03 | Gérer la **demande de charge** par initiative, run, dette, contraintes externes, par profil et période. | M | L3 |
| EX-RSR-04 | Afficher **capacité vs demande** et **taux de charge agrégés** ; signaler les tensions par profil et par compétence rare. | M | L3 |
| EX-RSR-05 | Gérer les **postes vacants** et besoins de recrutement par profil (durée de vacance, tension, impact sur initiatives). | M | L3 |
| EX-RSR-06 | Suivre la **dépendance aux prestataires** (part par équipe, par application, par profil ; échéance de contrats). | M | L3 |
| EX-RSR-07 | Suivre, **si l'organisme en a un**, un **plafond d'effectifs** (en ETPT ou autre unité) ; **règle de conversion ETP ↔ unité du plafond** visible (RG-16). | S | L3 |
| EX-RSR-08 | **Aucune vue ni export n'évalue, ne note, ne classe ni ne compare des personnes** (RG-01) ; les données nominatives (affectations, temps, compétences) ne sont visibles que des rôles habilités et de la personne concernée ; les audiences larges voient des agrégats (RG-02). | M | L3 |
| EX-RSR-09 | Identifier les **risques de dépendance à un rôle, une compétence ou une personne** (fonction portée par peu de personnes) ; visible des rôles habilités. | S | L3 |
| EX-RSR-10 | Intégrer dans les **scénarios** des variations de capacité (recrutement, renfort, redéploiement). | M | L3 |
| EX-RSR-11 | Visualiser l'**évolution** de la capacité et des vacances dans le temps. | S | L3 |
| EX-RSR-12 | Alimentation possible depuis des **sources RH** de l'organisme (personnes, équipes, quotités). | S | L3 |
| EX-RSR-13 | Gérer les **plans de formation** au niveau profil et compétence. | C | L6 |
| EX-RSR-14 | Gérer les **affectations** : répartition de chaque personne entre initiatives et applications (quotité, période), **charge prévue** par personne, équipe et profil ; **alerte de sur-affectation** (> 100 %). | M | L3 |
| EX-RSR-15 | Une personne voit **ses propres affectations et temps** ; les corrections passent par son responsable. | S | L3 |

## FIN. Finances

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-FIN-01 | Gérer le **budget** par exercice selon la **nomenclature de l'organisme** (niveaux paramétrables : par exemple programme, action, titre de dépense ; engagements et paiements si applicable). | M | L3 |
| EX-FIN-02 | Enregistrer ou importer les **dépenses** et les **imputer** aux applications, initiatives et services rendus avec règles d'allocation visibles. | M | L3 |
| EX-FIN-03 | Distinguer **run** et **build** ; afficher leur part et leur tendance. | M | L3 |
| EX-FIN-04 | Calculer le **coût complet** d'une application ou d'un service rendu (hors valorisation individuelle de personnes). | M | L3 |
| EX-FIN-05 | **Consolider la dépense numérique** de l'organisme (vue reproductible, exportable). | M | L3 |
| EX-FIN-06 | **Prévisions** et projections de consommation sur l'exercice. | S | L3 |
| EX-FIN-07 | Détecter les **écarts** entre budgets déclarés dans les rapports et données financières. | S | L3 |
| EX-FIN-08 | Suivre la **réalisation des bénéfices financiers** attendus par initiative. | S | L5 |
| EX-FIN-09 | Fournir un **dossier d'arbitrage budgétaire** (besoins, options, impacts, coût de l'inaction). | M | L5 |
| EX-FIN-10 | Suivre les **dépenses d'IA** (licences, services) comme catégorie à part. | C | L5 |
| EX-FIN-12 | **Saisie manuelle assistée** du budget et des dépenses (grille, copier-coller depuis un tableur, import de fichier) avec **contrôles** (totaux, cohérence, doublons, imputations manquantes), historique des versions et **validation par le contrôle de gestion** ; fiabilité maximale F2 sauf pièce justificative (D10). | M | L3 |

## FOU. Fournisseurs, marchés, licences

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-FOU-01 | Gérer **fournisseurs**, **marchés/contrats** et **licences** avec dates (début, fin, préavis, reconduction), montants, applications couvertes. | M | L3 |
| EX-FOU-02 | **Alertes d'échéance** graduées (par exemple 180/90/30 jours, paramétrables) vers les responsables, avec décisions à prendre. | M | L3 |
| EX-FOU-03 | **Analyse de dépendance** (part de dépense, criticité des services, difficultés de sortie). | M | L3 |
| EX-FOU-04 | **Scénario de sortie** d'un fournisseur : applications touchées, effort, délai, coût. | S | L5 |
| EX-FOU-05 | Rapprochement **licences acquises vs utilisées** (quand les données existent). | C | L6 |
| EX-FOU-06 | **Rétro-planning de remise en concurrence** à partir de l'échéance. | S | L3 |
| EX-FOU-07 | Suivi du **mode d'hébergement ou de fourniture** d'un service (interne, externe, localisation) comme information déclarée, avec source. | S | L4 |
| EX-FOU-08 | Les **clauses clés** (réversibilité, sécurité, localisation) sont consultables par contrat (champ structuré, pas d'analyse juridique). | C | L6 |

## SEC. Sécurité, risques, continuité

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-SEC-01 | Gérer un **registre de risques** (gravité, vraisemblance, risque résiduel, traitement, acceptation formelle datée et attribuée). | M | L4 |
| EX-SEC-02 | Gérer **mesures et plans d'action**, avec responsable et échéance. | M | L4 |
| EX-SEC-03 | Suivre les **évaluations et autorisations de sécurité** (homologation ou équivalent selon l'organisme) : validité, réserves, échéance. | M | L4 |
| EX-SEC-04 | Suivre **constats d'audit et de tests** et leur remédiation. | M | L4 |
| EX-SEC-05 | Suivre **dérogations/exceptions** avec échéance et revue. | S | L4 |
| EX-SEC-06 | Afficher une **posture de sécurité** par domaine et par application, avec tendance. | M | L4 |
| EX-SEC-07 | Les rapports de sécurité déposés alimentent des faits N4 **validés par le RSSI** ; leur affichage est restreint. | M | L4 |
| EX-SEC-08 | Suivre **criticité et continuité** (objectifs de reprise, date du dernier test de continuité) par application et service rendu. | M | L4 |
| EX-SEC-09 | Produire une **vue de direction** de la sécurité sans détail technique exploitable. | M | L4 |
| EX-SEC-10 | **Lien risque ↔ dette ↔ obsolescence ↔ initiative** navigable dans les deux sens. | M | L4 |
| EX-SEC-11 | Suivre les **risques liés aux tiers** (fournisseurs critiques, dépendances). | S | L4 |
| EX-SEC-12 | Prendre en compte les **échéances de sécurité externes** saisies comme contraintes (EX-REG-01). | S | L4 |
| EX-SEC-13 | **Quantification** du risque en coût (fourchettes) lorsque possible, signalée comme estimation. | C | L6 |
| EX-SEC-14 | S'interfacer avec des **outils de gestion des risques** existants plutôt que les remplacer (alimentation/import). | S | L4 |

## REG. Contraintes et échéances externes

Odin **ne livre aucun registre de textes ni de procédures** (D5). L'organisme saisit ce qui s'impose à lui.

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-REG-01 | Saisir et gérer des **contraintes externes** (libellé, **source en texte libre**, nature, échéance, responsable, applicabilité, état). | M | L2 |
| EX-REG-02 | **Rattacher** une contrainte à des applications, initiatives, équipes. | M | L2 |
| EX-REG-03 | Afficher un **calendrier consolidé** des échéances, activable en couche sur les roadmaps. | M | L2 |
| EX-REG-04 | **Alertes** graduées (paramétrables) à l'approche des échéances. | M | L2 |
| EX-REG-05 | Marquer une contrainte **« non arbitrable »** : elle alimente priorisation, roadmap et scénarios (RG-13). | M | L2 |
| EX-REG-06 | Proposer de **rattacher à une contrainte** les rapports et faits qui la mentionnent (à confirmer par un humain). | S | L2 |
| EX-REG-07 | Signaler les contraintes **non revues depuis un délai paramétrable** (« à revoir »). | S | L2 |
| EX-REG-08 | **Importer** une liste de contraintes existante de l'organisme (fichier). | S | L2 |

## DEC. Décisions et comités

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-DEC-01 | Gérer des **instances** (nom, composition par rôles, périodicité, ordre du jour type). | M | L2 |
| EX-DEC-02 | Préparer un **ordre du jour** à partir des sujets en attente, signaux, échéances. | S | L2 |
| EX-DEC-03 | Générer une **note de décision** structurée (décision demandée, contexte, options dont « ne rien faire », impacts, recommandation, sources). | M | L5 |
| EX-DEC-04 | Enregistrer une **décision** (choix, motifs, hypothèses, responsables, échéances, bénéfices attendus). | M | L2 |
| EX-DEC-05 | Une décision **contraire à la recommandation** exige un motif. | S | L2 |
| EX-DEC-06 | Générer un **compte rendu** en brouillon, validé par le secrétaire de séance. | S | L5 |
| EX-DEC-07 | Une décision crée automatiquement ses **suites** (actions, jalons, mises à jour de roadmap, d'objets). | M | L2 |
| EX-DEC-08 | Une **date de bilan** est posée ; un rappel déclenche la comparaison attendu/constaté. | M | L2 |
| EX-DEC-09 | Le **registre des décisions** est consultable (par objet, instance, période) selon les droits ; les décisions restreintes sont masquées aux non-habilités. | M | L2 |
| EX-DEC-10 | La **photo des faits** au jour de la décision est conservée (preuve reproductible). | M | L2 |
| EX-DEC-12 | Gérer les **étapes d'avis** définies par l'organisme et liées à une décision (voir EX-POR-14). | S | L2 |
| EX-DEC-13 | Une décision peut être **révisée** ; l'historique reste intact. | M | L2 |

## TDB. Tableaux de bord et alertes

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-TDB-01 | Une **vue stratégique** pour la direction (objectifs, portefeuille, dette, sécurité, ressources, finances, contraintes externes, contrats, décisions à prendre). | M | L1 |
| EX-TDB-02 | Chaque indicateur affiche **valeur, tendance, fiabilité, fraîcheur** et un lien « Pourquoi ? » vers ses faits et sources. | M | L1 |
| EX-TDB-03 | Les indicateurs dont les faits ne sont pas validés sont **distingués** (mention « déclaratif »). | M | L1 |
| EX-TDB-04 | Des **tableaux de bord par rôle** : responsable d'application, de projet, d'équipe, architecte, RSSI, finances, RH, PMO. | M | L1 |
| EX-TDB-05 | **Alertes et seuils** paramétrables, avec notification et inscription à un comité. | M | L2 |
| EX-TDB-06 | Distinction **indicateurs avancés / retardés** dans le catalogue. | S | L2 |
| EX-TDB-07 | **Historique et comparaison** dans le temps (périodes, versions de roadmap). | M | L2 |
| EX-TDB-08 | Le **catalogue d'indicateurs** (fichier 09 §3) est utilisé avec **définition accessible** pour chacun ; tout indicateur sans décision associée peut être retiré. | M | L1 |
| EX-TDB-09 | **Feux de santé** calculés par seuils objectifs (RG-08), jamais saisis librement ; toute dérogation est tracée. | M | L1 |
| EX-TDB-10 | **Benchmark interne** (comparaison entre périodes et équipes agrégées) et, si des données publiques existent, **externe**. | C | L6 |

## RST. Restitutions

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-RST-01 | Produire des **synthèses** d'un objet, d'un périmètre ou d'une période, avec sources. | M | L1 |
| EX-RST-02 | Produire un **résumé périodique** (hebdomadaire/mensuel) pour la direction, diffusable automatiquement. | S | L1 |
| EX-RST-03 | Produire des **rapports de direction** (rapport d'activité, revue de portefeuille, bilan trimestriel, point sécurité, dossier d'arbitrage). | M | L5 |
| EX-RST-04 | Produire des **présentations** par audience (comité, direction générale, tutelle, élus, équipes) avec structure, graphiques et texte. | M | L5 |
| EX-RST-05 | **Chaque chiffre est lié à ses faits sources** ; les passages produits par l'IA sont signalés. | M | L1 |
| EX-RST-06 | L'utilisateur **édite** librement le contenu généré ; l'IA reformule/ajuste le ton sur demande. | M | L5 |
| EX-RST-07 | Le **niveau de classification** d'une restitution est hérité des sources ; l'export vers une audience non habilitée est bloqué ou masque les éléments non autorisés (RG-04). | M | L1 |
| EX-RST-08 | Avertissement si des faits **non validés** sont utilisés ; option de les exclure. | M | L1 |
| EX-RST-09 | **Exports** en formats bureautiques courants **et ouverts**, avec charte graphique de l'organisme. | M | L5 |
| EX-RST-10 | Les restitutions sont **versionnées** et conservent la **photo des données** (reproductibilité). | S | L5 |
| EX-RST-11 | Workflow de **validation** avant diffusion pour certains types de restitution. | S | L5 |
| EX-RST-12 | **Gabarits de restitution** gérés par l'administrateur (structure, mentions, charte). | S | L5 |
| EX-RST-13 | **Accessibilité** des documents exportés (structure, textes alternatifs) selon le référentiel applicable. | S | L5 |
| EX-RST-14 | Mention **« généré avec l'aide de l'IA »** sur les documents concernés (configurable pour usage interne, obligatoire pour diffusion externe). | M | L1 |

## ASS. Assistant

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-ASS-01 | Poser une **question en langage naturel** depuis n'importe quel écran. | M | L1 |
| EX-ASS-02 | Les réponses sont **sourcées** (liens vers rapports, faits, objets) avec fiabilité et fraîcheur. | M | L1 |
| EX-ASS-03 | L'assistant **ne répond qu'avec ce que l'utilisateur est autorisé à voir** (RG-04). | M | L1 |
| EX-ASS-04 | Lorsque l'information manque, l'assistant **le dit** et indique qui interroger ; il n'invente jamais. | M | L1 |
| EX-ASS-05 | L'assistant **refuse** les demandes d'évaluation ou de classement de personnes et les atteintes à la confidentialité, avec explication (RG-01). | M | L1 |
| EX-ASS-06 | L'assistant propose des **actions** (ouvrir une fiche, créer une demande, demander une précision, produire un rapport). | S | L1 |
| EX-ASS-07 | Retour utilisateur sur chaque réponse (utile / inexacte / incomplète). | M | L1 |
| EX-ASS-08 | Suggestions de questions selon le rôle. | C | L1 |
| EX-ASS-09 | L'historique des questions de l'utilisateur est **privé** pour lui ; l'usage est journalisé pour l'audit selon la politique (RG-22). | M | L1 |
| EX-ASS-10 | Questions sur **données chiffrées** : l'assistant s'appuie sur les indicateurs calculés, pas sur des estimations libres. | M | L1 |

## QUA. Qualité des données

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-QUA-01 | Un écran de **santé du référentiel** : couverture, fraîcheur, faits en attente, orphelins, doublons, contradictions. | M | L1 |
| EX-QUA-02 | **Files de travail** de curation (validation second niveau, fusions, rattachements ambigus). | M | L1 |
| EX-QUA-03 | **Relances** préparées, sobres, sans formulation accusatrice, vers les responsables en retard. | S | L1 |
| EX-QUA-04 | Suivi de la **qualité de l'IA** (taux de corrections et de rejets par type de rapport, retours utilisateurs). | M | L1 |
| EX-QUA-05 | Alerte de direction sur **couverture insuffisante** (absence d'information sur des objets critiques), exprimée comme un problème de dispositif, pas de personne. | S | L2 |
| EX-QUA-06 | Chaque indicateur montre sa **complétude** (part des objets couverts). | M | L1 |

## NOT. Notifications et collaboration

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-NOT-01 | Notifications dans l'application et par courriel (au choix) pour : faits à relire, validations, précisions, échéances, décisions, retours. | M | L1 |
| EX-NOT-02 | Chaque utilisateur règle ses **préférences** (fréquence, canaux, regroupement). | M | L1 |
| EX-NOT-03 | **Demandes de précision** (P-06) avec choix prédéfinis, relance, escalade tracée. | M | L1 |
| EX-NOT-04 | **Commentaires** et mentions sur objets et restitutions, dans les droits. | S | L2 |
| EX-NOT-05 | Les notifications **ne divulguent jamais** de contenu N3/N4 à un non-habilité (message neutre). | M | L1 |
| EX-NOT-06 | **Boîte de tâches** personnelle (à relire, à valider, à répondre, à décider). | M | L1 |
| EX-NOT-07 | Rappels **calendaires** (rapport mensuel, bilan de décision, échéance de contrat). | M | L1 |

## ALI. Alimentations (sources de données)

Sources identifiées (D10) : outil de suivi de projets (Jira), imputation des temps, fichiers. **Les finances n'ont pas de source automatique** (voir EX-FIN-12). Sans alimentation, Odin fonctionne en mode déclaratif.

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-ALI-01 | **Alimentation depuis l'outil de suivi de projets** : avancement, jalons, volumes de travail, états ; correspondance configurable entre projets de l'outil et initiatives, applications, équipes d'Odin. Ces faits sont de niveau F3 (« alimenté »). | M | L2 |
| EX-ALI-02 | **Alimentation des temps imputés** : temps par **personne × initiative × période** et agrégats par équipe et profil ; visibilité selon droits ; jamais utilisés pour évaluer (RG-01, RG-38). | M | L3 |
| EX-ALI-03 | **File de correspondance** : projets, équipes ou profils non reconnus sont proposés à un humain pour rapprochement ; aucune donnée non rapprochée n'alimente un indicateur. | M | L2 |
| EX-ALI-04 | Chaque alimentation déclare sa **fiabilité**, sa **fréquence**, son **périmètre**, sa **dernière exécution réussie** ; les échecs sont visibles par l'administration. | M | L2 |
| EX-ALI-05 | **Détection d'écarts** entre données alimentées et faits déclarés (avancement, charge) ; signal et demande de précision (EX-IAF-08). | M | L2 |
| EX-ALI-06 | Comparer **charge réelle (temps imputés)** et **charge prévue** par profil et initiative ; écarts remontés dans les scénarios et la capacité. | S | L3 |
| EX-ALI-07 | Une alimentation peut être **suspendue** ou **désactivée** sans perte de l'historique ; Odin reste utilisable en déclaratif. | M | L2 |
| EX-ALI-08 | **Import de fichiers** (tableur, texte structuré) comme alimentation générique pour toute donnée sans source automatique. | M | L1 |
| EX-ALI-09 | Les **temps imputés** sont visibles des seuls rôles habilités et de la personne concernée ; les vues larges sont agrégées (RG-02). | M | L3 |

## ADM. Administration

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-ADM-01 | Gérer **organisation**, équipes, référentiels (profils, types de rapports, natures de faits), **sans développement**. | M | L1 |
| EX-ADM-02 | Gérer les **gabarits** de rapports et de restitutions. | M | L1 |
| EX-ADM-03 | Gérer **seuils, règles de santé, grille de priorisation, seuil d'agrégation, niveaux de classification, politique de conservation**. | M | L1 |
| EX-ADM-04 | **Aperçu d'impact** avant d'appliquer une modification de règle ; journal des modifications. | M | L1 |
| EX-ADM-05 | Gérer les **rôles, périmètres, délégations, expirations**. | M | L1 |
| EX-ADM-06 | Gérer le **calendrier des instances** et les modèles de contraintes. | M | L2 |
| EX-ADM-07 | Paramétrer les **sources d'alimentation** (fonctionnellement : quelles données, quelle fréquence, quelle fiabilité). | S | L3 |
| EX-ADM-08 | **Import/export** des référentiels. | M | L1 |
| EX-ADM-09 | Gérer le **vocabulaire** (libellés) pour s'adapter à l'organisme. | S | L1 |
| EX-ADM-10 | L'administrateur fonctionnel **n'accède pas par défaut** aux contenus N3/N4. | M | L1 |

## AUD. Audit et traçabilité

| ID | Exigence | Prio | Lot |
|---|---|---|---|
| EX-AUD-01 | **Journal** immuable des actions significatives (dépôt, validation, rejet, décision, modification de règle, accès N4, export, usage de l'IA). | M | L1 |
| EX-AUD-02 | Le journal est consultable par l'auditeur, le DPO (périmètre données personnelles/IA) et le RSSI (périmètre sécurité). | M | L1 |
| EX-AUD-03 | **Dossier de preuve** d'une décision (options, critères, hypothèses, faits au jour J, versions). | M | L2 |
| EX-AUD-04 | **Traçabilité de bout en bout** : de tout chiffre à ses faits, rapports, auteurs et validateurs. | M | L1 |
| EX-AUD-05 | **Registre d'usage de l'IA** : quelles analyses, quels modèles/versions, quels périmètres, quelles corrections humaines. | M | L1 |
| EX-AUD-06 | **Exports d'audit** reproductibles. | S | L6 |
| EX-AUD-07 | Politique de **conservation et d'effacement** appliquée et traçable (RG-20, RG-21). | M | L1 |

---

## Traçabilité parcours → modules

| Parcours | Modules principaux |
|---|---|
| P-01 | ACC, NOT |
| P-02, P-03, P-04 | RAP, IAF, ACC, NOT |
| P-05, P-06 | IAF, NOT, RAP |
| P-07 | RAP, IAF |
| P-08 | REF, IAF, DET, SEC, FIN |
| P-09 | POR, ROA, FIN, RSR, IAF, ALI |
| P-10, P-11 | POR, REG, IAF |
| P-12, P-13 | POR, ROA, RSR, FIN, DET, REG, DEC |
| P-14 | DET, SEC, POR, ROA |
| P-15 | RSR, POR, ROA |
| P-15, P-16, P-17 | RSR, FIN, FOU, DEC, ALI |
| P-18 | SEC, DET, DEC |
| P-19 | REG, ROA, POR |
| P-20 | DEC, RST, POR, ROA |
| P-21 | RST, IAF, TDB |
| P-22 | ASS, IAF |
| P-23 | TDB, OBJ, RST |
| P-24 | AUD, DEC, FIN |
| P-25 | QUA, IAF, NOT |
| P-26, P-27 | ADM, ACC, RAP |
