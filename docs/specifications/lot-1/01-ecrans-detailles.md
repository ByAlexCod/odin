# Lot 1. Écrans détaillés

Pour chaque écran : **acteurs et accès**, **objectif**, **point d'entrée**, **contenu** (zones, champs, valeurs par défaut, validations), **actions** (effet et message), **états**, **règles liées**, **clavier et accessibilité**, **tests associés**. Les maquettes générales sont au fichier 07 du dossier principal ; les messages sont au fichier 06 du lot ; les règles chiffrées au fichier 02.

**Conventions communes à tous les écrans**
- **En-tête** permanent : logo de l'organisme · bouton **« Partager un rapport »** · recherche globale · cloche · compte. Les entrées de navigation dépendent des rôles (fichier 07 §2.1).
- **Fil d'Ariane** sur les pages de détail. **Titre de page** unique et explicite.
- **Libellés** en langage simple ; jargon expliqué par une bulle d'aide.
- **Fiabilité, fraîcheur, source** : composants du fichier 07 §3, utilisés partout où un chiffre ou un fait est affiché.
- **Chaque action destructive** (retrait, rejet en lot, suppression) demande une confirmation avec résumé de l'effet.
- **Enregistrement** : automatique pour les brouillons ; explicite (bouton) pour les validations.
- **Tout champ obligatoire** est marqué et **expliqué** (jamais d'erreur muette).
- Les **droits** sont appliqués à l'affichage : ce qui n'est pas autorisé n'apparaît pas (message neutre si l'utilisateur tente d'y accéder).

Liste des écrans du lot : E-01 Bienvenue · E-00 Accueil · E-02 Dépôt · E-03 Choix du gabarit · E-04 Éditeur guidé · E-05 Signalement court · E-06 Revue des faits · E-07 Demande de précision · E-08 Mes rapports · E-09 Fiche application · E-10L Fiche initiative · E-24 Assistant · E-25 Vue stratégique (réduite) · E-27 Santé du référentiel · E-28 Administration (base) · E-29 Bibliothèque et recherche · E-30 Tâches et notifications · E-31 Journal d'audit · E-32 Import du référentiel · E-33 Référentiel (listes et fiches) · E-34 Pages d'information.

---

## E-01. Bienvenue (première connexion)

- **Acteurs / accès** : tout utilisateur à sa première connexion ; rappelable depuis l'aide.
- **Objectif** : expliquer en moins d'une minute à quoi sert Odin et poser les garde-fous (pas d'évaluation des personnes, rôle de l'IA).
- **Entrée** : première authentification.
- **Contenu**
  - Écran 1 « **Partagez, Odin comprend** » : vous écrivez comme d'habitude ; Odin propose ; vous confirmez.
  - Écran 2 « **Ce qu'Odin fait et ne fait pas** » : *Odin évalue des applications et des équipes, jamais des personnes. L'IA propose, vous décidez. Vos contributions servent à planifier et à décider ; elles ne servent pas à vous noter ni à vous comparer.*
  - Écran 3 « **Qui voit quoi** » : niveaux de visibilité N1 à N4 (selon la configuration de l'organisme) ; lien vers « Mes droits ».
  - Écran 4 (facultatif) « **Votre périmètre** » : champ **Équipe** (liste ; pré-sélection depuis l'annuaire) ; champ **Applications et projets** (sélection multiple, facultatif).
- **Actions** : *Suivant* ; *Précédent* ; *Passer* (accessible dès l'écran 1) ; *Terminer* → page d'accueil, avec proposition **« Partager mon premier rapport »**.
- **États** : équipe inconnue → rattachement provisoire à la direction ; annuaire indisponible → saisie libre de l'équipe.
- **Règles** : prise de connaissance **journalisée** (date, version du texte) ; le texte est **versionné** (re-présentation si une version majeure change).
- **Clavier / accessibilité** : navigation complète au clavier ; titres de niveau 1 ; contraste ; lecture d'écran des étapes (« étape 2 sur 4 »).
- **Tests** : T-ACU-*, T-ACC-*.

## E-00. Accueil

- **Acteurs / accès** : tout utilisateur authentifié.
- **Objectif** : montrer immédiatement **ce qui attend l'utilisateur** et **ce que ses contributions ont changé**.
- **Contenu (zones, dans l'ordre)**
  1. **Salutation** et date de la dernière connexion.
  2. **À faire** (au plus 5 éléments, + lien « Tout voir » → E-30) : faits à relire (N-01), précisions à répondre (N-03), rapports périodiques attendus (N-06), faits à valider si rôle de validation (N-02). Chaque ligne : intitulé, objet concerné, échéance, bouton d'action direct.
  3. **Ce que vos rapports ont changé** (3 derniers) : « Votre rapport de mars a mis à jour la fiche de PortailUsagers ».
  4. **Mon périmètre** (cartes, au plus 6) : objets dont l'utilisateur est responsable ou membre de l'équipe : santé (pastille + libellé), fraîcheur, nombre de faits à valider.
  5. **Question à Odin** : champ unique ; envoi → E-24.
  6. **Alertes** (selon rôle) : signaux pertinents (contradictions, fiches périmées de son périmètre).
- **Variantes par rôle**
  - R01/R02 : zones 1 à 5 ; R02 ne voit que ses périmètres.
  - R03/R04 : mise en avant de « Faits à valider » et de la santé calculée de leurs objets.
  - R05 : zone « Mon équipe » (rapports récents, faits à valider de l'équipe) ; **aucune vue nominative d'évaluation**.
  - R07 : « Faits de sécurité à valider » (N4) ; R12/R16 : files de curation ; R13/R14 : lien vers E-25 en tête.
- **États** : aucun élément → messages d'état vide (ex. « Rien à faire pour l'instant. Merci ! ») ; premier usage → proposition « Partager mon premier rapport ».
- **Règles** : aucune information N3/N4 n'apparaît dans les intitulés si l'utilisateur n'est pas habilité (message neutre) ; limite d'affichage pour éviter la surcharge.
- **Tests** : T-ACU-*, T-DRO-*, T-NOT-*.

## E-02. Dépôt d'un rapport

- **Acteurs / accès** : R01 et tous rôles de contribution ; R02 sur ses périmètres.
- **Objectif** : déposer un document ou un texte en **moins de 2 minutes**, avec une saisie minimale.
- **Entrée** : bouton « Partager un rapport » (en-tête), glisser-déposer n'importe où sur la page, ou transfert d'un texte collé.
- **Contenu**
  - **Zone de dépôt** : fichiers (un ou plusieurs), texte collé, ou **bouton « Choisir un fichier »**. Formats : texte, tableur, présentation, document portable, courriel, texte brut. **Taille max** PAR-13.
  - Après dépôt, **panneau de proposition** (modifiable) :
    - **Titre** : proposé (nom du fichier ou première ligne) ; obligatoire.
    - **Type de rapport** : liste (G-01, G-02, G-04, G-05, G-09, G-18 + types reconnus) ; proposé ; obligatoire.
    - **Période couverte** : date ou intervalle ; proposée ; obligatoire (défaut : mois du dépôt).
    - **Rattachements** : puces (applications, initiatives, équipes, services rendus) ; proposés avec indication « certain / à confirmer » ; possibilité de choisir « **Aucun rattachement** ».
    - **Visibilité** : *Mon périmètre* (défaut selon gabarit) / *Restreint à…* (choix de personnes ou rôles) / *Ouvert à toute l'organisation* ; **N4** proposé selon §3 du fichier 02, avec motif ; obligatoire.
    - **Avertissements** (zone dédiée, non bloquante sauf mention) : données personnelles détectées [Voir et masquer] ; tentative d'instruction détectée ; contenu possiblement hors périmètre ; doublon probable.
    - **Information fixe** : « Tous les contenus sont acceptés ; la visibilité suit les droits » + lien « Mes droits ».
  - **Boutons** : *Partager* (principal) ; *Enregistrer en brouillon* ; *Annuler*.
- **Actions**
  - *Partager* → statut « Déposé » ; écran de confirmation : « Rapport partagé. Odin l'analyse ; vous serez prévu(e) quand les faits seront prêts à relire. » ; lien « Déposer un autre rapport » / « Voir mes rapports ».
  - *Plusieurs fichiers* → **un rapport par fichier** ; propositions par fichier ; bouton « Partager tous ».
  - *Masquer* (données personnelles) → sélection de passages ; **version masquée** utilisée pour l'analyse et l'affichage ; l'original reste visible de l'auteur seul (selon politique).
  - *Doublon probable* → trois choix (fichier 02 §12).
- **États** : analyse **en cours** (indicateur de progression, possibilité de quitter) ; erreur de format ; document protégé ; taille dépassée ; IA indisponible (rapport partagé, analyse **en attente**, bandeau discret) ; alerte protégée détectée (E-02 affiche le message de renvoi, sans analyse, rapport conservé en brouillon privé).
- **Règles** : RG-03, RG-04, RG-24, RG-32, IA-07, IA-08, IA-12, IA-17 ; contributeur externe : rattachements limités à son périmètre.
- **Clavier / accessibilité** : zone de dépôt **utilisable sans souris** (bouton « Choisir un fichier », touche d'envoi) ; alternatives textuelles aux icônes ; annonces d'état pour lecteurs d'écran (« analyse en cours »).
- **Tests** : T-DEP-*, T-SEC-*, T-DEG-*.

## E-03. Choix du gabarit

- **Acteurs / accès** : tout contributeur.
- **Contenu** : cartes de gabarits (nom, description d'une ligne, durée estimée de rédaction, dernier usage). Ordre : **ceux du rôle** en premier (R04 → G-01 ; R03 → G-09, G-05 ; autres → G-18, G-04, G-02). Option **« Document libre »**.
- **Actions** : sélectionner → E-04 ; **« Reprendre un brouillon »** si existant.
- **Tests** : T-GAB-*.

## E-04. Éditeur guidé

- **Acteurs / accès** : selon gabarit.
- **Objectif** : rédiger rapidement un rapport structuré, **prérempli** depuis les faits validés et le dernier rapport.
- **Contenu commun** : en-tête (titre, période, rattachements pré-remplis, visibilité) ; sections du gabarit ; **volet d'aide** (exemples, rappel du dernier rapport, valeurs précédentes) ; **bouton « Reformuler avec l'IA »** par section (propose, l'auteur choisit) ; **enregistrement automatique** (horodatage visible) ; **aperçu**.
- **Champs par gabarit** (voir tables ci-dessous).
- **Actions** : *Partager* (même chaîne que E-02) ; *Soumettre pour validation* (G-01 si validation exigée) ; *Enregistrer et quitter*.
- **États** : conflit de modification (deux auteurs) → comparaison ; perte de connexion → brouillon conservé localement et message de reprise ; section obligatoire vide → liste claire des manques.
- **Règles** : EX-RAP-04/05 ; IA-13 (reformulation non destructive, original conservé) ; le texte libre est **analysé** comme un document déposé ; les champs structurés produisent des faits **F1 directement** (déclarés par l'auteur).
- **Tests** : T-GAB-*, T-IAX-*.

### Champs du gabarit G-01 Rapport d'avancement de projet

| Section | Champ | Type | Obligatoire | Prérempli depuis |
|---|---|---|---|---|
| Identité | Initiative | Sélection | Oui | Initiative de l'auteur |
| | Période | Mois | Oui | Mois précédent |
| Avancement | Avancement global (%) | 0–100 | Oui | Dernier fait (+ rappel de l'écart) |
| | Santé déclarée | Conforme / Vigilance / Critique | Oui | — |
| | Commentaire | Texte | Non | — |
| Jalons | Liste de jalons | Libellé, date prévue, statut | Oui (au moins 1) | Jalons existants |
| | Cause du décalage | Texte | Si décalé | — |
| Budget | Consommé, prévu (€), HT/TTC | Nombres + choix | Non | Dernier fait |
| Difficultés et risques | Texte libre + bouton « Ajouter un risque » (intitulé, cause, gravité facultative) | | Non | — |
| Ressources | Besoin ou manque par profil (profil, ETP, période) | | Non | — |
| Décisions attendues | Texte (+ instance, date) | | Non | — |
| Bénéfices | Texte | | Non | — |

### Champs du gabarit G-02 Retour d'expérience

| Section | Champ | Obligatoire | Aide |
|---|---|---|---|
| Contexte | Application ; date et heure de début ; durée | Oui | — |
| Chronologie | Texte | Non | « Décrivez ce qui s'est passé, dans l'ordre » |
| Impact | Texte ; nombre d'usagers ou de dossiers touchés | Non | — |
| Causes | Texte | Oui | **Rappel affiché : « Décrivez les causes liées aux processus, à l'outillage ou à l'organisation, pas aux personnes. »** |
| Ce qui a bien fonctionné | Texte | Non | — |
| Actions | Libellé, responsable (rôle ou personne), échéance | Non | — |
| Clos | Oui / Non | Oui | — |

### Champs du gabarit G-04 Fiche de risque

| Champ | Obligatoire | Aide |
|---|---|---|
| Objet (application, initiative) | Oui | — |
| Intitulé | Oui | — |
| Cause ; conséquence | Non | — |
| Gravité estimée ; vraisemblance estimée | Non | « Laissez vide si vous ne savez pas » |
| Mesures envisagées | Non | — |
| Visibilité | Oui | Défaut **N3** |

### Champs du gabarit G-05 Fiche de dette

| Champ | Obligatoire | Aide |
|---|---|---|
| Application | Oui | — |
| Type de dette | Oui | Liste (fichier 03 §6) |
| Description | Oui | — |
| Technologie concernée ; date de fin de support | Si « technologie obsolète » | — |
| Intérêt annuel estimé ; fiabilité (chiffrée / estimée / inconnue) | Non | « Une fourchette suffit » |
| Effort estimé (j.h) | Non | — |
| Échéance critique | Non | — |

### Champs du gabarit G-09 État d'une application

| Champ | Obligatoire | Prérempli depuis |
|---|---|---|
| Application | Oui | Application de l'auteur |
| Période | Oui | Trimestre |
| Faits marquants | Non | — |
| Incidents de la période (nombre, majeurs) | Non | Faits existants |
| Fin de support connue | Non | Faits existants |
| Dette connue | Non | Faits existants |
| Perspectives | Non | — |

### Gabarit G-18 Document libre
Titre ; période ; rattachements ; texte. Aucune autre contrainte.

## E-05. Signalement court

- **Acteurs / accès** : tout utilisateur.
- **Contenu** : zone de texte (jusqu'à 1 000 caractères) ; **nature** (puces : Risque, Problème, Dette, Idée, Besoin) ; **objet concerné** (suggéré ; facultatif) ; **visibilité** (défaut : mon périmètre ; case **« Signalement discret vers [rôle] »** → liste : RSSI, référent du domaine ; l'identité de l'auteur n'est visible que du destinataire et de l'auditeur habilité, RG-23) ; **mention fixe** : « Pour des faits graves concernant des personnes, utilisez la procédure d'alerte de votre organisme » avec lien configurable.
- **Actions** : *Envoyer* → accusé immédiat « Signalement transmis à [rôle]. Vous serez informé(e) de la suite. » ; analyse comme un mini-rapport.
- **États** : texte vide → bouton inactif ; contenu relevant de l'alerte protégée → message de renvoi, pas d'envoi ; IA indisponible → envoi sans analyse.
- **Règles** : EX-RAP-18/19 ; RG-23, RG-24.
- **Tests** : T-SIG-*.

## E-06. Revue des faits (écran central)

- **Acteurs / accès** : l'auteur du rapport (revue F0 → F1) ; responsable de l'objet et curateur (validation F1 → F2, mode « Validation »).
- **Objectif** : confirmer, corriger ou rejeter les faits proposés **vite**, avec la source sous les yeux.
- **Mise en page** : deux volets.
  - **Gauche : le document** (texte ou aperçu), avec **passages surlignés** au survol d'un fait ; navigation par fait précédent/suivant.
  - **Droite : les faits proposés**, **groupés par nature** (Avancement, Jalons, Budget, Risques, Incidents, Dette, Sécurité, Ressources, Dépendances, Décisions, Autres). Ordre : **contradictions** d'abord, puis **faible confiance**, puis le reste.
- **Chaque fait affiche** : étiquette de nature ; valeur lisible (« Recette : 30/04/2026 (décalée, initiale 15/04) ») ; objet rattaché (avec « certain/à confirmer ») ; **confiance** (haute/moyenne/faible, en texte et icône) ; **statut** (proposé) ; éventuel **avertissement** (contradiction, champ manquant, valeur inhabituelle) ; boutons.
- **Boutons par fait** : **✓ Confirmer** ; **✎ Corriger** (ouvre les champs de la nature, fichier 03) ; **✗ Rejeter** (motif facultatif : *inexact*, *hors sujet*, *déjà connu*, *sensible*, *autre*) ; **Demander à quelqu'un…** (crée une demande de précision) ; **Scinder** / **Fusionner** (si pertinent).
- **Actions groupées** : **« Confirmer les faits fiables (N) »** = confiance **haute** + **sans contradiction** + **rattachement certain** + **non sensible (N4)** ; **« Rejeter les faits sélectionnés »** ; **« Tout confirmer pour cette nature »** (faits de confiance haute uniquement).
- **Panneau d'effet** (bas) : « Confirmer ces faits met à jour : fiche INI-01 (avancement, jalons), santé calculée de INI-01 ». Chaque effet est un lien.
- **Avertissements du rapport** (haut) : passages évaluatifs nominatifs **ignorés** (avec option de reformuler), tentatives d'instruction, données personnelles, contexte manquant.
- **Fin de revue** : bouton **« Terminer »** actif dès que **tous les faits sont traités** ou explicitement **laissés en attente** (« Je reviendrai plus tard »). Effet : faits confirmés → F1 ; non traités → restent F0 et **non utilisés** ; le rapport passe à **Publié** ; rappel automatique pour les faits en attente (N-01, puis N-10 à PAR-11).
- **Mode Validation (F1 → F2)** : même écran, affichant **plusieurs rapports** pour le même objet, **valeur retenue** et **valeurs concurrentes** ; boutons **Valider** / **Rejeter** / **Demander une précision** ; refusé si la personne est l'auteur et seul valideur (fichier 02 §4).
- **États** : analyse non terminée (progress) ; aucun fait détecté (« Aucun fait détecté dans ce rapport » + résumé ; possibilité d'ajouter un fait manuellement) ; document trop long (découpé en parties) ; erreur de rattachement (objet inexistant : créer ou curation).
- **Règles** : EX-IAF-04/05/06/08/10/11/12/14/15 ; RG-05, RG-07, RG-33 ; IA-01/02/03/06/08/12/14.
- **Clavier** : raccourcis (↑/↓ fait suivant, **C** confirmer, **R** rejeter, **E** corriger) avec aide visible ; focus visible ; tout est utilisable sans souris.
- **Tests** : T-REV-*, T-IAX-*, T-SEC-*, T-NOM-*.

## E-07. Demande de précision

- **Acteurs / accès** : le répondant (auteur ou responsable de l'objet).
- **Contenu** : **question** en une phrase ; **contexte** (les deux faits en conflit avec sources, ou la donnée manquante) ; **choix prédéfinis** (« Le premier est correct », « Le second est correct », « Les deux, voir précision », « Je ne sais pas, voir [rôle] ») ; **zone libre** ; **échéance** souhaitée.
- **Actions** : *Répondre* → met à jour les faits (fichier 02 §5) et ferme le signal ; *Transmettre à…* (désigner un autre répondant) ; *Ce n'est pas clair* (retour qualité).
- **États** : déjà résolue (par un tiers) → message d'information ; échue → bandeau neutre.
- **Règles** : fichier 02 §13 ; RG-30 (formulation neutre).
- **Tests** : T-PRE-*.

## E-08. Mes rapports

- **Contenu** : tableau (titre, type, période, statut, faits « confirmés/total », visibilité, date) ; filtres (statut, type, période) ; onglet **Brouillons** ; panneau latéral **« Ce que cette contribution a changé »** (objets mis à jour, indicateurs concernés, décisions qui citent, **sans** contenu hors droits).
- **Actions par rapport** : *Ouvrir* ; *Relire les faits* ; *Remplacer par une nouvelle version* ; *Retirer* (confirmation, RG-20/21) ; *Changer la visibilité* (dans les limites des droits) ; *Exporter*.
- **États** : vide → « Aucun rapport. Partagez le premier. ».
- **Tests** : T-RAP-*.

## E-09. Fiche application

- **Acteurs / accès** : lecture selon droits ; modification par R03 (son application), R06, R16.
- **Onglets du lot 1** : **Synthèse** · **Faits à valider** · **Rapports** · **Historique**. (Dette, Risques, Technologies, Contrats, Coûts, Équipe : lots suivants.)
- **En-tête** : nom (+ alias), statut de cycle de vie, responsable (rôle et nom), équipe, **criticité** (avec bouton « Pourquoi ? » et ajustement motivé), **services rendus servis** (puces cliquables), **santé calculée** (pastille + libellé + « Pourquoi ? »), **fraîcheur** (« mis à jour il y a N jours », alerte au-delà du seuil), badge **« Orpheline »** ou **« Fiche périmée »** si applicable.
- **Synthèse** : **résumé IA** des 90 derniers jours (avec **sources cliquables** et mention IA, bouton *Régénérer*) ; **faits clés** : fins de support (liste), dettes critiques, derniers incidents, constats de sécurité (**nombres seulement** pour les non-habilités N4) ; **indicateurs** de l'objet.
- **Faits à valider** : liste des F1 en attente de F2 avec actions *Valider / Rejeter / Demander une précision* (mode Validation d'E-06).
- **Rapports** : liste des rapports rattachés (selon droits), tri par date.
- **Historique** : modifications de fiche, validations, changements de santé (date, règle déclenchante).
- **Actions** : *Modifier la fiche* (champs : nom, alias, description, responsable, équipe, services rendus, mode de fourniture, statut) ; *Ajouter un fait* (fichier 03 §16) ; *Demander un rapport* (à l'équipe ou au responsable) ; *Exporter la fiche*.
- **États** : **Non évaluée** (aucun fait F1+) ; application **retirée** (lecture seule).
- **Règles** : RG-08, RG-09, RG-10 ; fichier 02 §9–10.
- **Tests** : T-SAN-*, T-DRO-*, T-QUA-*.

## E-10L. Fiche initiative (légère)

- **Contenu** : nom (+ alias), responsable, équipe, applications liées, dates, statut ; **santé calculée** (règles §11) **à côté** de la **santé déclarée** (écart surligné) ; **avancement** (dernière valeur F1+ et évolution) ; **jalons** (prévu, initial, statut) ; **budget** (consommé/prévu déclarés, mention « déclaratif ») ; **faits à valider** ; **rapports** ; **historique**.
- **Actions** : modifier (R04, R12) ; ajouter un fait ; demander un rapport.
- **Hors lot** : portefeuille complet, scénarios, ETP, dépendances (lots 2 et 3).
- **Tests** : T-SAN-*, T-FIA-*.

## E-24. Assistant

- **Acteurs / accès** : tout utilisateur.
- **Contenu** : **champ de question** (toujours visible) ; **suggestions** selon le rôle (ex. R13 : « Quelles applications critiques sont en fin de support cette année ? » ; R04 : « Où en est mon projet ? » ; R01 : « Quels rapports parlent de mon application ? ») ; **réponse** structurée (résumé, détails, **Sources**, **Fiabilité et fraîcheur**, **Actions suggérées**) ; **retour** (utile / inexacte / incomplète).
- **Actions** : poser une question ; ouvrir une source ; exécuter une action suggérée (ouvrir la fiche, demander une précision, créer un signalement) ; **« Effacer l'historique »** (de l'utilisateur).
- **États** : information absente (« Je n'ai pas cette information. Qui interroger : … ») ; refus (évaluation de personnes, hors droits, instructions de document) avec explication et alternative ; **IA indisponible** → recherche textuelle simple.
- **Règles** : fichier 02 §16 ; RG-01, RG-04, RG-22 ; IA-04/05/06/10/11.
- **Tests** : T-ASS-*.

## E-25. Vue stratégique (réduite)

- **Acteurs / accès** : R13, R14 ; accessible aux rôles de gouvernance en lecture.
- **Tuiles du lot 1** : **Santé du parc applicatif** (L1-I01) · **Initiatives : déclaré vs calculé** (L1-I02) · **Fins de support proches sur applications critiques** (L1-I03) · **Applications orphelines** (L1-I04) · **Constats de sécurité critiques ouverts** (L1-I05, **valeur seule** pour les non-habilités N4) · **Couverture et fraîcheur** (L1-I06, I07) · **Fiabilité** (L1-I08) · **Décisions attendues** (L1-I12).
- **Chaque tuile** : valeur, **tendance** (à partir de la 2ᵉ période), **fiabilité** (barre), **fraîcheur**, **complétude**, lien **« Pourquoi ? »** (3 faits contributeurs principaux avec sources) et **« Voir le détail »** (liste filtrée).
- **Contrôles** : sélecteur de **période** (mois, trimestre) ; sélecteur de **périmètre** (organisme / direction / équipe) ; **résumé hebdomadaire** (case pour recevoir N-12).
- **Règles** : RG-05 (mention « déclaratif »), RG-06, RG-04 ; aucune vue nominative d'évaluation.
- **États** : indicateur sans donnée → « Pas assez de faits » + **bouton « Demander un rapport »** ; indicateurs en cours de clarification (contradiction) → mention.
- **Tests** : T-FIA-*, T-DRO-*.

## E-27. Santé du référentiel

- **Acteurs / accès** : R16, R06, R12, R17.
- **Contenu** : **couverture** (L1-I06) ; **fraîcheur** (L1-I07) ; **faits en attente** (F0/F1) ; **orphelins** (applications, initiatives sans responsable) ; **doublons possibles** ; **contradictions ouvertes** ; **rattachements ambigus** ; **qualité de l'IA** (L1-I11 par nature et par type de rapport) ; **adoption** (L1-I09, **agrégée**).
- **Files de travail** : (1) *À valider* (second niveau) ; (2) *Rattachements ambigus* (choisir l'objet) ; (3) *Doublons* (fusionner) ; (4) *Orphelins* (désigner un responsable).
- **Actions** : traiter un élément ; **relancer** (messages préparés, sobres, RG-34) ; **demander un rapport** sur un objet critique sans information.
- **Règles** : RG-10, RG-30, RG-34 ; EX-QUA-01..06.
- **Tests** : T-QUA-*.

## E-28. Administration (base)

- **Acteurs / accès** : R17 (accès aux contenus N3/N4 **non** accordé par défaut, ET-03).
- **Rubriques du lot 1** : **Organisation** (directions, équipes) · **Rôles et périmètres** (attribution, délégations, expirations, contributeurs externes avec date de fin) · **Référentiels** (types de rapports, natures de faits, profils) · **Gabarits** (modification des textes d'aide, champs facultatifs) · **Seuils et règles** (PAR-01 à PAR-19, règles de santé §10–11, niveaux de classification, seuil d'agrégation avec plancher 3) · **Conservation** · **Vocabulaire** (libellés) · **Import / export** · **Journal des modifications**.
- **Principe** : chaque modification propose un **aperçu d'impact** (« 12 applications changeraient de santé ») avant application ; la modification s'applique **à partir de la date choisie** (non rétroactive par défaut) ; chaque changement est **journalisé**.
- **Règles** : EX-ADM-01..05/08/09/10 ; EX-ACC-04/05/08.
- **Tests** : T-ADM-*.

## E-29. Bibliothèque de rapports et recherche

- **Acteurs / accès** : tout utilisateur (résultats limités à ses droits).
- **Contenu** : **barre de recherche** (texte intégral) ; **filtres** : type, période, objet, auteur (nom, **non utilisé pour classer**), statut, niveau ; **liste** (titre, type, période, objet, statut, niveau ; extrait de texte correspondant surligné) ; **tri** par date, pertinence ; **filtres enregistrables**.
- **Actions** : ouvrir un rapport (aperçu, faits, historique des versions) ; ajouter aux favoris ; exporter la liste.
- **Règles** : EX-RAP-09/10 ; RG-04.
- **Tests** : T-RAP-*, T-DRO-*.

## E-30. Tâches et notifications

- **Contenu** : **boîte de tâches** (à relire, à valider, à répondre, à rédiger) avec échéance, objet, bouton d'action ; **historique des notifications** (lues/non lues) ; **préférences** (par type : application / courriel / aucun ; regroupement quotidien). Les notifications **obligatoires** (N-03, N-11) ne sont pas désactivables.
- **Règles** : fichier 02 §14 ; RG-29 ; PAR-09.
- **Tests** : T-NOT-*.

## E-31. Journal d'audit

- **Acteurs / accès** : R15, R17 (limité), R07 (périmètre sécurité), R08 (périmètre données personnelles et IA).
- **Contenu** : liste chronologique (date, acteur, action, objet, avant/après) ; filtres (période, acteur, type d'action, objet) ; **recherche** ; **export** reproductible. Actions journalisées : dépôt, partage, retrait, confirmation, rejet, validation, correction, accès N4, habilitation, modification de règle, usage de l'IA (analyses, assistant : **sans le texte des questions**), import, connexion à l'administration.
- **Règles** : EX-AUD-01/02/04/05/07 ; RG-22 ; le journal est **immuable** (aucune modification ni suppression par l'interface).
- **Tests** : T-AUD-*.

## E-32. Import du référentiel

- **Acteurs / accès** : R17, R12.
- **Parcours** : 1) **choisir le type** (Équipes, Personnes, Services rendus, Applications, Initiatives) ; 2) **télécharger le modèle** ou **déposer le fichier** ; 3) **aperçu** (tableau : créés / modifiés / rejetés, avec **motif par ligne rejetée**, propositions de **rapprochement** à ≥ 90 %) ; 4) **confirmer** ; 5) **résultat** (récapitulatif) + **annuler l'import** (24 h).
- **Règles** : fichier 02 §17 ; journalisation ; responsables inconnus → importés sans responsable (objet orphelin).
- **Tests** : T-IMP-*.

## E-33. Référentiel : listes et fiches

- **Acteurs / accès** : lecture tous (selon droits) ; modification R06, R12, R17 ; R03/R04 sur leurs objets.
- **Contenu** : listes (Applications, Initiatives, Équipes, Services rendus, Personnes) avec filtres, tri, recherche, **colonnes** (nom, responsable, équipe, criticité, santé, fraîcheur) ; **formulaires** de création/modification (champs du fichier 02 §17) avec **alias** ; **désignation d'un responsable** (rôle R03/R04 attribué sur l'objet) ; **fusion** de doublons.
- **Annuaire des personnes** : nom, équipe, profil (facultatif), rôles dans Odin ; **aucune évaluation, aucun classement** ; visibilité des fiches selon droits.
- **Règles** : EX-REF-01/02/03/07/08/13/15/16.
- **Tests** : T-IMP-*, T-QUA-*, T-DRO-*.

## E-34. Pages d'information

- **Pages** : **Ce que fait l'IA** (IA-19 : ce qu'elle fait, limites, comment contester, contact du DPO) ; **Mes droits et ma confidentialité** (liste de mes rôles, niveaux visibles, mes contributions, comment retirer ou rectifier, RG-21) ; **Glossaire** ; **Aide et formation** (guides courts par rôle) ; **Contact et soutien**.
- **Règles** : ET-10, ET-27/28.
- **Tests** : T-ACU-*.
