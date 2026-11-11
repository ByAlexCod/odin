# 04. Parcours utilisateurs

Chaque parcours décrit : **acteur(s)**, **déclencheur**, **pré-conditions**, **étapes** (avec l'écran concerné, voir fichier 07), **alternatives et erreurs**, **résultat**, **modules** (voir fichier 05) et **critères d'acceptation** (format *Étant donné / Quand / Alors*). Les rapports et faits suivent les cycles de vie du fichier 03.

Index : P-01 découverte · P-02 déposer un rapport · P-03 rédiger avec gabarit · P-04 signalement court · P-05 confirmer les faits · P-06 répondre à une précision · P-07 suivre mes rapports · P-08 responsable d'application · P-09 responsable de projet · P-10 exprimer une demande · P-11 qualifier les demandes · P-12 prioriser et arbitrer · P-13 roadmap · P-14 dette · P-15 ressources · P-16 budget · P-17 contrats · P-18 sécurité et risques · P-19 contraintes et échéances · P-20 comité et décision · P-21 produire rapport/présentation · P-22 assistant · P-23 vue stratégique · P-24 traçabilité et justification · P-25 qualité des données · P-26 administration · P-27 mobilité, départ, retrait.

---

## P-01. Première connexion et découverte

- **Acteur** : tout utilisateur (R01).
- **Déclencheur** : première authentification.
- **Pré-condition** : l'utilisateur est reconnu par l'organisme ; un rôle par défaut (R01) lui est affecté.
- **Étapes**
  1. *E-01 Accueil de bienvenue* : en 3 écrans courts, Odin explique (a) à quoi sert le dépôt de rapports, (b) ce que l'IA fait et ne fait pas, (c) **ce qu'Odin ne fait pas : il n'évalue pas les personnes**.
  2. L'utilisateur confirme son **équipe** (suggérée depuis l'organisation) et ses **applications / projets** de référence (suggestions, facultatif).
  3. Odin présente les **règles de confidentialité** (niveaux de classification définis par l'organisme) et ce qu'Odin fait ou non des contenus.
  4. Odin propose deux actions : *Déposer mon premier rapport* ou *Explorer*.
- **Alternatives** : l'utilisateur passe l'introduction (accessible ensuite dans l'aide) ; équipe inconnue → rattachement provisoire à son service.
- **Résultat** : profil de contribution initialisé ; consentement d'information tracé.
- **Modules** : ACC, NOT. 
- **Critères** : *Étant donné* un nouvel utilisateur, *quand* il se connecte, *alors* il atteint la page de dépôt en moins de 3 actions et voit la mention « Odin n'évalue pas les personnes ».

## P-02. Déposer un rapport existant (parcours cœur)

- **Acteur** : contributeur (R01 et tous rôles), prestataire (R02, périmètre restreint).
- **Déclencheur** : l'auteur a un document à partager (compte rendu, rapport d'avancement, post-mortem, audit, note…).
- **Pré-condition** : authentifié.
- **Étapes**
  1. *E-02 Dépôt* : l'utilisateur **glisse un document** (ou colle un texte, ou transfère un message) dans la zone de dépôt, disponible depuis n'importe quel écran (bouton permanent « Partager un rapport »).
  2. Odin affiche immédiatement : nom du fichier, **type de rapport proposé** (ex. rapport d'avancement), **rattachements proposés** (application, projet, équipe), **niveau de classification proposé**. Tout est modifiable.
  3. L'utilisateur peut **ajuster** (type, rattachement, période couverte, niveau de visibilité) ou valider tel quel : un bouton **« Partager »**.
  4. Odin confirme le dépôt (« Rapport partagé ») et lance l'analyse ; l'utilisateur peut quitter la page.
  5. L'analyse se termine (typiquement en quelques minutes) ; l'utilisateur est notifié « X faits à relire » (→ P-05).
- **Alternatives et erreurs**
  - Format non lisible ou protégé : message clair, proposition de coller le texte ou de convertir.
  - Détection de **données personnelles** ou de **contenu sensible** : l'utilisateur est averti avant publication ; niveau N4 proposé ; option de **masquer** les passages (IA-07, IA-08).
  - Détection de **consignes adressées à l'IA** dans le document : le document est traité comme du contenu, jamais comme instruction ; un avertissement est consigné (IA-12).
  - **Doublon** probable (même document ou version proche) : proposition de remplacer la version existante.
  - IA indisponible : le rapport est tout de même partagé et classé ; l'analyse est mise en attente ; le contributeur peut saisir des faits à la main (principe 10).
  - Document dépassant la taille limite : message avec solution (découper).
  - Contributeur externe : seuls ses périmètres ouverts sont proposés en rattachement.
- **Résultat** : un rapport au statut *Déposé → Analysé*, des faits proposés (F0), visible selon son niveau.
- **Modules** : RAP, IAF, ACC, NOT.
- **Critères**
  - *Étant donné* un rapport d'avancement au format bureautique, *quand* l'utilisateur le glisse et clique « Partager » sans autre saisie, *alors* le rapport est enregistré avec des valeurs proposées, et l'utilisateur est invité à relire les faits.
  - *Étant donné* un rapport contenant des noms de personnes dans un contexte de jugement, *quand* l'analyse s'exécute, *alors* aucun fait évaluatif nominatif n'est créé et l'auteur est invité à pseudonymiser (RG-01, IA-08).

## P-03. Rédiger un rapport avec un gabarit guidé

- **Acteur** : tout contributeur ; surtout chefs de projet, responsables d'application.
- **Déclencheur** : l'auteur n'a pas de document ou souhaite un format normalisé.
- **Étapes**
  1. *E-03 Choisir un gabarit* parmi ceux proposés pour son rôle (rapport d'avancement, retour d'expérience, compte rendu de comité, fiche de dette, fiche de risque, besoin métier, etc., voir fichier 09).
  2. *E-04 Éditeur guidé* : sections courtes avec **aide à la rédaction** (exemples, rappel de la période, valeurs précédentes). Les champs structurés (avancement, jalons, budget consommé, difficultés, besoins) sont **préremplis** depuis le dernier rapport et les faits validés.
  3. L'utilisateur peut **dicter ou écrire librement** ; l'IA reformule sur demande (« rendre plus concis »), toujours sous contrôle de l'auteur.
  4. Enregistrement automatique en **brouillon** ; reprise possible plus tard.
  5. *Partager* : même chaîne que P-02 (analyse, relecture des faits).
- **Alternatives** : abandon → brouillon conservé 30 jours ; conflit de modification (co-rédaction) → affichage des différences ; gabarit non adapté → proposition « document libre ».
- **Résultat** : rapport structuré dont une partie des faits est **déclarée directement** (F1) ; moins d'extraction nécessaire.
- **Modules** : RAP, IAF.
- **Critères** : *Étant donné* un rapport d'avancement du mois précédent, *quand* l'auteur ouvre le gabarit du mois courant, *alors* les rubriques sont préremplies avec les derniers faits validés et un résumé des différences à confirmer.

## P-04. Signaler rapidement un risque, un problème ou une idée

- **Acteur** : tout utilisateur.
- **Déclencheur** : constat à partager sans rédiger un rapport (« ce serveur arrive en fin de support », « ce projet dérive », « idée d'amélioration »).
- **Étapes**
  1. *E-05 Signalement court* : une zone de texte, 1 choix de nature (risque / problème / dette / idée / besoin), l'objet concerné (suggéré), le niveau de visibilité (par défaut périmètre).
  2. Option : **signalement discret** vers le responsable de sécurité ou le référent du domaine (niveau N3/N4), sans exposer l'auteur aux autres (RG-23).
  3. Envoi ; l'utilisateur voit « Votre signalement a été transmis à [rôle] ; vous serez informé de la suite ».
  4. Le signalement est analysé comme un mini-rapport ; il peut déclencher un **signal** (OBJ-52) ou être converti en risque, dette ou demande.
- **Alternatives** : signalement relevant d'une **alerte protégée** (faits graves, mise en cause de personnes, infractions) : Odin affiche un message dirigeant vers la procédure légale de l'organisme (RG-24) sans analyser le contenu.
- **Résultat** : information captée en moins de 30 secondes.
- **Modules** : RAP, IAF, SEC, DET, POR.
- **Critères** : *Étant donné* un utilisateur, *quand* il envoie un signalement, *alors* il reçoit un accusé immédiat et une notification lorsque le signalement est traité (converti, clos avec motif).

## P-05. Relire et confirmer les faits extraits (auteur)

- **Acteur** : auteur du rapport.
- **Déclencheur** : notification « N faits à relire ».
- **Étapes**
  1. *E-06 Revue des faits* : écran en deux volets : le **document** à gauche (passage en surbrillance) et la liste des **faits proposés** à droite, groupés par nature (avancement, jalons, risques, ressources, budget, dette, sécurité…).
  2. Pour chaque fait : **Confirmer** (un clic), **Corriger** (modifier la valeur ou le rattachement), **Rejeter**, ou **Demander à quelqu'un** (renvoie à un responsable).
  3. Actions groupées : « Tout confirmer pour cette nature », « Confirmer les faits à haute confiance » ; les faits à faible confiance et les **contradictions** sont mis en avant en premier.
  4. L'auteur voit l'**effet** de ses confirmations (« Ce fait met à jour la santé de l'application X »).
  5. Fin de revue : le rapport passe à *Publié* ; les faits confirmés deviennent F1.
- **Alternatives** : rapport non relu après X jours → rappels, puis publication **sans** faits (le rapport reste consultable mais n'alimente aucun indicateur) ; l'auteur absent → délégation au responsable de l'objet.
- **Résultat** : faits en F1, prêts pour validation F2 par le responsable.
- **Modules** : IAF, RAP.
- **Critères**
  - *Étant donné* 20 faits proposés dont 15 à haute confiance, *quand* l'auteur utilise « Confirmer les faits à haute confiance », *alors* 15 faits passent en F1 et 5 restent à examiner.
  - *Étant donné* un fait rejeté, *quand* l'auteur le rejette, *alors* il ne sera pas reproposé identique pour ce rapport, et l'avis est consigné comme retour de qualité (IA-14).

## P-06. Répondre à une demande de précision

- **Acteur** : auteur ou responsable d'objet.
- **Déclencheur** : un signal (contradiction, donnée manquante) génère une **demande de précision**.
- **Étapes**
  1. Notification contenant la question en une phrase, le contexte (les deux faits en conflit ou la donnée manquante) et le délai souhaité.
  2. *E-07 Réponse* : choix prédéfinis (« le premier est correct », « le second est correct », « les deux, voir précision », « je ne sais pas, voir [rôle] ») + zone libre.
  3. La réponse met à jour les faits (F1/F2) et ferme le signal.
- **Alternatives** : non-réponse → relance puis **escalade** au responsable (tracée, sans blâme) ; question mal posée → l'utilisateur la signale (retour qualité).
- **Résultat** : écart résolu, traçabilité de la clarification.
- **Modules** : NOT, IAF.
- **Critères** : *Étant donné* deux rapports annonçant des dates différentes, *quand* l'utilisateur répond, *alors* un seul jalon est retenu et le fait rejeté est marqué avec le motif.

## P-07. Suivre mes rapports et voir ce qu'Odin en a fait

- **Acteur** : tout contributeur.
- **Déclencheur** : l'utilisateur veut savoir ce qu'est devenu son rapport.
- **Étapes**
  1. *E-08 Mes rapports* : liste avec statut (déposé, analysé, à relire, publié, périmé), date, nombre de faits confirmés.
  2. Ouverture d'un rapport : **« Ce que cette contribution a changé »** (faits utilisés, indicateurs concernés, décisions qui l'ont cité), sans exposer d'informations hors de son périmètre.
  3. Actions : remplacer par une nouvelle version, retirer, changer la visibilité (dans les limites de ses droits), exporter.
- **Alternatives** : rapport cité dans une décision N3/N4 → mention « cité dans une décision restreinte » sans détail.
- **Résultat** : boucle de retour qui motive la contribution (principe 6).
- **Modules** : RAP, IAF.
- **Critères** : *Étant donné* un rapport publié, *quand* l'auteur ouvre « Ce que cette contribution a changé », *alors* il voit les objets mis à jour, et pas les contenus au-delà de ses droits.

## P-08. Responsable d'application : maintenir la fiche et valider

- **Acteur** : R03.
- **Déclencheur** : notification de faits à valider ; revue périodique ; signal sur son application.
- **Étapes**
  1. *E-09 Fiche application* (onglets : Synthèse, Faits à valider, Rapports, Dette, Risques et sécurité, Technologies et fin de support, Contrats, Coûts, Équipe, Historique).
  2. **Valider** (F2), **corriger** ou **rejeter** les faits proposés ; les faits de plusieurs auteurs sont présentés ensemble avec leurs sources.
  3. Compléter les informations absentes que la fiche signale (criticité, services rendus servis, responsable, équipe).
  4. Consulter la **santé calculée** et sa justification (RG-08) ; contester un calcul (commentaire tracé).
  5. Déclencher une action : créer un élément de dette, une demande, un risque, un rapport de situation.
- **Alternatives** : fiche **périmée** (aucune contribution depuis X jours) → rappel et suggestion de demander un rapport aux contributeurs ; application orpheline → proposition de désignation.
- **Résultat** : fiche à jour, faits F2.
- **Modules** : REF, IAF, DET, SEC, FIN.
- **Critères** : *Étant donné* une fiche avec 8 faits en attente, *quand* le responsable les valide, *alors* la fraîcheur affichée de la fiche se met à jour et la santé est recalculée.

## P-09. Responsable de projet : rapport d'avancement et santé de l'initiative

- **Acteur** : R04.
- **Déclencheur** : échéance mensuelle (rappel) ; événement notable.
- **Étapes**
  1. Rappel (avec le gabarit préparé, P-03). Le chef de projet dépose son rapport (document ou gabarit).
  2. Revue des faits (P-05) : avancement, jalons, consommation budgétaire, ETP, risques, dépendances, décisions attendues.
  3. *E-10 Fiche initiative* : visualisation de la **santé calculée** vs la **santé déclarée** ; en cas d'écart, Odin demande une précision (P-06) **avant** diffusion.
  4. Mise à jour des **bénéfices attendus** et des **décisions à demander** au comité.
  5. Le rapport officiel est **soumis à validation** du commanditaire (si exigé par le gabarit) puis marqué « officiel ».
- **Alternatives** : rapport en retard → rappel puis alerte au PMO ; changement de périmètre → proposition de créer une décision de réplanification.
- **Résultat** : initiative à jour ; une seule saisie alimente avancement, budget, ressources, risques.
- **Modules** : POR, ROA, FIN, RSR, IAF.
- **Critères** : *Étant donné* une santé déclarée « verte » avec un jalon dépassé de 30 jours, *quand* le rapport est analysé, *alors* Odin affiche l'écart et réclame une confirmation avant de publier la santé.

## P-10. Exprimer une demande ou un besoin

- **Acteur** : tout agent, direction métier.
- **Déclencheur** : besoin nouveau ou évolution d'un service rendu.
- **Étapes**
  1. *E-11 Nouvelle demande* : énoncé du besoin en langage libre, **service rendu concerné**, urgence ressentie, échéance contrainte (texte, calendrier), valeur attendue (qualitative, usagers concernés).
  2. L'IA propose : demandes **similaires ou existantes** (éviter les doublons), initiatives en cours qui y répondent, applications déjà disponibles qui couvrent le besoin (réutilisation, solutions mutualisées ou réutilisables connues de l'organisme).
  3. Envoi ; accusé avec numéro et circuit prévu.
  4. Suivi dans « Mes demandes » (statut, décisions, motifs).
- **Alternatives** : demande déjà couverte → redirection ; demande incomplète → précision demandée.
- **Résultat** : demande entrée dans l'entonnoir (P-11).
- **Modules** : POR, IAF.
- **Critères** : *Étant donné* une demande proche d'une demande existante, *quand* l'utilisateur la soumet, *alors* il voit les similaires et choisit de rattacher ou de créer.

## P-11. Qualifier les demandes (bureau de portefeuille)

- **Acteur** : R12 (PMO) ; consultés : R06, R07, R09.
- **Déclencheur** : file de demandes ; revue périodique.
- **Étapes**
  1. *E-12 File de qualification* : demandes triées (urgence, échéances contraintes), avec regroupements suggérés (doublons, thèmes).
  2. Pour chaque demande : compléter (valeur, effort estimé, services rendus, dépendances, **contrainte externe liée**, risque couvert), demander avis (architecture, sécurité, finances).
  3. Décision de qualification : **instruire**, **fusionner**, **différer** (avec motif), **refuser** (avec motif), **orienter** vers un dispositif existant.
  4. Les demandes instruites deviennent des **candidats** au portefeuille.
- **Alternatives** : demande sensible → circuit restreint ; échéance légale → marquage « non arbitrable » (RG-13).
- **Résultat** : portefeuille de candidats prêts à arbitrer ; motifs tracés et visibles du demandeur.
- **Modules** : POR, REG.
- **Critères** : *Étant donné* une demande refusée, *quand* le PMO clôt, *alors* le demandeur est notifié avec le motif.

## P-12. Prioriser le portefeuille et préparer l'arbitrage

- **Acteur** : R12, R13 ; contributeurs R06, R07, R09, R10.
- **Déclencheur** : cycle budgétaire ; comité d'investissement ; événement.
- **Étapes**
  1. *E-13 Portefeuille* : vue d'ensemble des initiatives (en cours, candidates) avec valeur, coût, ETP, risque couvert, dette traitée, dépendances, échéances contraintes.
  2. Paramétrer la **grille de critères** (valeur de service, risque couvert, contrainte externe, dette traitée, coût, effort, urgence, souveraineté…) avec **pondérations** ; scores calculés **et explicables**.
  3. Poser des **contraintes** : budget (nomenclature de l'organisme), capacité en ETP par profil, plafond d'effectifs éventuel, échéances non arbitrables.
  4. *E-14 Scénarios* : créer des scénarios (« avec/sans projet X », « budget −10 % », « 3 ETP de moins sur le profil Y ») ; Odin calcule **ce qui tient, ce qui est dépassé, ce qui est retardé**, et le **coût du report**.
  5. Comparer les scénarios côte à côte ; Odin met en évidence les **conséquences non évidentes** (dépendances, dette qui s'aggrave, échéance externe manquée, profil en tension).
  6. Constituer la **proposition d'arbitrage** → note de décision (P-20).
- **Alternatives** : données insuffisantes → liste des faits manquants avec responsable ; échéance non arbitrable en conflit avec la capacité → alerte rouge.
- **Résultat** : arbitrage préparé, traçable, avec hypothèses explicites.
- **Modules** : POR, ROA, RSR, FIN, DET, REG, DEC.
- **Critères**
  - *Étant donné* un scénario réduisant la capacité d'un profil, *quand* il est calculé, *alors* la liste des initiatives retardées est affichée avec la durée du retard et les effets en chaîne.
  - *Étant donné* des pondérations modifiées, *quand* l'utilisateur compare, *alors* il voit comment le classement change (analyse de sensibilité).

## P-13. Construire et faire évoluer la roadmap

- **Acteur** : R12 (principal), R06, R04, R13.
- **Déclencheur** : cycle annuel ; décision d'arbitrage ; changement majeur.
- **Étapes**
  1. *E-15 Roadmap* : vue par **horizons** (maintenant, prochainement, plus tard) et par **thèmes/objectifs** ; options : par service rendu, par application, par équipe, par contrainte externe.
  2. Positionner/déplacer des initiatives et jalons ; Odin vérifie en continu la **cohérence** (dépendances, capacité, budget, fin de support technologique, échéances légales).
  3. Voir les **conflits** (capacité insuffisante, dépendance non satisfaite, échéance dépassée) avec une explication en une phrase.
  4. **Versionner** : publier une version (avec motif et décision associée), comparer à la version précédente.
  5. Créer des **vues de diffusion** (roadmap pour les élus/tutelles : sans détails sensibles).
- **Alternatives** : changement non cohérent → blocage ou avertissement selon le paramétrage ; roadmap partagée à l'extérieur → vérification de classification.
- **Résultat** : roadmap validée et versionnée, reliée aux décisions.
- **Modules** : ROA, POR, DET, RSR, REG.
- **Critères** : *Étant donné* une initiative déplacée après la fin de support d'une technologie qu'elle traite, *quand* l'utilisateur confirme, *alors* un avertissement indique la période d'exposition et le risque associé.

## P-14. Gérer la dette

- **Acteur** : R03, R06, R05 (recensent) ; R12, R13 (priorisent).
- **Déclencheur** : signalement (P-04), faits extraits, fin de support proche, audit.
- **Étapes**
  1. *E-16 Registre de dette* : éléments classés par type, application, intérêt estimé, effort de remboursement, échéance critique.
  2. **Qualifier** un élément (type, intérêt en coût ou en risque par an, effort, lien avec sécurité/continuité).
  3. **Prioriser** : ordre proposé (rapport intérêt / effort, urgence, criticité du service rendu) ; contrôler la **part de capacité** consacrée à la dette (objectif paramétrable).
  4. **Planifier** : rattacher l'élément à une initiative ou en créer une ; ou **accepter** la dette (motif, date de revue).
  5. Suivre l'**évolution** : dette totale estimée, tendance, éléments dépassant leur échéance.
- **Alternatives** : intérêt non estimable → estimation par fourchette, signalée comme telle (fiabilité faible) ; dette liée à un risque sécurité → lien automatique.
- **Résultat** : dette visible, chiffrée avec prudence, reliée aux arbitrages.
- **Modules** : DET, SEC, POR, ROA.
- **Critères** : *Étant donné* un élément de dette accepté, *quand* sa date de revue arrive, *alors* une demande de réévaluation est envoyée au responsable.

## P-15. Piloter capacité et ressources (équipes et profils)

- **Acteur** : R05, R10, R12, R13.
- **Déclencheur** : cycle de planification ; vacances de poste ; arbitrage.
- **Étapes**
  1. *E-17 Capacité* : vue **par équipe et par profil** : capacité disponible (internes, prestataires) vs demande (initiatives engagées + run + dette + contraintes externes), avec **taux de charge** agrégé.
  2. Ajuster les **hypothèses** (congés, part de run, productivité) ; elles sont visibles et datées.
  3. Identifier **tensions** (profils ou compétences rares), **dépendance aux prestataires**, **vacances de postes** et durée.
  4. Simuler (P-12 scénarios) : recrutement, renfort prestataire, redéploiement entre équipes.
  5. Si l'organisme suit un **plafond d'effectifs** (en ETPT ou autre unité) : consommation vs plafond.
- **Alternatives** : équipe sous le seuil d'agrégation → métriques masquées ou remontées au niveau supérieur (RG-02) ; demande d'une **vue nominative** → refusée avec explication (RG-01).
- **Résultat** : décisions de recrutement, de redéploiement et d'arbitrage fondées sur la capacité réelle par profil.
- **Modules** : RSR, POR, ROA.
- **Critères** : *Étant donné* une équipe de 3 personnes, *quand* un responsable ouvre la vue capacité, *alors* les indicateurs de charge ne sont pas affichés à son niveau (seuil d'agrégation) mais remontés au niveau supérieur.

## P-16. Piloter le budget et les coûts

- **Acteur** : R09, R13, R12, R03/R04 (lecture).
- **Déclencheur** : préparation budgétaire ; suivi mensuel ; arbitrage.
- **Étapes**
  1. *E-18 Finances* : budget selon la **nomenclature de l'organisme** (niveaux paramétrables), consommé, disponible ; distinction **run / build**.
  2. **Imputer** les dépenses aux applications, initiatives et services rendus (règles d'allocation visibles, déclarées par le contrôle de gestion).
  3. Voir le **coût complet** d'une application (licences, prestataires, hébergement, ETP valorisés **au niveau agrégé**).
  4. **Consolider** la dépense numérique de l'organisme (vue demandée par les corps de contrôle) ; exporter.
  5. Comparer prévisions de rapports (budget consommé déclaré) et données financières (fiabilité F3).
- **Alternatives** : dépense sans imputation → file d'imputation ; écart entre budget déclaré dans un rapport et comptabilité → signal.
- **Résultat** : coûts compréhensibles par la direction, consolidation reproductible.
- **Modules** : FIN, FOU, TDB.
- **Critères** : *Étant donné* des dépenses non imputées, *quand* le contrôleur de gestion ouvre l'écran, *alors* il voit le montant et le pourcentage non imputés et peut imputer en lot.

## P-17. Gérer contrats et fournisseurs

- **Acteur** : R11, R13, R03/R04 (lecture).
- **Déclencheur** : échéance proche ; arbitrage de sortie ; risque fournisseur.
- **Étapes**
  1. *E-19 Contrats* : calendrier des **échéances** (fin, **préavis**, reconduction), montants, applications couvertes.
  2. Alertes à J-180 / J-90 / J-30 (paramétrables) avec la **liste des décisions à prendre** (renouveler, remettre en concurrence, sortir).
  3. Analyse de **dépendance** : part d'un fournisseur dans la dépense et dans les services critiques ; scénario de sortie (applications touchées, effort, délai).
  4. Rapprochement avec **licences** consommées vs acquises.
- **Alternatives** : contrat sans responsable → alerte ; préavis manqué → signal critique avec options restantes.
- **Résultat** : aucune échéance subie ; arbitrages anticipés.
- **Modules** : FOU, FIN, DEC.
- **Critères** : *Étant donné* un contrat dont le préavis expire dans 90 jours, *quand* la date approche, *alors* le responsable et le PMO sont alertés avec une proposition de décision préparée.

## P-18. Piloter sécurité et risques

- **Acteur** : R07 (principal), R13, R03/R04, R06.
- **Déclencheur** : audit, constat, rapport de sécurité déposé, échéance d'évaluation de sécurité, revue périodique.
- **Étapes**
  1. *E-20 Sécurité et risques* : **posture** (maturité par domaine), registre des risques, constats d'audit et de tests, évaluations de sécurité (validité), exceptions, plans d'action.
  2. Les **rapports de sécurité déposés** (N4) alimentent des faits que le RSSI **valide** ; les rattachements aux applications se font automatiquement sous sa supervision.
  3. Arbitrer : traiter, transférer, accepter un risque (**acceptation formelle** par l'autorité compétente, tracée, datée).
  4. Lier risques et **dette / obsolescence** : applications en fin de support exposées ; lier aux initiatives.
  5. Produire la **vue de direction** (synthèse sans détail technique sensible).
- **Alternatives** : contenu technique sensible → affichage restreint ; évaluation expirée → signal critique ; exception arrivant à échéance → relance.
- **Résultat** : risques décidés et tracés ; sécurité intégrée aux arbitrages.
- **Modules** : SEC, DET, DEC, TDB.
- **Critères** : *Étant donné* une évaluation de sécurité expirant dans 60 jours, *quand* le seuil est atteint, *alors* le RSSI et le responsable d'application sont alertés et la direction voit la mention agrégée.

## P-19. Suivre les contraintes et échéances externes

- **Acteur** : R13, R12, R07, R08 ; tout rôle responsable d'un objet concerné.
- **Déclencheur** : l'organisme identifie une obligation, un engagement ou une échéance qui s'impose à lui (réglementaire, tutelle, contractuelle, interne).
- **Étapes**
  1. *E-21 Contraintes et échéances* : saisir une contrainte (libellé, **source en texte libre**, nature, échéance, responsable). L'organisme en reste seul maître ; Odin ne fournit pas de liste de textes.
  2. Indiquer son **applicabilité** (applicable, à confirmer, non applicable avec motif) et son **état** (à venir, en écart, satisfaite).
  3. **Rattacher** la contrainte aux applications, initiatives et équipes concernées.
  4. Voir le **calendrier consolidé** et la couche d'échéances sur la roadmap ; marquer « non arbitrable » une échéance ferme.
  5. Recevoir des **alertes** à l'approche des échéances ; un rapport déposé qui mentionne une contrainte lui est rattaché (proposition à confirmer).
- **Alternatives** : contrainte sans responsable → signal ; non mise à jour depuis longtemps → badge « à revoir » ; import d'une liste existante de l'organisme.
- **Résultat** : les échéances externes pèsent dans les arbitrages sans qu'Odin porte de procédure officielle.
- **Modules** : REG, ROA, POR.
- **Critères** : *Étant donné* une contrainte « non arbitrable » avec échéance, *quand* un scénario retarde l'initiative liée au-delà de l'échéance, *alors* le scénario affiche un conflit explicite.

## P-20. Préparer un comité et formaliser une décision

- **Acteur** : R12/R13 ; participants : tous rôles concernés.
- **Déclencheur** : calendrier d'une instance (comité d'investissement, comité d'architecture, comité sécurité, comité stratégique).
- **Étapes**
  1. *E-22 Comité* : l'ordre du jour proposé (sujets en attente, signaux, échéances) ; ajout/retrait de points.
  2. Pour chaque point, Odin génère une **note de décision** : décision demandée, contexte, options (dont « ne rien faire » avec coût du retard), impacts (coût, risque, service rendu, ETP, calendrier), recommandation, **sources** cliquables (P-21).
  3. Les participants lisent, **commentent** et préparent leurs avis ; l'IA peut synthétiser les commentaires.
  4. Séance : le secrétaire saisit/valide la **décision** (choix, motifs, hypothèses, responsables, échéances, bénéfices attendus) ; le **compte rendu** est généré en brouillon puis validé.
  5. Les suites sont créées automatiquement (jalons, actions, mises à jour de roadmap) ; une **date de bilan** est posée.
  6. À la date de bilan, rappel : les bénéfices attendus sont comparés aux constats.
- **Alternatives** : décision ajournée → point reporté avec motif ; décision contraire à la recommandation → motif obligatoire ; décision sensible → registre restreint.
- **Résultat** : décision tracée, traçable, suivie, auditable.
- **Modules** : DEC, RST, POR, ROA.
- **Critères** : *Étant donné* une décision enregistrée, *quand* son bilan est dû, *alors* le décideur reçoit une demande de bilan avec les faits à comparer ; *Étant donné* un auditeur, *quand* il ouvre la décision, *alors* il voit les options, critères, hypothèses et sources telles qu'elles étaient au jour de la décision.

## P-21. Produire un rapport de direction ou une présentation

- **Acteur** : tout rôle ayant un périmètre ; surtout R13, R12, R04, R07, R09.
- **Déclencheur** : besoin d'un document pour une audience (comité, direction générale, tutelle, élus, équipe).
- **Étapes**
  1. *E-23 Atelier de restitution* : choisir le **type** (rapport d'activité, revue de portefeuille, bilan trimestriel, note de décision, point sécurité, dossier d'arbitrage budgétaire, présentation de roadmap…), l'**audience**, la **période**, le **périmètre**.
  2. Odin **compose** un brouillon : structure, texte de synthèse, graphiques, tableaux ; **chaque chiffre est lié à ses faits sources** ; les passages produits par l'IA sont signalés.
  3. L'utilisateur **édite**, ajuste le ton (technique ↔ exécutif), supprime/ajoute des parties ; l'IA reformule sur demande.
  4. Vérifications automatiques : **niveau de classification** hérité (RG-04), **fiabilité des chiffres** (alerte si des faits F0/F1 sont utilisés), **fraîcheur**, informations nominatives détectées.
  5. **Valider / faire valider** (workflow si requis) puis **exporter** (formats bureautiques courants et ouverts, charte graphique de l'organisme) ou **partager** dans Odin.
  6. Versionner ; conserver la **photo des données** au moment de la production (reproductibilité).
- **Alternatives** : données insuffisantes → liste de lacunes proposées en commentaire ; destinataire externe → avertissement et retrait des éléments N3/N4.
- **Résultat** : document complet en minutes, traçable, conforme au niveau de confidentialité.
- **Modules** : RST, IAF, TDB.
- **Critères**
  - *Étant donné* une présentation générée, *quand* l'utilisateur clique sur un chiffre, *alors* il voit sa source (faits, rapports, date, fiabilité).
  - *Étant donné* des sources de niveaux différents, *quand* la présentation est produite, *alors* son niveau est le plus élevé des sources et un avertissement bloque l'export vers une audience non habilitée.

## P-22. Interroger Odin (assistant)

- **Acteur** : tout utilisateur.
- **Déclencheur** : question en langage naturel (« Quelles applications critiques sont en fin de support cette année ? », « Où en est le projet X ? », « Quels rapports parlent de cette dépendance ? »).
- **Étapes**
  1. *E-24 Assistant* : champ de question toujours accessible ; suggestions de questions selon le rôle.
  2. Réponse **structurée** : réponse courte, détails, **liens vers les sources** (rapports, faits, objets), **fiabilité et fraîcheur** de l'information.
  3. Actions suggérées (ouvrir la fiche, créer une demande, demander une précision, produire un rapport).
  4. **Retour** : l'utilisateur note la réponse (utile / inexacte / incomplète) ; une réponse inexacte peut être signalée avec correction.
- **Alternatives** : information insuffisante → l'assistant le dit et propose qui interroger (jamais d'invention) ; demande sur des personnes (« Qui est le moins performant ? ») → **refus** avec explication (RG-01) ; question sur un contenu hors droits → « information non accessible avec vos droits » sans révéler son existence détaillée (RG-04).
- **Résultat** : réponses sourcées dans les limites des droits.
- **Modules** : ASS, IAF.
- **Critères** : *Étant donné* une question sur un sujet N4 sans droit, *quand* l'assistant répond, *alors* il n'expose ni contenu ni détail ; *Étant donné* une réponse, *quand* l'utilisateur ouvre les sources, *alors* chaque affirmation est reliée à au moins une source.

## P-23. Vue stratégique de la direction

- **Acteur** : R13, R14 (lecture).
- **Déclencheur** : consultation périodique ; alerte ; préparation d'un échange avec la tutelle.
- **Étapes**
  1. *E-25 Vue stratégique* : **cascade des objectifs** (avancement, santé), **portefeuille** (santé, dépassements), **dette** (tendance), **sécurité** (posture, risques majeurs), **ressources** (tensions de profils), **finances** (consommation, run/build), **conformité** (échéances), **contrats** (échéances), **décisions à prendre**.
  2. Chaque tuile affiche : valeur, tendance, **fiabilité**, **fraîcheur**, et un lien « Pourquoi ? ».
  3. **Explorer** : descendre d'un indicateur vers ses objets, faits et rapports sources (dans les droits).
  4. **Alertes** : liste des signaux notables ; actions : demander une précision, inscrire à un comité, produire une note.
  5. **Résumé de la semaine** généré (P-21), à diffusion automatique paramétrable.
- **Alternatives** : indicateur fondé sur des faits non validés → affiché en gris avec mention « déclaratif » ; absence de données → proposition de demander un rapport.
- **Résultat** : vision décisionnelle fiable en moins de 5 minutes.
- **Modules** : TDB, OBJ, RST.
- **Critères** : *Étant donné* un indicateur dégradé, *quand* le décideur clique « Pourquoi ? », *alors* Odin affiche les 3 faits contributeurs principaux et leurs sources.

## P-24. Traçabilité et justification d'une décision

- **Acteur** : R15 (auditeur / contrôle interne) ; R13, R12 (répondent).
- **Déclencheur** : besoin de justifier une décision ou de répondre à une demande d'explication (interne ou externe).
- **Étapes**
  1. *E-26 Traçabilité* : ouvrir le **dossier de preuve** d'une décision (options, critères, hypothèses, faits au jour J, versions, auteurs et validateurs).
  2. Consulter le **journal** (qui a déposé, validé, décidé, consulté un contenu sensible, utilisé l'IA).
  3. Produire des **états consolidés** exportables (dont la consolidation de la dépense numérique), reproductibles.
- **Alternatives** : preuve manquante → signal ; accès sensible → demande d'habilitation tracée.
- **Résultat** : toute décision et tout chiffre sont justifiables sans reconstitution manuelle.
- **Modules** : AUD, DEC, FIN.
- **Critères** : *Étant donné* une décision ancienne, *quand* l'auditeur ouvre son dossier, *alors* il voit les options, hypothèses et faits tels qu'ils étaient le jour de la décision.

## P-25. Qualité des données et curation

- **Acteur** : R16, R06, R17, R12.
- **Déclencheur** : tableau de fraîcheur ; signaux ; revue périodique.
- **Étapes**
  1. *E-27 Santé du référentiel* : couverture (applications avec fiche complète, avec rapport récent), fraîcheur, faits non validés en attente, rattachements ambigus, objets orphelins, doublons, contradictions.
  2. Traiter les files : **valider/rejeter** des faits en second niveau, **fusionner** des doublons, **résoudre** des rattachements ambigus.
  3. **Relancer** les responsables en retard (messages préparés, sobres, non accusateurs).
  4. Suivre la **qualité de l'IA** (taux de faits corrigés/rejetés par type de rapport, retours) et remonter les cas d'échec à l'administrateur.
- **Alternatives** : objet critique sans donnée depuis longtemps → alerte à la direction (couverture insuffisante, pas faute individuelle).
- **Résultat** : confiance maintenue dans les indicateurs.
- **Modules** : QUA, IAF, NOT.
- **Critères** : *Étant donné* des applications critiques sans rapport depuis 90 jours, *quand* le curateur ouvre l'écran, *alors* elles sont listées avec le responsable et un bouton « demander un rapport ».

## P-26. Administration et paramétrage

- **Acteur** : R17 (administrateur fonctionnel).
- **Déclencheur** : mise en service ; évolution des règles ; départ de personnes.
- **Étapes**
  1. *E-28 Administration* : **organisation** (directions, équipes), **référentiels** (profils, compétences, types de rapports, nature de faits), **gabarits**, **seuils et règles de santé**, **calendrier des instances**, **contraintes externes**, **niveaux de classification**, **grille de priorisation**, **seuil d'effectif d'agrégation**, **politique de conservation**.
  2. Gestion des **rôles et périmètres** : affectation, délégations, expirations (prestataires).
  3. **Aperçu d'impact** avant toute modification de règle (quels indicateurs changeront) ; journal des modifications.
  4. Paramétrer les **sources d'alimentation** et leur fréquence (fonctionnel).
- **Alternatives** : modification de règle de santé → proposition d'application à partir d'une date (pas rétroactive par défaut) ; conflit de droits → alerte.
- **Résultat** : outil adapté à l'organisme sans développement.
- **Modules** : ADM, ACC.
- **Critères** : *Étant donné* une modification de seuil de santé, *quand* l'administrateur la valide, *alors* il voit la liste des objets dont la santé changerait avant d'appliquer.

## P-27. Mobilité, départ, retrait et droits des agents

- **Acteur** : R17, responsables ; tout agent pour ses droits.
- **Déclencheur** : mobilité ou départ d'un agent ; demande de retrait ou d'accès.
- **Étapes**
  1. À la mobilité/au départ, Odin liste les **objets sous la responsabilité** de la personne (applications, projets, validations) et demande une **réattribution** avant suspension.
  2. Les contributions du départ restent attachées aux objets (pas à la personne dans les vues de pilotage) ; l'auteur reste nommé dans l'historique d'audit (selon la politique de conservation).
  3. **Droit de retrait / rectification** : un agent peut demander de retirer ou corriger un rapport ou un fait le concernant ; la demande suit un circuit (responsable, DPO) avec réponse dans un délai défini.
  4. **Transparence** : un agent peut consulter *où ses contributions sont utilisées* et ce que l'IA en a fait.
- **Alternatives** : objet non réattribué → alerte au responsable hiérarchique et au PMO ; demande de suppression en conflit avec une obligation de conservation → motif exposé.
- **Résultat** : continuité de la connaissance, droits respectés.
- **Modules** : ACC, ADM, RAP.
- **Critères** : *Étant donné* un départ, *quand* l'administrateur déclenche la suspension, *alors* aucun objet n'est laissé sans responsable sans alerte explicite.
