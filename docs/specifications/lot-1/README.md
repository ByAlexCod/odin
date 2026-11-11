# Lot 1 : Contribution et compréhension. Spécification détaillée

Version 0.1, 11 novembre 2026. Complète le dossier principal (`../README.md`). **Métier et UX uniquement** : aucun choix technique.

## 1. Objet du lot

Valider l'hypothèse centrale du produit : **tout le monde dépose des rapports ; l'IA propose des faits ; des humains les confirment et les valident ; la direction voit une première vue fiable et peut interroger Odin.** Le lot est utilisable seul, sans les lots suivants (portefeuille, ressources, finances, sécurité détaillée, restitutions avancées).

**Ce que l'utilisateur peut faire à la fin du lot 1**
- Se connecter, comprendre ce qu'Odin fait et ne fait pas (pas d'évaluation des personnes).
- Déposer un rapport ou un signalement en moins de 2 minutes, ou rédiger avec un gabarit guidé.
- Relire, corriger, confirmer ou rejeter les faits proposés par l'IA ; valider les faits de son périmètre.
- Voir, sur une fiche application ou initiative, une **santé calculée et justifiée**, des faits sourcés, la fraîcheur.
- Répondre aux contradictions et demandes de précision.
- Interroger l'assistant (réponses sourcées, dans les droits de l'utilisateur).
- Pour la direction : une **vue stratégique réduite** (8 tuiles), avec fiabilité, fraîcheur et « Pourquoi ? ».
- Pour l'administration : importer le référentiel, régler seuils et rôles, consulter le journal d'audit.

## 2. Contenu du dossier du lot

| Fichier | Contenu |
|---|---|
| [01-ecrans-detailles.md](01-ecrans-detailles.md) | 21 écrans : contenu, champs, actions, états, règles, tests liés |
| [02-regles-et-calculs.md](02-regles-et-calculs.md) | Paramètres initiaux, santé, contradictions, péremption, droits, indicateurs, import |
| [03-catalogue-des-faits.md](03-catalogue-des-faits.md) | Natures de faits, champs, validations, exemples positifs et négatifs |
| [04-cas-de-test.md](04-cas-de-test.md) | 219 cas de test de recette |
| [05-jeux-de-donnees.md](05-jeux-de-donnees.md) | Organisme fictif, personnes, applications, 17 rapports de référence avec résultats attendus, 10 scénarios |
| [06-messages-et-textes.md](06-messages-et-textes.md) | Textes de l'interface, refus, avertissements, notifications |

## 3. Périmètre précis

### 3.1 Inclus
- Les **101 exigences** marquées L1 (liste au §4).
- Parcours : P-01 à P-08, P-09 (version légère : rapport d'avancement, santé simple), P-22, P-23 (vue réduite), P-25, P-26 (base), P-27.
- Écrans : E-01, E-00, E-02 à E-10L, E-24, E-25 (réduite), E-27, E-28 (base), E-29 à E-34.
- Gabarits : **G-01, G-02, G-04, G-05, G-09, G-18** (les types G-03, G-06, G-14 sont **reconnus** à l'extraction mais sans gabarit guidé).
- Natures de faits : avancement, jalon, budget (déclaré), risque, incident, dette (dont fin de support), sécurité, ressources, dépendance, décision, bénéfice, satisfaction, signal faible.
- Indicateurs : L1-I01 à L1-I12.
- Objets : application, équipe, service rendu, initiative (**fiche légère**), personne (**annuaire minimal**), rapport, fait, signal, demande de précision, journal.

### 3.2 Précisions de périmètre (arbitrées pour rendre le lot cohérent)
1. **Fiche initiative légère** (EX-REF-15) : nécessaire pour rattacher les rapports d'avancement dès le lot 1. Pas de portefeuille, de scénarios ni d'ETP (lots 2 et 3).
2. **Annuaire minimal des personnes** (EX-REF-16) : nom, équipe, profil facultatif, rôles dans Odin. Pas de quotités, d'affectations ni de temps (lot 3).
3. **Faits d'affectation nominatifs** : l'IA peut les extraire (F0), mais ils sont **restreints** aux rôles habilités et **n'alimentent aucun indicateur** avant le lot 3.
4. **Finances** : seuls les budgets **déclarés dans les rapports** sont extraits (plafond F2) ; la saisie manuelle assistée et la consolidation sont du lot 3.
5. **Alimentations** : au lot 1, seul l'**import de fichiers** (EX-ALI-08). Jira est du lot 2, les temps imputés du lot 3.
6. **Sécurité** : le lot 1 extrait et affiche des **faits de sécurité** (niveau N4, validation par le rôle sécurité) et un indicateur **agrégé**. Le registre de risques, les homologations et les plans d'action sont du lot 4.
7. **Décisions** : le lot 1 conserve des faits « décision attendue / prise » ; le registre des décisions, les comités et les notes sont du lot 2.

### 3.3 Exclu du lot 1
Portefeuille et priorisation, roadmaps et scénarios, registre de dette complet, capacité et affectations, finances et contrats, registre de risques, contraintes et échéances externes, notes de décision, rapports de direction et présentations générés, benchmark.

## 4. Exigences du lot 1 (extraites du fichier 05 du dossier principal)

### ACC. Accès et rôles (10)

| ID | Exigence | Prio |
|---|---|---|
| EX-ACC-01 | Tout agent de l'organisme peut se connecter avec son identité professionnelle et obtient le rôle Contributeur par défaut. | M |
| EX-ACC-02 | Des prestataires peuvent être autorisés avec le rôle Contributeur externe, limité à des périmètres et à une durée. | M |
| EX-ACC-03 | Un utilisateur peut cumuler plusieurs rôles ; ses vues s'adaptent à ses rôles (navigation simplifiée pour le contributeur). | M |
| EX-ACC-04 | Les droits sont attribués à un rôle sur un périmètre (équipe, direction, application, projet, domaine). | M |
| EX-ACC-05 | Les délégations temporaires de validation sont possibles, tracées et expirent automatiquement. | S |
| EX-ACC-06 | À l'arrivée d'un agent, Odin propose son équipe et ses objets de référence ; à son départ, Odin impose la réattribution de ses objets (P-27). | M |
| EX-ACC-07 | L'utilisateur peut consulter la liste des droits dont il dispose et leur origine. | S |
| EX-ACC-08 | Les accès aux contenus N4 sont soumis à une habilitation explicite par le rôle responsable du domaine. | M |
| EX-ACC-09 | Un message d'information expliquant ce qu'Odin fait et ne fait pas (dont « n'évalue pas les personnes ») est présenté à la première connexion et reste accessible. | M |
| EX-ACC-10 | Les contributeurs externes ne voient aucun contenu N1 à N4 hors de leur périmètre explicitement ouvert. | M |

### RAP. Rapports (19)

| ID | Exigence | Prio |
|---|---|---|
| EX-RAP-01 | Depuis n'importe quel écran, un utilisateur peut **partager un rapport** en glissant un document, en collant un texte ou en transférant un message. | M |
| EX-RAP-02 | Le dépôt nécessite au plus un clic de validation ; type, rattachements, période et niveau sont proposés et modifiables. | M |
| EX-RAP-03 | Les types de documents bureautiques courants (texte, tableur, présentation, document portable, texte brut, courriel) sont acceptés ; une indication claire est donnée en cas de format illisible. | M |
| EX-RAP-04 | L'utilisateur peut rédiger un rapport dans Odin avec un **gabarit guidé** (bibliothèque de gabarits, fichier 09), préremplie depuis les faits validés. | M |
| EX-RAP-05 | Les brouillons sont enregistrés automatiquement et repris ultérieurement. | M |
| EX-RAP-06 | Chaque rapport a une version ; un nouveau dépôt peut **remplacer** une version, l'historique des versions reste consultable. | M |
| EX-RAP-07 | Un rapport a un type, une période couverte, un auteur, des rattachements (applications, projets, équipes, services rendus), un niveau de classification et un statut de cycle de vie (fichier 03 §5.1). | M |
| EX-RAP-08 | Un rapport « officiel » (par ex. rapport d'avancement) peut être soumis à **validation** d'un responsable avant d'être marqué officiel. | S |
| EX-RAP-09 | L'utilisateur dispose d'une **bibliothèque de rapports** filtrable (type, période, objet, auteur, statut, niveau) limitée à ses droits. | M |
| EX-RAP-10 | Le texte intégral des rapports accessibles est **recherchable**. | M |
| EX-RAP-11 | Les rapports ont une durée de validité par type ; à expiration ils passent à *périmé* ; ils peuvent être archivés. | M |
| EX-RAP-12 | L'auteur peut **retirer** un rapport, sous les règles de conservation et de traçabilité (RG-20, RG-21). | M |
| EX-RAP-13 | Une détection de **doublons** propose de remplacer ou de rattacher plutôt que de dupliquer. | S |
| EX-RAP-14 | L'auteur voit **ce que son rapport a changé** (faits utilisés, objets mis à jour, décisions citant) dans les limites de ses droits. | M |
| EX-RAP-15 | Des **demandes de rapport** peuvent être émises (par un PMO, un responsable) vers un auteur ou une équipe, avec échéance et gabarit. | S |
| EX-RAP-16 | Des **rappels de dépôt périodique** (rapport mensuel) sont envoyés avec le gabarit prérempli. | S |
| EX-RAP-18 | Le **signalement court** (risque, problème, dette, idée, besoin) est possible en moins de 30 secondes, avec option de visibilité restreinte (P-04). | M |
| EX-RAP-19 | Un message dirigeant vers la **procédure d'alerte protégée** de l'organisme est affiché lorsque le contenu relève de ce cadre (RG-24). | M |
| EX-RAP-20 | Le contributeur peut **exporter** ses propres rapports et leur historique. | S |

### IAF. Faits et compréhension IA (15)

| ID | Exigence | Prio |
|---|---|---|
| EX-IAF-01 | À chaque dépôt, Odin analyse le rapport et propose : type, résumé court, rattachements, niveau de classification, faits extraits. | M |
| EX-IAF-02 | Les faits extraits suivent le catalogue des natures de faits (fichier 06 §3) : avancement, jalon, risque, incident, dépendance, besoin ou capacité en ressources, budget, dette, sécurité, contrainte externe, bénéfice, fournisseur, décision. | M |
| EX-IAF-03 | Chaque fait proposé indique son **extrait source**, sa **valeur**, son **objet rattaché**, sa **date de validité** et un niveau de **confiance**. | M |
| EX-IAF-04 | Un fait est d'abord **proposé (F0)** et ne peut alimenter un indicateur de direction qu'après confirmation et validation (RG-05). | M |
| EX-IAF-05 | L'auteur peut **confirmer, corriger, rejeter** chaque fait, individuellement ou en lot, depuis un écran à deux volets document/faits (E-06). | M |
| EX-IAF-06 | Le responsable de l'objet (application, projet…) et les curateurs peuvent **valider** (F2) les faits d'un objet ; les faits issus de plusieurs rapports sont présentés ensemble. | M |
| EX-IAF-07 | Les faits sont **historisés** : chaque valeur garde sa date, ses sources, ses validations et ses remplacements. | M |
| EX-IAF-08 | Odin détecte les **contradictions** entre faits (deux dates différentes, deux statuts, un statut déclaré incompatible avec des signaux) et génère un **signal** puis, si nécessaire, une **demande de précision**. | M |
| EX-IAF-10 | Odin signale les **données personnelles** et **contenus sensibles** détectés avant publication et propose masquage ou restriction (IA-07, IA-08). | M |
| EX-IAF-11 | L'IA ne crée aucun fait évaluatif portant sur une personne identifiable (RG-01, IA-08). | M |
| EX-IAF-12 | Les contenus déposés sont traités comme des données, jamais comme des instructions ; les tentatives sont consignées (IA-12). | M |
| EX-IAF-13 | Les utilisateurs peuvent donner un **retour qualité** sur chaque fait et chaque réponse (exact, inexact, incomplet). | M |
| EX-IAF-14 | Le rattachement d'un fait à plusieurs objets est possible ; un rattachement ambigu est proposé à un curateur. | S |
| EX-IAF-15 | Un fait peut aussi être **saisi directement** sans rapport (avec rattachement et justification) ; il est alors marqué « saisie manuelle ». | M |
| EX-IAF-17 | Une **synthèse multi-rapports** (par objet, par période, par thème) est disponible avec citations. | M |

### REF. Référentiel du SI (10)

| ID | Exigence | Prio |
|---|---|---|
| EX-REF-01 | Gérer les **applications** avec leur fiche (OBJ-12), responsable, équipe, services rendus servis, criticité, cycle de vie. | M |
| EX-REF-02 | Gérer les **équipes** : rattachement, applications portées, **membres**, effectif par profil. | M |
| EX-REF-03 | Gérer les **services rendus** et leurs liens avec applications et processus ; calculer la criticité de continuité. | M |
| EX-REF-06 | La **fiche application** présente une synthèse (santé calculée, fraîcheur, faits à valider) et des onglets (rapports, dette, risques, technologies, contrats, coûts, équipe, historique). | M |
| EX-REF-07 | Le référentiel se **met à jour par les faits validés** (pas de ressaisie par fiche). | M |
| EX-REF-08 | Une application sans responsable, sans équipe ou sans rapport récent est signalée « orpheline » ou « périmée ». | M |
| EX-REF-11 | **Import initial** du patrimoine existant (listes d'applications, organisation) depuis des fichiers ou sources de l'organisme. | M |
| EX-REF-13 | Statut de cycle de vie des applications (en projet → retirée) modifié via décisions tracées. | M |
| EX-REF-15 | Gérer une **fiche initiative légère** (nom, responsable, équipe, applications liées, dates, statut, santé calculée et déclarée) pour permettre le rattachement des rapports de projet dès le lot 1 ; la gestion complète du portefeuille reste au lot 2. | M |
| EX-REF-16 | Gérer un **annuaire minimal des personnes** (nom, équipe, profil optionnel, rôles dans Odin) issu de l'identité de l'organisme ; quotités, affectations et temps sont du lot 3. | M |

### NOT. Notifications (6)

| ID | Exigence | Prio |
|---|---|---|
| EX-NOT-01 | Notifications dans l'application et par courriel (au choix) pour : faits à relire, validations, précisions, échéances, décisions, retours. | M |
| EX-NOT-02 | Chaque utilisateur règle ses **préférences** (fréquence, canaux, regroupement). | M |
| EX-NOT-03 | **Demandes de précision** (P-06) avec choix prédéfinis, relance, escalade tracée. | M |
| EX-NOT-05 | Les notifications **ne divulguent jamais** de contenu N3/N4 à un non-habilité (message neutre). | M |
| EX-NOT-06 | **Boîte de tâches** personnelle (à relire, à valider, à répondre, à décider). | M |
| EX-NOT-07 | Rappels **calendaires** (rapport mensuel, bilan de décision, échéance de contrat). | M |

### ASS. Assistant (10)

| ID | Exigence | Prio |
|---|---|---|
| EX-ASS-01 | Poser une **question en langage naturel** depuis n'importe quel écran. | M |
| EX-ASS-02 | Les réponses sont **sourcées** (liens vers rapports, faits, objets) avec fiabilité et fraîcheur. | M |
| EX-ASS-03 | L'assistant **ne répond qu'avec ce que l'utilisateur est autorisé à voir** (RG-04). | M |
| EX-ASS-04 | Lorsque l'information manque, l'assistant **le dit** et indique qui interroger ; il n'invente jamais. | M |
| EX-ASS-05 | L'assistant **refuse** les demandes d'évaluation ou de classement de personnes et les atteintes à la confidentialité, avec explication (RG-01). | M |
| EX-ASS-06 | L'assistant propose des **actions** (ouvrir une fiche, créer une demande, demander une précision, produire un rapport). | S |
| EX-ASS-07 | Retour utilisateur sur chaque réponse (utile / inexacte / incomplète). | M |
| EX-ASS-08 | Suggestions de questions selon le rôle. | C |
| EX-ASS-09 | L'historique des questions de l'utilisateur est **privé** pour lui ; l'usage est journalisé pour l'audit selon la politique (RG-22). | M |
| EX-ASS-10 | Questions sur **données chiffrées** : l'assistant s'appuie sur les indicateurs calculés, pas sur des estimations libres. | M |

### QUA. Qualité des données (5)

| ID | Exigence | Prio |
|---|---|---|
| EX-QUA-01 | Un écran de **santé du référentiel** : couverture, fraîcheur, faits en attente, orphelins, doublons, contradictions. | M |
| EX-QUA-02 | **Files de travail** de curation (validation second niveau, fusions, rattachements ambigus). | M |
| EX-QUA-03 | **Relances** préparées, sobres, sans formulation accusatrice, vers les responsables en retard. | S |
| EX-QUA-04 | Suivi de la **qualité de l'IA** (taux de corrections et de rejets par type de rapport, retours utilisateurs). | M |
| EX-QUA-06 | Chaque indicateur montre sa **complétude** (part des objets couverts). | M |

### ADM. Administration (8)

| ID | Exigence | Prio |
|---|---|---|
| EX-ADM-01 | Gérer **organisation**, équipes, référentiels (profils, types de rapports, natures de faits), **sans développement**. | M |
| EX-ADM-02 | Gérer les **gabarits** de rapports et de restitutions. | M |
| EX-ADM-03 | Gérer **seuils, règles de santé, grille de priorisation, seuil d'agrégation, niveaux de classification, politique de conservation**. | M |
| EX-ADM-04 | **Aperçu d'impact** avant d'appliquer une modification de règle ; journal des modifications. | M |
| EX-ADM-05 | Gérer les **rôles, périmètres, délégations, expirations**. | M |
| EX-ADM-08 | **Import/export** des référentiels. | M |
| EX-ADM-09 | Gérer le **vocabulaire** (libellés) pour s'adapter à l'organisme. | S |
| EX-ADM-10 | L'administrateur fonctionnel **n'accède pas par défaut** aux contenus N3/N4. | M |

### AUD. Audit et traçabilité (5)

| ID | Exigence | Prio |
|---|---|---|
| EX-AUD-01 | **Journal** immuable des actions significatives (dépôt, validation, rejet, décision, modification de règle, accès N4, export, usage de l'IA). | M |
| EX-AUD-02 | Le journal est consultable par l'auditeur, le DPO (périmètre données personnelles/IA) et le RSSI (périmètre sécurité). | M |
| EX-AUD-04 | **Traçabilité de bout en bout** : de tout chiffre à ses faits, rapports, auteurs et validateurs. | M |
| EX-AUD-05 | **Registre d'usage de l'IA** : quelles analyses, quels modèles/versions, quels périmètres, quelles corrections humaines. | M |
| EX-AUD-07 | Politique de **conservation et d'effacement** appliquée et traçable (RG-20, RG-21). | M |

### TDB. Tableaux de bord (6)

| ID | Exigence | Prio |
|---|---|---|
| EX-TDB-01 | Une **vue stratégique** pour la direction (objectifs, portefeuille, dette, sécurité, ressources, finances, contraintes externes, contrats, décisions à prendre). | M |
| EX-TDB-02 | Chaque indicateur affiche **valeur, tendance, fiabilité, fraîcheur** et un lien « Pourquoi ? » vers ses faits et sources. | M |
| EX-TDB-03 | Les indicateurs dont les faits ne sont pas validés sont **distingués** (mention « déclaratif »). | M |
| EX-TDB-04 | Des **tableaux de bord par rôle** : responsable d'application, de projet, d'équipe, architecte, RSSI, finances, RH, PMO. | M |
| EX-TDB-08 | Le **catalogue d'indicateurs** (fichier 09 §3) est utilisé avec **définition accessible** pour chacun ; tout indicateur sans décision associée peut être retiré. | M |
| EX-TDB-09 | **Feux de santé** calculés par seuils objectifs (RG-08), jamais saisis librement ; toute dérogation est tracée. | M |

### RST. Restitutions (6)

| ID | Exigence | Prio |
|---|---|---|
| EX-RST-01 | Produire des **synthèses** d'un objet, d'un périmètre ou d'une période, avec sources. | M |
| EX-RST-02 | Produire un **résumé périodique** (hebdomadaire/mensuel) pour la direction, diffusable automatiquement. | S |
| EX-RST-05 | **Chaque chiffre est lié à ses faits sources** ; les passages produits par l'IA sont signalés. | M |
| EX-RST-07 | Le **niveau de classification** d'une restitution est hérité des sources ; l'export vers une audience non habilitée est bloqué ou masque les éléments non autorisés (RG-04). | M |
| EX-RST-08 | Avertissement si des faits **non validés** sont utilisés ; option de les exclure. | M |
| EX-RST-14 | Mention **« généré avec l'aide de l'IA »** sur les documents concernés (configurable pour usage interne, obligatoire pour diffusion externe). | M |

### ALI. Alimentations (1)

| ID | Exigence | Prio |
|---|---|---|
| EX-ALI-08 | **Import de fichiers** (tableur, texte structuré) comme alimentation générique pour toute donnée sans source automatique. | M |

## 5. Traçabilité parcours → écrans → tests

| Parcours | Écrans | Tests |
|---|---|---|
| P-01 | E-01, E-34 | T-ACU, T-ACC |
| P-02 | E-02, E-05 | T-DEP, T-SEC, T-DEG, T-SIG |
| P-03 | E-03, E-04 | T-GAB, T-IAX |
| P-04 | E-05 | T-SIG |
| P-05 | E-06 | T-REV, T-IAX, T-NOM, T-SEC |
| P-06 | E-07, E-30 | T-PRE, T-NOT |
| P-07 | E-08, E-29 | T-RAP |
| P-08 | E-09, E-33 | T-SAN, T-DRO, T-QUA |
| P-09 (légère) | E-04, E-10L | T-GAB, T-SAN, T-FIA |
| P-22 | E-24 | T-ASS, T-SEC, T-NOM |
| P-23 (réduite) | E-25 | T-FIA, T-DRO |
| P-25 | E-27, E-33 | T-QUA |
| P-26 (base) | E-28, E-32, E-31 | T-ADM, T-IMP, T-AUD |
| P-27 | E-34 | T-DRO |

Règles du dossier principal exercées par le lot : RG-01 à RG-08, RG-10, RG-11, RG-20 à RG-24, RG-29 à RG-34, RG-38 (partiel) ; IA-01 à IA-22.

## 6. Ordre de recette recommandé

1. **Socle** : droits et rôles, import du référentiel, administration de base (T-IMP, T-ADM, T-DRO).
2. **Contribution** : dépôt, gabarits, signalement, cycle de vie (T-DEP, T-GAB, T-SIG, T-RAP).
3. **Compréhension IA** : extraction sur le corpus de référence, revue, validation (T-IAX, T-REV).
4. **Qualité et contradictions** : précisions, qualité des données (T-PRE, T-QUA, T-NOT).
5. **Garde-fous** : non-évaluation des personnes, sécurité des contenus et de l'IA, mode dégradé (T-NOM, T-SEC, T-DEG).
6. **Restitution** : santé, indicateurs, vue stratégique, assistant (T-SAN, T-FIA, T-ASS).
7. **Traçabilité, accessibilité, utilisabilité** : T-AUD, T-ACC, T-ERG.

## 7. Calibrage de l'IA (avant la recette finale)

Le corpus du fichier 05 est un **point de départ**. Avant la recette finale :
1. Collecter **60 à 100 rapports réels anonymisés** de l'organisme pilote, représentatifs des types G-01, G-02, G-04, G-05, G-09, G-18, de rapports de sécurité et de tableurs.
2. Faire annoter les **faits attendus** par deux personnes (accord à mesurer).
3. Mesurer rappel et précision par nature de fait ; **ajuster les seuils PAR-01 à PAR-03**.
4. Décider avec le commanditaire de la **tolérance** (ex. 80 % de précision) avant ouverture à tous.
5. Mettre en place un **suivi continu** de L1-I11 (qualité de l'IA) avec alerte de dégradation (IA-20).

## 8. Définition de « terminé » pour le lot 1

- Toutes les exigences **M** du lot passent leurs tests **P1**.
- **100 %** des tests de **non-évaluation des personnes** (T-NOM) et de **confidentialité** (T-DRO, T-SEC) réussis, sans dérogation.
- Seuils de qualité IA du fichier 04 (§IAX) atteints sur le corpus de référence **et** sur le corpus réel anonymisé.
- Tests d'utilisabilité (T-ERG) : critères P1 atteints avec au moins 8 utilisateurs.
- Accessibilité (T-ACC) : parcours clés conformes au niveau choisi par l'organisme.
- Jeu de paramètres initiaux (fichier 02 §1) **validé** par le commanditaire avec un organisme pilote.
- Journal d'audit exploitable pour reconstituer SC-01 à SC-04.
- Mode dégradé sans IA démontré (SC-10).

## 9. Risques et hypothèses propres au lot

| Risque / hypothèse | Effet | Traitement |
|---|---|---|
| Qualité d'extraction insuffisante sur les rapports réels | Revue pénible, rejet par les utilisateurs | Calibrage (§7), confirmation en lot, mode dégradé, retour qualité |
| Goulot de validation (peu de curateurs) | Indicateurs vides | Validation par le responsable de l'objet ; relances sobres ; priorisation par criticité |
| Rapports trop hétérogènes (formats libres) | Faible rappel | Gabarits guidés ; rapports préremplis |
| Seuils de santé non adaptés | Fausses alertes | Paramétrage + aperçu d'impact ; calibrage avec l'organisme pilote |
| Perception de surveillance | Rejet | MSG-01/50, RG-01, E-34, T-ERG-07/08 ; information des agents |
| Contenus sensibles déposés par erreur | Exposition | Suggestion de niveau, N4 non modifiable à la baisse, cloisonnement |
| **Hypothèse** : l'identité des agents est disponible pour l'authentification | Sans elle, pas de droits | À confirmer avec l'organisme (H2) |
| **Hypothèse** : les rapports existent déjà en format bureautique courant | Sans cela, peu à déposer | H3 |

## 10. Questions ouvertes spécifiques au lot 1

| # | Question | Bloque | Proposition par défaut |
|---|---|---|---|
| L1-Q1 | Quel **organisme pilote** et quels **utilisateurs pilotes** (taille, direction) ? | Calibrage, recette | Direction du numérique (≈ 44 personnes), puis extension |
| L1-Q2 | Quelle **procédure d'alerte protégée** (lien à afficher) ? | MSG-03, MSG-40 | Lien configurable ; message générique sinon |
| L1-Q3 | **Taille maximale** de dépôt (PAR-13) et types de fichiers réellement utilisés ? | E-02 | 50 Mo ; types listés |
| L1-Q4 | Faut-il **activer la séparation des rôles** (l'auteur ne valide pas son propre fait) dès le lot 1 ? | E-06 | Oui par défaut, désactivable |
| L1-Q5 | **Qui reçoit** les signalements « discrets » (rôles destinataires) ? | E-05 | RSSI et référent du domaine |
| L1-Q6 | Quels **alias** d'applications et d'initiatives existent déjà dans le langage courant ? | Qualité du rattachement | À recueillir lors de l'import |
| L1-Q7 | Le **courriel** peut-il servir de canal de dépôt dès le lot 1 (Q-21) ? | E-02 | Non au lot 1 (dépôt dans l'application) |
| L1-Q8 | **Niveaux de classification** de l'organisme (libellés, habilitations) ? | RG-32, suggestions de niveau | Jeu N1–N4 par défaut |
| L1-Q9 | Les **seuils de santé** (§10–11 du fichier 02) conviennent-ils à l'organisme ? | Santé calculée | Calibrage avec l'organisme pilote |
