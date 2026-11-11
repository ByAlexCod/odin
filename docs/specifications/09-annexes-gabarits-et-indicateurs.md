# 09. Annexes : gabarits de rapports, catalogue d'indicateurs, registre réglementaire initial

## 1. Gabarits de rapports (bibliothèque initiale)

Chaque gabarit : **public/auteur**, **périodicité**, **durée de validité**, **sections**, **faits attendus**. Tous sont modifiables par l'administrateur. Aucun gabarit ne comporte de champ d'évaluation de personnes.

| # | Gabarit | Auteur | Périodicité | Validité | Sections principales | Faits produits |
|---|---|---|---|---|---|---|
| G-01 | **Rapport d'avancement de projet** | Responsable de projet | Mensuelle | 45 j | Avancement, jalons, budget, difficultés/risques, ressources (par profil), décisions attendues, bénéfices | Avancement, jalon, budget, risque, ressources, bénéfice, décision |
| G-02 | **Retour d'expérience / post-mortem (sans recherche de coupable)** | Équipe / responsable d'application | À l'événement | 12 mois | Contexte, chronologie, impact, causes (systèmes et processus), ce qui a bien fonctionné, actions | Incident, dette, risque, action |
| G-03 | **Compte rendu de comité** | Secrétaire | À la séance | 12 mois | Participants (rôles), points, décisions, actions, échéances | Décision, action |
| G-04 | **Fiche de risque** | Tout contributeur / RSSI | À l'événement | 6 mois | Description, objet, cause, conséquence, gravité/vraisemblance estimées, mesures | Risque, sécurité |
| G-05 | **Fiche de dette** | Développeur / responsable d'application | À l'événement | 12 mois | Description, type, application, intérêt (coût/risque), effort, échéance critique | Dette |
| G-06 | **Rapport d'audit ou de test de sécurité (synthèse)** | RSSI / prestataire | À l'événement | 12 mois | Périmètre, méthode, constats, gravité, recommandations | Sécurité, risque |
| G-07 | **Besoin métier / demande** | Direction métier / agent | À l'événement | 6 mois | Service rendu, besoin, urgence, échéance, valeur attendue | Demande |
| G-08 | **Rapport d'activité d'équipe** | Responsable d'équipe | Trimestrielle | 90 j | Faits marquants, applications portées, charge globale (agrégée), besoins de profils, difficultés | Ressources, avancement, dette |
| G-09 | **État d'une application** | Responsable d'application | Trimestrielle | 120 j | Santé, évolutions, incidents, fin de support, dette, coûts, perspectives | Dette, incident, dépendance, budget |
| G-10 | **Bilan de projet** | Responsable de projet | À la clôture | 24 mois | Réalisé vs prévu, bénéfices constatés, coûts, enseignements | Bénéfice, budget, avancement |
| G-11 | **Note de veille** | Architecte / contributeur | Libre | 12 mois | Sujet, enjeux pour l'organisme, recommandations | Alerte, dépendance |
| G-12 | **Demande de dérogation / exception** | Responsable d'application | À l'événement | Selon durée | Règle concernée, justification, durée, mesures compensatoires | Sécurité, conformité |
| G-13 | **État des contrats et fournisseurs** | Achats | Trimestrielle | 120 j | Échéances, dépendances, difficultés | Fournisseur/contrat |
| G-14 | **Point budgétaire** | Contrôle de gestion | Mensuelle | 45 j | Consommé, prévisions, écarts, run/build | Budget |
| G-15 | **Point ressources (agrégé)** | RH du numérique | Trimestrielle | 120 j | Vacances par profil, tensions, dépendances prestataires | Ressources |
| G-16 | **Point conformité** | Référent conformité / DPO | Trimestrielle | 120 j | Textes, obligations, états, échéances | Conformité |
| G-17 | **Satisfaction et qualité de service** | Responsable de service | Trimestrielle | 120 j | Retours d'usage, indicateurs de qualité | Satisfaction |
| G-18 | **Document libre** | Tout contributeur | — | 12 mois | — | Selon extraction |

Règles d'écriture communes affichées dans l'éditeur : *décrire des faits et des situations, pas des personnes ; nommer des rôles plutôt que des noms ; signaler une source ; indiquer la période*.

## 2. Gabarits de restitutions

| # | Restitution | Audience | Contenu type | Périodicité |
|---|---|---|---|---|
| R-01 | **Résumé hebdomadaire de direction** | DNUM, direction | Faits marquants, alertes, décisions à venir (1 page) | Hebdomadaire |
| R-02 | **Tableau de bord mensuel du DNUM** | DNUM | Objectifs, portefeuille, dette, sécurité, ressources, finances, conformité | Mensuelle |
| R-03 | **Revue de portefeuille** | Comité d'investissement | Initiatives, santé, dérives, arbitrages proposés | Trimestrielle |
| R-04 | **Note de décision** | Instance | Voir fichier 06 §5 | À la demande |
| R-05 | **Point sécurité pour la direction** | Direction générale | Posture, risques majeurs, échéances, décisions | Trimestrielle |
| R-06 | **Dossier d'arbitrage budgétaire** | Direction financière / tutelle | Besoins, options, impacts, coût de l'inaction | Annuelle |
| R-07 | **Rapport d'activité annuel du numérique** | Direction, tutelle | Réalisations, indicateurs, dette, sécurité, bénéfices | Annuelle |
| R-08 | **Présentation de roadmap** | Direction, tutelle, élus | Vision, horizons, décisions, risques | Semestrielle |
| R-09 | **Dossier de passage en instance d'avis (grands projets)** | Instance d'avis | Stratégie, finances, gouvernance, réalisation, planning | À la demande |
| R-10 | **Bilan de projet** | Direction, comité | Réalisé vs prévu, bénéfices, enseignements | À la clôture |
| R-11 | **Revue des contrats** | DNUM, achats | Échéances, dépendances, décisions | Trimestrielle |
| R-12 | **Point conformité** | Direction | Textes, obligations, états, échéances | Trimestrielle |
| R-13 | **Consolidation de la dépense numérique** | Direction financière, contrôle | Dépense par programme/titre/application, run/build | Annuelle et à la demande |
| R-14 | **Suivi des recommandations de contrôle** | Direction, audit | Recommandations, réponses, échéances | Trimestrielle |
| R-15 | **Synthèse pour une équipe** | Équipe | Ce qui a changé sur son périmètre | Mensuelle |

## 3. Catalogue d'indicateurs

Principes : peu d'indicateurs, chacun relié à une **décision**. Pour chaque indicateur : définition accessible, sources de faits, fiabilité minimale, seuils **paramétrables** (valeurs proposées à confirmer). Types : **A** avancé, **R** retardé.

### 3.1 Stratégie et objectifs

| ID | Indicateur | Définition | Type | Décision éclairée |
|---|---|---|---|---|
| I-01 | Avancement des objectifs | % d'objectifs en bonne voie / à risque / en retard | R | Revoir priorités |
| I-02 | Initiatives hors stratégie | Nombre et budget des initiatives sans objectif | A | Réaffecter ou arrêter |
| I-03 | Couverture stratégique | % du budget build rattaché à un objectif | A | Alignement |

### 3.2 Portefeuille et transformation

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-10 | Santé du portefeuille | Répartition conforme/vigilance/critique (calculée) | A | Arbitrer, soutenir, arrêter |
| I-11 | Écart déclaré/calculé | Initiatives dont santé déclarée ≠ calculée | A | Détecter le « vert de façade » |
| I-12 | Dérive calendrier et budget | Écart moyen et médian vs prévisions initiales | R | Corriger gouvernance |
| I-13 | Jalons tenus | % de jalons tenus à ± N jours | A | Replanifier |
| I-14 | Délai de traitement des demandes | Médiane soumission → décision | R | Fluidifier |
| I-15 | Bénéfices réalisés | Bénéfices constatés / attendus | R | Capitaliser |
| I-16 | Coût du retard cumulé | Somme estimée du coût du report des initiatives différées | A | Arbitrer |
| I-17 | Dépendances critiques non satisfaites | Nombre et initiatives bloquées | A | Débloquer |

### 3.3 Patrimoine et dette

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-20 | Dette estimée | Somme des intérêts annuels estimés (fourchette) | A | Budget de remboursement |
| I-21 | Tendance de la dette | Variation sur 6/12 mois | A | Contrôler la dérive |
| I-22 | Part de capacité consacrée à la dette | Capacité allouée / capacité totale | A | Atteindre l'objectif |
| I-23 | Applications en fin de support | Nombre et criticité des applications avec technologie en fin de support à N mois | A | Planifier migrations |
| I-24 | Âge moyen du parc | Ancienneté pondérée par criticité | R | Rationalisation |
| I-25 | Applications orphelines | Sans responsable / sans équipe | A | Désigner |
| I-26 | Doublons fonctionnels | Services rendus servis par plusieurs applications | A | Rationaliser |

### 3.4 Ressources (agrégées, jamais nominatives)

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-30 | Taux de charge par profil | Demande / capacité | A | Recruter, redéployer, arbitrer |
| I-31 | Vacances de postes | Postes vacants et durée moyenne, par profil | R | Recruter |
| I-32 | Dépendance aux prestataires | Part de capacité externe, par profil/application | R | Internaliser, sécuriser |
| I-33 | Rôles à risque | Profils ou compétences portés par peu de personnes (sans nom) | A | Transmettre, former |
| I-34 | Consommation du plafond d'emplois | ETPT / plafond | R | Recrutement possible |
| I-35 | Part du run | Capacité de run / totale | R | Libérer des marges |

### 3.5 Finances

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-40 | Consommation budgétaire | Consommé / voté (AE, CP) | R | Réaffecter |
| I-41 | Part run / build | Répartition des dépenses | R | Transformer |
| I-42 | Coût par application / service rendu | Coût complet (agrégé) | R | Rationaliser |
| I-43 | Dépenses non imputées | % du total | A | Améliorer l'imputation |
| I-44 | Inflation des coûts logiciels/cloud | Variation annuelle des coûts de licences/abonnements | R | Négocier, sortir |
| I-45 | Dépenses d'IA | Montant et tendance | R | Maîtriser |

### 3.6 Fournisseurs et contrats

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-50 | Échéances à 180/90/30 jours | Nombre de contrats et montant | A | Préparer les décisions |
| I-51 | Concentration fournisseurs | Part de la dépense des 5 premiers fournisseurs | R | Réduire la dépendance |
| I-52 | Services critiques à fournisseur unique | Nombre | A | Plan de sortie |

### 3.7 Sécurité et continuité

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-60 | Posture de sécurité | Maturité par domaine (référentiel retenu) | R | Investir |
| I-61 | Risques majeurs ouverts | Nombre, ancienneté, acceptés vs traités | A | Traiter, accepter |
| I-62 | Applications critiques homologuées | % avec homologation valide | A | Homologuer |
| I-63 | Remédiation des constats | % remédiés dans les délais | R | Mobiliser |
| I-64 | Exceptions en cours | Nombre et échéances | A | Rattraper |
| I-65 | Tests de continuité | % d'applications critiques testées sur 12 mois | A | Tester |
| I-66 | Applications obsolètes exposées | Fin de support × criticité × exposition | A | Prioriser la dette de sécurité |

### 3.8 Conformité

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-70 | Obligations en écart | Nombre, criticité, échéance | A | Plan de conformité |
| I-71 | Échéances réglementaires à 90 jours | Nombre | A | Anticiper |
| I-72 | Textes à revérifier | Nombre de textes non vérifiés depuis N mois | A | Veille |
| I-73 | Applications soumises à des obligations d'accessibilité / numérique responsable | Part conforme | R | Corriger |

### 3.9 Service rendu et satisfaction

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-80 | Qualité des services rendus | Indicateurs de qualité de démarche (satisfaction, accessibilité, délai) | R | Améliorer |
| I-81 | Incidents sur services critiques | Nombre et durée | R | Fiabiliser |
| I-82 | Satisfaction des agents (applications internes) | Résultat d'enquêtes agrégées | R | Améliorer |

### 3.10 Contribution, fiabilité, IA (pilotage d'Odin)

| ID | Indicateur | Définition | Type | Décision |
|---|---|---|---|---|
| I-90 | Couverture | % d'applications critiques avec un rapport récent | A | Demander des rapports |
| I-91 | Fraîcheur moyenne | Âge médian des faits validés | A | Relancer |
| I-92 | Fiabilité | Répartition F0/F1/F2/F3 des faits d'un indicateur | A | Confiance |
| I-93 | Adoption | % d'agents du périmètre ayant contribué (agrégé) | A | Conduite du changement |
| I-94 | Délai de revue | Médiane dépôt → faits validés | A | Fluidifier |
| I-95 | Qualité de l'IA | Taux de faits confirmés tels quels ; taux de rejets | A | Améliorer la configuration |
| I-96 | Décisions bilanées | % de décisions avec bilan fait | R | Boucle de décision |
| I-97 | Recommandations de contrôle en retard | Nombre | A | Traiter |

Règle : tout indicateur est **supprimable** s'il ne déclenche plus aucune décision pendant deux cycles de revue.

## 4. Registre réglementaire initial proposé (à vérifier)

Liste **proposée à titre de jeu initial**, issue de la recherche ; **chaque statut doit être vérifié sur le texte officiel avant mise en service** (EX-REG-09, RG-28). Les divergences de sources relevées sont signalées.

| Texte / doctrine | Nature | Pourquoi dans Odin | Point à vérifier |
|---|---|---|---|
| Décret de gouvernance des SI de l'État (avis de l'instance interministérielle au-delà d'un seuil) | Texte | Avis obligatoire des grands projets | **Seuil : 9 ou 15 M€** (source de presse unique pour le relèvement) |
| Doctrine « cloud au centre » et dispositions législatives associées | Doctrine + loi | Choix d'hébergement, contrôle des contrats SaaS | Dates de mise à jour (mai 2023) ; décret d'application annoncé en 2026 |
| Politique de sécurité des systèmes d'information de l'État, homologation, référentiel général de sécurité | Doctrine / référentiel | Homologation, sécurité des SI | Version en vigueur ; mise à jour annoncée |
| Feuille de route cybersécurité 2026-2027 de l'État | Doctrine | Échéances (homologation des SI à enjeux, authentification forte des administrateurs) | Texte officiel non lu ; échéances rapportées |
| Directive européenne sur la cybersécurité (NIS 2) et projet de loi de transposition | Loi | Obligations de sécurité et de gouvernance | **Non promulguée au 11/11/2026** selon la recherche ; périmètre « administrations » incertain |
| Règlement européen sur l'IA et ses reports | Règlement | Registre des systèmes d'IA, niveau de risque | **Calendrier des obligations « haut risque »** (report annoncé ; adoption formelle à confirmer) |
| Règlement sur la protection des données personnelles | Règlement | Registre des traitements, AIPD | Texte non analysé dans la recherche |
| Règlement européen sur la résilience cyber des produits | Règlement | Chaîne d'approvisionnement logicielle | Dates d'application à vérifier |
| Règlement sur les données (Data Act) | Règlement | Gouvernance des données, fournisseurs | Non analysé |
| Référentiels d'accessibilité numérique | Référentiel | Applications et documents | Version applicable ; sanctions (sources divergentes) |
| Référentiel d'écoconception de services numériques | Référentiel | Numérique responsable | Valeur juridique à confirmer |
| Règles budgétaires de l'État (LOLF) | Loi organique | Imputation, programmes, plafonds d'emplois | Non analysé en détail |
| Évaluation socio-économique des investissements publics (seuil d'obligation) | Guide / circulaire | Dossier de grands projets | Seuil (20 M€ cité) |
| Dispositifs de signalement des alertes | Loi | Renvoi RG-24 | Décret d'application ; procédure de l'organisme |
| Orientations de l'État sur l'IA (plan et assistant interministériel) | Doctrine | Usage de l'IA dans Odin | Statut et accès pour l'organisme |
| Circulaires de rémunération et référentiel de métiers du numérique de l'État | Référentiel | Profils (D2) | Version en vigueur |

**Règle** : Odin affiche pour chaque ligne la date de vérification, la source et le statut ; tout texte non vérifié depuis un délai paramétrable est marqué « à revérifier ».

## 5. Référentiel de profils (D2) : structure proposée

- **Famille** (ex. conduite de projets, développement, architecture, production et exploitation, sécurité, données et IA, support, pilotage et gestion).
- **Profil** (intitulé du référentiel de l'État ou, à défaut, du référentiel de la profession).
- **Niveau** (junior, confirmé, senior, expert).
- **Statut d'emploi** (titulaire, contractuel, prestataire) pour la dépendance aux externes.
- **Compétences associées** (liste de compétences et technologies).

Le référentiel retenu (référentiel de l'État, nomenclature de la profession ou hybride) est une **question ouverte** (Q-09).

## 6. Typologie de risques et de dette (listes de départ)

**Types de dette** : code ; architecture ; infrastructure ; tests et qualité ; documentation ; sécurité ; données ; fonctionnelle (écart avec le besoin) ; organisationnelle (compétences, processus, dépendances).

**Familles de risques** : sécurité ; continuité ; conformité ; fournisseur/dépendance ; ressources et compétences ; financier ; calendrier ; image et usagers ; technologique (obsolescence) ; données et IA.
