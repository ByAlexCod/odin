# 07. UX : navigation, écrans clés et comportements

Les maquettes ci-dessous sont des **schémas fonctionnels en texte** : elles fixent l'organisation et le contenu, pas l'esthétique. Le design visuel est une étape ultérieure.

## 1. Principes UX

1. **Déposer d'abord** : l'action « Partager un rapport » est visible en permanence ; elle est la plus rapide de l'outil.
2. **Montrer la valeur au contributeur** : retour immédiat (ce que mon rapport a changé), rappels utiles, synthèses de ses objets.
3. **Une interface, plusieurs profondeurs** : le contributeur voit 5 entrées ; le décideur voit la vue stratégique ; l'expert voit les détails.
4. **Toujours la source** : tout chiffre, tout fait, toute réponse est à un clic de sa source.
5. **Toujours la fiabilité** : couleur/étiquette de fiabilité (déclaré, confirmé, validé, vérifié) et fraîcheur visibles sans effort.
6. **Pas de jugement sur les personnes** : aucune vue ne désigne une personne comme cause d'un problème ; le vocabulaire est celui des objets et des rôles.
7. **Langage simple** : pas de jargon sans bulle d'aide ; vocabulaire de l'organisme paramétrable.
8. **Peu de clics** : actions fréquentes en 1 à 3 clics ; confirmations en lot.
9. **Pas de culpabilisation** : relances sobres, factuelles, utiles.
10. **Accessibilité d'emblée** : exigences en §8.

## 2. Architecture de l'information

### 2.1 Navigation principale (varie selon les rôles)

| Entrée | Contenu | Visible pour |
|---|---|---|
| **Accueil** | Boîte de tâches, mes objets, alertes pertinentes, bouton « Partager un rapport » | Tous |
| **Mes rapports** | Rapports déposés, brouillons, faits à relire | Tous |
| **Mon périmètre** | Mes applications / projets / équipe : synthèses et faits | Tous (selon rattachements) |
| **Patrimoine** | Applications, services rendus, technologies, équipes | Tous (contenu selon droits) |
| **Transformation** | Demandes, portefeuille, roadmaps, scénarios | Tous (lecture) ; gestion pour PMO et responsables |
| **Dette** | Registre de dette, obsolescence | Tous (lecture) ; gestion selon rôles |
| **Ressources** | Capacité, charge, vacances, dépendances (agrégé) | R05, R10, R12, R13 |
| **Finances et contrats** | Budget, dépenses, marchés, licences | R09, R11, R12, R13 + lecture ciblée |
| **Sécurité et conformité** | Risques, homologations, registre réglementaire | R07, R08, R13 + lecture ciblée |
| **Décisions** | Comités, notes, registre des décisions, recommandations de contrôle | Tous (publiques) ; gestion R12, R13 |
| **Restitutions** | Atelier de rapports et présentations, bibliothèque | Tous (selon droits) |
| **Assistant** | Questions en langage naturel | Tous |
| **Qualité** | Santé du référentiel, files de curation | R16, R06, R12, R17 |
| **Administration** | Paramétrage | R17 |

Le **contributeur simple** (R01) voit seulement : Accueil, Mes rapports, Mon périmètre, Patrimoine (lecture), Assistant. Les autres entrées apparaissent selon ses rôles.

### 2.2 Éléments transversaux

- **Bouton « Partager un rapport »** : en-tête, toujours visible.
- **Recherche globale** : rapports, objets, décisions, textes (selon droits).
- **Cloche de notifications** et **boîte de tâches**.
- **Sélecteur de périmètre / de période** persistant (équipe, direction, exercice).
- **Aide** : introduction, glossaire, page « Ce que fait l'IA », page « Mes droits et ma confidentialité ».
- **Barre de fiabilité** : légende des niveaux de fiabilité.

## 3. Composants et conventions récurrents

| Composant | Description |
|---|---|
| **Étiquette de fiabilité** | Proposé · Déclaré · Validé · Vérifié (couleur + texte + icône, jamais la couleur seule) |
| **Fraîcheur** | « Mis à jour il y a N jours », avec alerte au-delà du seuil |
| **Santé** | Conforme / sous vigilance / critique, avec bouton « Pourquoi ? » listant les règles et faits contributeurs |
| **Source** | Lien discret vers rapport + extrait + date + auteur (rôle) ; survol = aperçu |
| **Niveau de confidentialité** | Pastille N1 à N4 avec libellé clair ; cadenas pour restreint |
| **Marqueur IA** | Icône « généré avec l'aide de l'IA » sur les contenus concernés |
| **Carte objet** | Nom, responsable (rôle), santé, fraîcheur, 3 indicateurs clés, actions |
| **Tableau filtrable** | Filtres enregistrables, tri, regroupements, export |
| **Fil d'historique** | Qui/quand/quoi, modifications, validations, versions |
| **Demande de précision** | Question en une phrase + choix prédéfinis |
| **Mode comparaison** | Deux versions/scénarios côte à côte avec différences surlignées |

## 4. Écrans clés

### E-01. Bienvenue (première connexion)

```
┌────────────────────────────────────────────────────────────┐
│  Bienvenue sur Odin                                  [1/3] │
│  Partagez vos rapports : Odin les comprend pour vous.      │
│  • Vous écrivez comme d'habitude.                          │
│  • Odin propose, vous confirmez.                           │
│  • Odin n'évalue pas les personnes.                        │
│                              [Passer]   [Suivant ▶]        │
└────────────────────────────────────────────────────────────┘
```

### E-00. Accueil (contributeur)

```
┌ Odin ─ [Partager un rapport] ─ 🔍 Rechercher ─ 🔔 ─ Mon compte ┐
│ Bonjour. Voici ce qui vous attend :                           │
│  À FAIRE (3)                                                  │
│  ▸ Relire 7 faits du rapport « Avancement mars »   [Relire]   │
│  ▸ Répondre : quelle date de MEP pour l'appli X ?  [Répondre] │
│  ▸ Rapport mensuel du projet Y (échéance 5 avril)  [Rédiger]  │
│  CE QUE VOS RAPPORTS ONT CHANGÉ                               │
│  ▸ Votre rapport de février a mis à jour la fiche Appli X     │
│  MON PÉRIMÈTRE                                                │
│  [Appli X · Vigilance · à jour il y a 12 j] [Projet Y · ...]  │
│  Poser une question à Odin : [__________________________ ▶]  │
└────────────────────────────────────────────────────────────────┘
```

### E-02. Dépôt d'un rapport

```
┌ Partager un rapport ───────────────────────────────────────┐
│  ┌──────────────────────────────────────────────┐          │
│  │  Glissez un document ici                      │          │
│  │  ou collez un texte ou choisissez un fichier  │          │
│  └──────────────────────────────────────────────┘          │
│  Détecté : Rapport d'avancement · période mars 2026        │
│  Rattaché à : [Projet Y ▾] [Appli X ▾] [+]                 │
│  Visibilité : (•) Mon périmètre  ( ) Restreint  ( ) Ouvert │
│  ⚠ Données personnelles possibles : [Voir et masquer]      │
│  Odin n'accepte pas d'informations classifiées de défense. │
│                      [Enregistrer en brouillon] [Partager] │
└────────────────────────────────────────────────────────────┘
```

Comportements : la zone de dépôt est active sur toute la page ; une barre de progression montre l'analyse ; l'utilisateur peut quitter ; l'étape « Partager » est la seule obligatoire.

### E-03. Choix d'un gabarit

Cartes de gabarits groupées par rôle (« Mes gabarits » en premier) avec description d'une ligne, durée estimée de rédaction (« 5 min ») et dernier usage. Option « Document libre ».

### E-04. Éditeur guidé

```
┌ Rapport d'avancement · Projet Y · avril 2026 ─ Enregistré à 10:42 ┐
│ 1. Avancement       Statut proposé : [En cours ▾]  Avanc.: [62%]│
│    (mois précédent : 55 %)        Commentaire : [______________] │
│ 2. Jalons           ▣ J3 Recette  prévu 12/04  → [Décalé au __]  │
│ 3. Budget           Consommé: [__] k€   Prévu: [__] k€           │
│ 4. Difficultés et risques  [Texte libre + « + Ajouter un risque »]│
│ 5. Ressources       Besoin / manque par profil : [Profil ▾][ETP] │
│ 6. Décisions attendues [_______]                                  │
│ [Reformuler avec l'IA ▾]       [Aperçu]   [Soumettre pour valid.] │
└──────────────────────────────────────────────────────────────────┘
```
Aide à la rédaction en volet latéral (exemples, valeurs précédentes) ; aucun champ nominatif d'évaluation.

### E-05. Signalement court

Une zone de texte ; chips de nature (Risque, Problème, Dette, Idée, Besoin) ; objet concerné suggéré ; visibilité ; case « Signalement discret vers [rôle] » ; bouton Envoyer. Texte d'aide : *« Pour des faits graves concernant des personnes, utilisez la procédure d'alerte de l'organisme [lien]. »*

### E-06. Revue des faits extraits (écran central)

```
┌ Document ───────────────────────┬ Faits proposés (14) ─────────────────┐
│ …l'avancement est de 62 %…      │ AVANCEMENT                           │
│ …la recette est décalée au…     │ ▣ 62 % · Projet Y · confiance élevée │
│ …le prestataire ne dispose plus │   [✓ Confirmer] [✎ Corriger] [✗]     │
│  de profil d'architecte…        │ JALONS                               │
│                                 │ ▣ Recette décalée au 30/04 ⚠ conflit │
│ (passage surligné au survol     │   avec rapport du 12/03 (15/04)      │
│  d'un fait)                     │   [Garder] [Remplacer] [Demander…]   │
│                                 │ RESSOURCES                           │
│                                 │ ▣ Manque profil Architecte (équipe Z)│
│                                 │   [✓] [✎] [✗]                        │
│                                 │ [Confirmer les faits fiables (9)]    │
└─────────────────────────────────┴──────────────────────────────────────┘
 Effet : confirmer met à jour la santé de « Projet Y »    [Terminer ▶]
```

Règles : contradictions et faibles confiances en premier ; passages évaluatifs nominatifs signalés « ignorés » avec option de pseudonymiser ; raccourcis clavier ; progression visible.

### E-07. Demande de précision

Carte compacte : question en une phrase, contexte (les deux faits), choix prédéfinis, zone libre, échéance. Pas de formulation accusatrice.

### E-08. Mes rapports

Tableau : titre · type · période · statut (déposé, analysé, à relire, publié, périmé) · faits (confirmés/total) · visibilité. Panneau « Ce que cette contribution a changé ». Actions : remplacer, retirer, exporter, changer la visibilité.

### E-09. Fiche application

```
┌ Application X · Responsable : [rôle] · Équipe : [Équipe Z] ─────────────────┐
│ Santé : ◐ Vigilance [Pourquoi ?]   Fraîcheur : 12 j   Criticité : Élevée    │
│ Services rendus servis : [Instruction des demandes] [Paiement]              │
│ Onglets : Synthèse | Faits à valider (8) | Rapports | Dette | Risques       │
│           Technologies | Contrats | Coûts | Équipe | Historique              │
│ SYNTHÈSE (IA)  Résumé des 90 derniers jours, sources citées     [Régénérer]  │
│ Points d'attention : fin de support technologie T (déc.), 2 dettes critiques │
│ Indicateurs : Dette estimée · Coût annuel · Incidents 90 j · Obligations     │
└──────────────────────────────────────────────────────────────────────────────┘
```

### E-10. Fiche initiative

Santé **calculée** à côté de la santé **déclarée** (écart surligné) ; jalons ; budget (consommé vs prévu) ; ETP par profil (agrégé) ; risques ; dépendances ; bénéfices attendus/constatés ; décisions ; rapports ; historique.

### E-11. Nouvelle demande

Formulaire court : besoin en texte libre ; service rendu ; urgence ; échéance et motif ; valeur attendue. Panneau « Existe déjà ? » (demandes similaires, initiatives, applications, solutions mutualisées).

### E-12. File de qualification (PMO)

Table avec regroupements suggérés, colonnes valeur/effort/urgence/échéance contrainte, actions Instruire, Fusionner, Différer, Refuser (avec motif), Demander un avis.

### E-13. Portefeuille

```
┌ Portefeuille 2026–2027 ──────────────── Grille : [Standard ▾] [Pondérations ⚙] ┐
│ ▢ Initiative         Score  Valeur Coût  ETP  Risque couvert  Dette  Échéance  │
│ ▣ Migration Appli X   82    ●●●    1,2M  6    Élevé           2     NON ARBIT. │
│ ▣ Portail usagers     74    ●●●●   0,8M  4    Moyen           0     —          │
│ ▣ Refonte SIRH        61    ●●     2,4M  9    Faible          1     —          │
│ [Contraintes : Budget 5M | Capacité par profil | Plafond d'emplois]             │
│ Dépassements : Profil Architecte −2 ETP ; Budget T3 +0,4M      [Créer scénario] │
└──────────────────────────────────────────────────────────────────────────────────┘
```

### E-14. Scénarios

Deux ou trois colonnes de scénarios : hypothèses modifiées en tête (surlignées), puis résultats (initiatives qui tiennent / retardées / abandonnées), tensions de capacité, coût du report, effets en chaîne. Boutons : *Dupliquer*, *Comparer à la référence*, *Convertir en proposition de décision*.

### E-15. Roadmap

Axe temporel par horizons (Maintenant / Prochainement / Plus tard) ; lignes = thèmes ou objectifs ; jalons ; liens de dépendance ; couches (échéances réglementaires, fins de support, calendrier ministériel) activables ; panneau de **conflits** (capacité, dépendance, échéance, fin de support) ; versions et comparaison.

### E-16. Registre de dette

Tableau : élément · type · application · intérêt estimé (fourchette) · effort · échéance critique · statut ; graphique de tendance ; indicateur « part de capacité consacrée à la dette » vs objectif ; action « Planifier dans une initiative », « Accepter (motif, revue) ».

### E-17. Capacité et ressources (agrégé)

```
┌ Capacité · Direction du numérique · T3 2026 ───────────────────────────────┐
│ Profil           Capacité  Demande  Charge  Vacances  Prestataires  Tension │
│ Architecte         4,0      6,0     150 %     1,0       1,0 (25 %)     ●●●  │
│ Développeur        18       17      94 %      2,0       6,0 (33 %)     ●    │
│ Analyste sécurité  3,0      3,5     117 %     0,0       0              ●●   │
│ Plafond d'emplois (ETPT) : 112 / 115     Règle de conversion ETP→ETPT [i]   │
│ ⓘ Équipes de moins de 5 personnes : valeurs remontées au niveau supérieur. │
└────────────────────────────────────────────────────────────────────────────┘
```
Pas de colonne ni d'export nominatif ; les hypothèses sont modifiables et visibles.

### E-18. Finances

Budget par programme/action/titre (AE/CP, voté, engagé, consommé, disponible) ; vue run/build ; coût par application/service ; dépenses non imputées (file d'imputation en lot) ; consolidation de la dépense numérique (export).

### E-19. Contrats et fournisseurs

Calendrier des échéances (fin, préavis, reconduction) ; fiche contrat ; indicateur de dépendance ; assistant de décision « renouveler / remettre en concurrence / sortir » avec impacts.

### E-20. Sécurité et risques

Posture (par domaine, application), registre des risques (matrice gravité × vraisemblance), homologations (échéances), constats et remédiations, exceptions, plans d'action. Contenu N4 masqué hors droits ; vue **direction** sans détail technique.

### E-21. Registre réglementaire

Table : texte · statut juridique · source · **vérifié le** · applicabilité · obligations · état · échéance. Badge « À revérifier ». Calendrier consolidé. Fiche texte avec historique des changements de statut.

### E-22. Comité

Ordre du jour (points, documents liés) ; par point : note de décision générée, commentaires, avis, décision à saisir (choix, motifs, hypothèses, responsables, échéances, bénéfices attendus) ; compte rendu brouillon ; suites créées automatiquement ; date de bilan.

### E-23. Atelier de restitution

```
┌ Produire : [Revue de portefeuille ▾]  Audience: [Comité d'investissement ▾] ┐
│ Période : [T1 2026]  Périmètre : [Direction du numérique]  [Composer]       │
│ ┌ Plan ─────────┬ Aperçu ───────────────────────────┬ Contrôles ─────────┐ │
│ │1 Synthèse     │ Titre-message : « 3 initiatives… » │ Classification: N2 │ │
│ │2 Portefeuille │ [graphique]  ⓘ source (clic)       │ Faits non validés: 2│ │
│ │3 Risques      │ Texte généré par IA (marqué)       │ Fraîcheur: OK      │ │
│ │4 Décisions    │ [Reformuler ▾]  [Ton : exécutif ▾] │ Noms détectés: 0   │ │
│ └───────────────┴────────────────────────────────────┴────────────────────┘ │
│ [Enregistrer version] [Demander validation] [Exporter ▾]                    │
└──────────────────────────────────────────────────────────────────────────────┘
```

### E-24. Assistant

Champ de question ; réponse avec **résumé**, **détails**, **Sources** (liste cliquable), **Fiabilité/fraîcheur**, **Actions suggérées** ; boutons de retour (utile / inexacte / incomplète). Les refus (évaluation de personnes, hors droits) sont expliqués avec une alternative.

### E-25. Vue stratégique

```
┌ Vue stratégique · Organisme · Exercice 2026 ─ Période [T3 ▾] ┐
│ OBJECTIFS      ▮▮▮▯ 3/4 en bonne voie    [Voir la cascade]   │
│ PORTEFEUILLE   2 initiatives critiques  Dérive moy. 11 %     │
│ DETTE          ▲ +6 % sur 6 mois  Intérêt estimé 2,1 M€/an   │
│ SÉCURITÉ       Posture 3,1/5  2 risques majeurs ouverts      │
│ RESSOURCES     Tension : Architecte, Analyste sécurité       │
│ FINANCES       Consommé 61 %  Run 68 % / Build 32 %          │
│ CONFORMITÉ     3 échéances < 90 j  1 en écart                │
│ CONTRATS       2 préavis < 90 j                              │
│ À DÉCIDER      4 décisions en attente  [Ouvrir]              │
│ Chaque tuile : valeur · tendance · fiabilité · fraîcheur · « Pourquoi ? » │
└──────────────────────────────────────────────────────────────┘
```

### E-26. Espace audit

Recommandations reçues (origine, objet, réponse, échéance, statut) ; dossier de preuve d'une décision ; journal (filtres) ; états consolidés exportables.

### E-27. Santé du référentiel

Indicateurs de couverture, fraîcheur, faits en attente, orphelins, doublons, contradictions ; files de travail (valider, fusionner, rattacher) ; qualité de l'IA (taux de corrections par type de rapport) ; bouton « Demander un rapport » sur les objets critiques sans information.

### E-28. Administration

Rubriques : Organisation · Rôles et périmètres · Référentiels (profils, types de rapports, natures de faits) · Gabarits · Seuils et règles de santé · Grille de priorisation · Politique de classification · Seuil d'agrégation · Conservation · Registre réglementaire · Instances · Sources d'alimentation · Vocabulaire · Journal des modifications. Chaque modification propose un **aperçu d'impact**.

## 5. États et messages

| État | Comportement |
|---|---|
| **Vide** | Explication + action (« Aucun rapport. Partagez le premier. ») |
| **Chargement/analyse** | Indication de progression ; possibilité de quitter ; notification à la fin |
| **Erreur** | Message clair en langage simple, cause probable, action de correction ; jamais de code technique brut |
| **Droits insuffisants** | Message neutre (« Cette information n'est pas accessible avec vos droits ») sans révéler le contenu |
| **IA indisponible** | Bandeau discret ; fonctions manuelles disponibles ; reprise automatique |
| **Données périmées** | Fraîcheur en alerte, proposition de demander un rapport |
| **Conflit de modification** | Affichage des différences et choix |
| **Hors ligne / perte de connexion** | Brouillon préservé ; message de reprise |
| **Confirmation** | Pour les actions irréversibles (retrait, rejet en lot, acceptation de risque) |

## 6. Notifications

| Événement | Destinataire | Canal par défaut | Contenu |
|---|---|---|---|
| Faits à relire | Auteur | Application + courriel | « 7 faits à relire pour votre rapport » |
| Faits à valider | Responsable de l'objet | Application | Résumé, lien |
| Demande de précision | Auteur / responsable | Application + courriel | Question + choix |
| Rapport périodique attendu | Responsable de projet | Courriel | Gabarit prérempli |
| Échéance (contrat, obligation, homologation, fin de support) | Responsables concernés | Application + courriel | Échéance + décision à prendre |
| Décision prise / bilan dû | Participants / décideur | Application | Lien décision |
| Réponse à une demande | Demandeur | Application | Statut + motif |
| Signal critique | Référent du domaine, direction | Application | Message neutre, sans contenu N4 |
| Accès/habilitation | Demandeur / habilitant | Application | Demande et décision |

Règles : regroupement (synthèse quotidienne possible), pas de contenu N3/N4 dans les courriels, langage non accusatoire, désactivation fine par type.

## 7. Parcours d'adoption (conduite du changement, vu côté produit)

- **Première semaine** : lien direct vers « Partager un rapport », exemple de rapport, vidéo/guide court (3 min).
- **Premier rapport** : félicitation sobre, explication de ce qu'il a changé.
- **Rappels** : un rappel mensuel par responsable de projet ou d'application, jamais plus d'un par semaine par personne (hors alerte critique).
- **Retours** : un bouton « Dites-nous » sur chaque écran ; traitement tracé.
- **Valeur pour le contributeur** : synthèse mensuelle de « ce qui s'est passé sur mon périmètre » générée automatiquement.
- **Transparence** : page « Ce qu'Odin fait de vos informations » (usage, droits, contacts DPO).

## 8. Accessibilité, langue, supports

- **Accessibilité** : conformité au référentiel d'accessibilité applicable aux services publics numériques de l'État (niveau à confirmer, visé : AA), pour l'application et les documents produits. Navigation clavier complète, contrastes suffisants, jamais d'information portée par la seule couleur, textes alternatifs, lecteurs d'écran, taille de texte ajustable.
- **Charte** : cohérence visuelle avec la charte graphique de l'État ou de l'organisme (à confirmer ; question ouverte Q-12).
- **Langue** : français ; vocabulaire paramétrable ; bulles d'aide ; glossaire.
- **Supports** : usage sur poste de travail en priorité ; consultation (lecture, validation simple, réponse à une précision, dépôt de rapport) sur tablette et téléphone ; l'édition lourde (roadmap, scénarios) est réservée au poste de travail.
- **Mode sobre** : pas de mise en page lourde ; tableau de bord « faible complexité » pour les utilisateurs occasionnels.
- **Performance perçue** : retour visuel immédiat sur dépôt ; analyse annoncée avec délai estimé ; aucun écran de direction ne dépasse quelques secondes d'affichage dans les conditions nominales (valeurs cibles à fixer en phase technique).
