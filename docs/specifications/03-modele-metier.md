# 03. Modèle métier : glossaire, objets, relations, cycles de vie

## 1. Glossaire

| Terme | Définition dans Odin |
|---|---|
| **Organisme** | L'organisation cliente (une seule par déploiement, décision D3). |
| **Service rendu** | Ce que l'organisme fournit à ses usagers, agents ou à sa tutelle (démarche, mission, prestation). Remplace « capacité métier ». Sert à relier les applications aux missions et à mesurer la criticité. |
| **Processus** | Enchaînement d'activités qui produit un service rendu ou le soutient. |
| **Application** | Ensemble logiciel qui rend un service fonctionnel (y compris les services SaaS utilisés). |
| **Technologie** | Produit ou composant technique (système, logiciel de base, langage, plateforme) avec un cycle de vie (support, fin de vie). |
| **Équipe** | Groupe stable de personnes qui porte une ou plusieurs applications ou activités. Unité d'évaluation et de capacité (D1). |
| **Profil** | Profil de métier du numérique (famille + intitulé de référentiel RH), utilisé pour la capacité et les compétences (D2). Ce n'est **pas** une personne. |
| **Compétence** | Savoir-faire attaché à un profil ou une technologie, avec niveau requis. |
| **Initiative** | Projet, programme, chantier ou évolution majeure inscrit au portefeuille. |
| **Demande** | Besoin exprimé (métier ou SI) avant qualification en initiative. |
| **Feuille de route (roadmap)** | Séquencement d'initiatives et de jalons sur des horizons de temps, versionné et décliné en scénarios. |
| **Élément de dette** | Écart connu entre l'état actuel et l'état attendu qui génère un coût ou un risque croissant (technique, d'architecture, de sécurité, de données, de documentation, fonctionnelle, organisationnelle). |
| **Risque** | Événement possible avec une gravité et une vraisemblance, rattaché à un objet. |
| **Objectif** | Résultat attendu (stratégique, SI, de service) avec ses indicateurs et sa cible. |
| **Rapport** | Document ou contribution déposé(e) ou rédigé(e) dans Odin : unité de contribution. |
| **Fait** | Information élémentaire extraite d'un rapport (ou saisie), typée, datée, sourcée, rattachée à un objet. Un indicateur est calculé à partir de faits. |
| **Rattachement** | Lien entre un fait ou un rapport et un objet du patrimoine (application, initiative, équipe…). |
| **Signal** | Alerte détectée automatiquement (écart, contradiction, dérive, échéance) à examiner. |
| **Décision** | Choix formalisé par une instance ou un responsable, avec options, critères, hypothèses et suites. |
| **Scénario** | Hypothèse alternative (budget, ressources, calendrier) comparée à une base de référence, sans modifier la référence. |
| **Service fait / réalisé** | Avancement constaté, par opposition à l'avancement déclaré. |
| **ETP** | Équivalent temps plein (capacité ou consommation de travail). |
| **ETPT** | Équivalent temps plein travaillé (moyenne annualisée, utilisé pour le plafond d'emplois de l'État). |
| **Run / Build** | Dépenses de fonctionnement et maintien (run) vs évolutions et projets (build / change). |
| **Fraîcheur** | Ancienneté de l'information la plus récente qui alimente un chiffre. |
| **Fiabilité** | Niveau de confiance d'un fait : déclaré, confirmé, validé, vérifié (voir §4). |

## 2. Objets métier

Chaque objet porte au minimum : identifiant, nom, description, responsable, statut de cycle de vie, dates, historique, niveau de classification (sauf les référentiels ouverts).

### 2.1 Organisation et ressources

| ID | Objet | Attributs principaux | Notes |
|---|---|---|---|
| OBJ-01 | **Organisme** | Nom, tutelle, type (ministère, direction, opérateur), exercice courant | Un seul par déploiement |
| OBJ-02 | **Direction / service** | Nom, rattachement hiérarchique, responsable | Hiérarchie d'unités |
| OBJ-03 | **Équipe** | Nom, mission, rattachement, applications portées, effectif **agrégé** par profil | Aucun lien vers des personnes affiché dans les vues de pilotage |
| OBJ-04 | **Profil** | Famille, intitulé (référentiel), niveau, statut (titulaire, contractuel, prestataire) | Référentiel interne, aligné sur un référentiel de l'État (D2) |
| OBJ-05 | **Compétence** | Libellé, domaine, technologie liée, niveau | Rareté, criticité |
| OBJ-06 | **Capacité** | Équipe × profil × période : ETP disponibles (internes, prestataires) | Calculée à partir d'hypothèses (congés, productivité) |
| OBJ-07 | **Poste vacant / besoin de recrutement** | Profil, équipe, durée de vacance, tension | Non nominatif |
| OBJ-08 | **Plafond d'emplois / schéma d'emplois** | ETPT, ETP, exercice | Contrainte, saisie par la fonction RH ou financière |

### 2.2 Patrimoine du SI

| ID | Objet | Attributs principaux |
|---|---|---|
| OBJ-10 | **Service rendu** | Nom, description, public (usagers, agents, tutelle), criticité de continuité, indicateurs de qualité |
| OBJ-11 | **Processus** | Nom, service rendu servi, propriétaire |
| OBJ-12 | **Application** | Nom, description, responsable, équipe, services rendus servis, criticité, statut de cycle de vie (en projet, en service, en sortie, retirée), utilisateurs estimés, mode de fourniture (interne, SaaS, éditeur), hébergement (information), coût annuel, date de dernière mise à jour de la fiche |
| OBJ-13 | **Technologie** | Nom, version, éditeur, dates de fin de support, applications qui l'utilisent |
| OBJ-14 | **Donnée / jeu de données** | Nom, nature (personnelle, sensible, ouverte), propriétaire, applications qui la traitent |
| OBJ-15 | **Flux / interface** | Application source, cible, nature, criticité |
| OBJ-16 | **Environnement / infrastructure (information)** | Libellé, nature, rattachement | Niveau de détail limité à la décision |

### 2.3 Stratégie et transformation

| ID | Objet | Attributs principaux |
|---|---|---|
| OBJ-20 | **Objectif** | Intitulé, niveau (stratégie de l'organisme, SI, service), échéance, cible, indicateurs, parent |
| OBJ-21 | **Indicateur** | Définition, formule, source (faits), seuils, cible, fréquence |
| OBJ-22 | **Demande** | Émetteur (service), besoin, urgence, valeur attendue, statut |
| OBJ-23 | **Initiative** | Nom, nature (projet, programme, chantier), objectifs servis, responsable, équipe(s), budget, ETP, dates, jalons, dépendances, bénéfices attendus, statut, santé |
| OBJ-24 | **Jalon** | Libellé, date prévue/réelle, initiative |
| OBJ-25 | **Dépendance** | Entre initiatives, applications, fournisseurs, échéances réglementaires, décisions |
| OBJ-26 | **Feuille de route** | Nom, périmètre, horizon, version, statut (brouillon, validée, archivée) |
| OBJ-27 | **Scénario** | Base de référence, hypothèses modifiées, résultats comparés, auteur, statut |
| OBJ-28 | **Bénéfice** | Type (financier, service, risque évité), valeur attendue, valeur constatée, date de mesure |
| OBJ-29 | **Élément de dette** | Type, application/technologie concernée, description, intérêt estimé (coût ou risque par an), effort de remboursement estimé, échéance critique, statut |

### 2.4 Finances et fournisseurs

| ID | Objet | Attributs principaux |
|---|---|---|
| OBJ-30 | **Ligne budgétaire** | Exercice, programme/action (cadre de l'État), titre de dépense, AE/CP, montant voté, montant disponible |
| OBJ-31 | **Dépense** | Montant, nature (run, build), date, imputation (application, initiative, service), origine |
| OBJ-32 | **Fournisseur** | Nom, nature (éditeur, ESN, hébergeur), dépendance (part de la dépense, criticité) |
| OBJ-33 | **Marché / contrat** | Objet, fournisseur, dates de début/fin, échéance de préavis, reconductions, montant, applications couvertes |
| OBJ-34 | **Licence / abonnement** | Produit, quantité, coût, renouvellement |

### 2.5 Sécurité, risques, conformité

| ID | Objet | Attributs principaux |
|---|---|---|
| OBJ-40 | **Risque** | Intitulé, objet concerné, gravité, vraisemblance, risque résiduel, propriétaire, traitement, acceptation (qui, quand) |
| OBJ-41 | **Mesure de sécurité / plan d'action** | Libellé, risque ou écart traité, échéance, responsable, statut |
| OBJ-42 | **Homologation / évaluation de sécurité** | Application, date, validité, décision, réserves |
| OBJ-43 | **Constat d'audit ou de test** | Source, date, gravité, application, statut de remédiation |
| OBJ-44 | **Dérogation / exception** | Règle dérogée, justification, durée, validation |
| OBJ-45 | **Plan de continuité (information)** | Application, objectifs de reprise, date du dernier test |
| OBJ-46 | **Texte / exigence réglementaire** | Référence, nature, statut juridique (en vigueur, adopté non promulgué, projet), source, date de vérification, périmètre d'application |
| OBJ-47 | **Obligation** | Texte, exigence concrète, échéance, applicabilité à l'organisme, responsable, état de conformité |
| OBJ-48 | **Doctrine / règle de l'État** | Référence, exigence, échéance | (ex. doctrine d'hébergement, feuilles de route ministérielles) |

### 2.6 Contribution, IA et décision

| ID | Objet | Attributs principaux |
|---|---|---|
| OBJ-50 | **Rapport** | Titre, type (gabarit), auteur, date, période couverte, rattachements, niveau de classification, statut, version, fichier ou contenu |
| OBJ-51 | **Fait** | Type, valeur, unité, date de validité, rapport source + extrait cité, objet rattaché, niveau de fiabilité, confiance IA, statut (proposé, confirmé, rejeté, validé, périmé), valideur |
| OBJ-52 | **Signal** | Nature (écart, contradiction, dérive, échéance proche, donnée manquante), objets concernés, gravité, statut (nouveau, examiné, clos), faits à l'origine |
| OBJ-53 | **Demande de précision** | Question posée à un auteur ou responsable, objet, statut |
| OBJ-54 | **Instance / comité** | Nom, composition (rôles), périodicité, ordre du jour type |
| OBJ-55 | **Décision** | Date, instance, objet, options, critères, hypothèses, décideur, motifs, bénéfices attendus, échéance de revue, statut, bilan |
| OBJ-56 | **Note de décision** | Décision demandée, contexte, options, impacts, recommandation, sources |
| OBJ-57 | **Recommandation de contrôle** | Origine (corps de contrôle, audit), date, objet, réponse, plan d'action, échéance, statut |
| OBJ-58 | **Restitution** | Type (rapport de direction, présentation, synthèse, export), audience, période, gabarit, version, sources, statut |
| OBJ-59 | **Gabarit** | Type de rapport ou de restitution, champs, charte, audience |

## 3. Relations principales

```
Organisme ─ a ─ Directions ─ ont ─ Équipes ─ portent ─ Applications ─ servent ─ Services rendus
   │                               │                        │
   │                               └ capacité par Profil     ├ utilisent Technologies (cycle de vie)
   │                                                         ├ traitent Données ; échangent Flux
   │                                                         ├ sont couvertes par Contrats ─ avec Fournisseurs
   │                                                         ├ ont Éléments de dette, Risques, Homologations
   │                                                         └ reçoivent Dépenses (imputées)
Objectifs ─ (cascade) ─ Initiatives ─ ont ─ Jalons, Bénéfices, Dépendances, Budget, ETP
Initiatives ─ composent ─ Feuilles de route ─ déclinées en ─ Scénarios
Demandes ─ (qualification) ─▶ Initiatives
Textes réglementaires ─ génèrent ─ Obligations ─ rattachées à ─ Applications / Initiatives / Équipes
Rapports ─ contiennent ─ Faits ─ rattachés à ─ n'importe quel objet ci-dessus ─ alimentent ─ Indicateurs
Faits ─ (écarts / contradictions) ─▶ Signaux ─▶ Demandes de précision
Décisions ─ portent sur ─ Initiatives / Applications / Risques / Contrats ─ citent ─ Faits et Rapports
Restitutions ─ composées de ─ Indicateurs, Faits, Décisions (avec sources)
```

Règles de relation clés :
- Une **application** a au moins une équipe responsable et un responsable d'application nommé (sinon elle est signalée « orpheline »).
- Une **initiative** sert au moins un objectif ou un service rendu, ou est marquée « hors stratégie » (transparence).
- Une **obligation** porte toujours sa source juridique et son **statut juridique** au jour de la dernière vérification.
- Un **fait** est toujours relié à un rapport source (ou à une saisie manuelle identifiée) ; un fait sans source n'existe pas.

## 4. Niveaux de fiabilité d'un fait

| Niveau | Nom | Signification | Utilisable pour |
|---|---|---|---|
| F0 | **Proposé** | Extrait par l'IA, non encore revu | Affichage marqué « à confirmer » ; jamais dans un indicateur de direction |
| F1 | **Déclaré** | Saisi ou confirmé par l'auteur du rapport | Vues de travail ; indicateurs avec mention « déclaratif » |
| F2 | **Validé** | Confirmé par le responsable de l'objet (application, projet…) ou un curateur | Indicateurs de direction |
| F3 | **Vérifié** | Rapproché d'une source objective (alimentation automatique, pièce justificative, comptabilité) | Indicateurs de direction avec mention « vérifié » ; sert de référence pour détecter les écarts |
| F4 | **Périmé / rejeté** | Dépassé par un fait plus récent, ou invalidé | Historique uniquement |

Un indicateur de direction affiche la **répartition de fiabilité** de ses faits sources et sa **fraîcheur** (RG-06).

## 5. Cycles de vie

### 5.1 Rapport

```
Brouillon ─▶ Déposé ─▶ Analysé ─▶ En revue (auteur) ─▶ Publié ─▶ Périmé ─▶ Archivé
                │                         │                │
                └─▶ Retiré (par l'auteur) └─▶ Corrigé      └─▶ Remplacé (nouvelle version)
```
- **Analysé** : l'IA a extrait des faits et proposé des rattachements.
- **En revue** : l'auteur confirme, corrige ou rejette les faits ; les faits confirmés passent en F1.
- **Publié** : visible selon son niveau et son périmètre ; les faits confirmés sont disponibles pour validation F2.
- **Périmé** : la période couverte est dépassée ou la durée de validité du gabarit est atteinte.
- **Retiré** : l'auteur le retire (ses faits repassent en « non utilisables » sauf si validés F2 par un tiers, avec traçabilité).
- La **suppression définitive** suit la politique de conservation (RG-20).

### 5.2 Fait

`Proposé (F0) → Déclaré (F1) → Validé (F2) → Vérifié (F3)` ; à tout moment `→ Rejeté` ou `→ Périmé`.

### 5.3 Demande → initiative

`Soumise → Qualifiée → (Complétée) → Priorisée → Arbitrée (acceptée / différée / refusée / fusionnée) → Initiative en cours → Clôturée → Bilan de bénéfices`.

### 5.4 Initiative

`Idée → Cadrage → Engagée → En cours → En pause → Terminée → Bilan réalisé` (ou `Abandonnée`).

### 5.5 Application

`En projet → En service → En décroissance → En sortie → Retirée` ; chaque changement est une décision tracée.

### 5.6 Décision

`Préparée → À décider → Décidée → En exécution → Bilan à faire → Bilan fait`. Une décision peut être **révisée** ; l'historique reste.

### 5.7 Élément de dette

`Identifié → Évalué → Priorisé → Planifié (dans une initiative) → En cours → Remboursé` (ou `Accepté` avec justification et date de revue).

### 5.8 Obligation réglementaire

`Identifiée → Applicabilité évaluée → Plan de conformité → En conformité / En écart / Non applicable (motivé)` ; avec alerte d'échéance.

### 5.9 Signal

`Nouveau → Examiné → (Demande de précision) → Clos (justifié) / Converti en risque, dette ou décision`.

## 6. Unités et conventions de mesure

- **Argent** : euros ; exercice budgétaire ; distinction AE/CP lorsque applicable ; hors taxes ou toutes taxes comprises précisé à chaque saisie.
- **Capacité** : ETP par profil et par équipe ; conversion en **ETPT** pour le suivi du plafond d'emplois, avec règle de conversion visible (RG-16).
- **Temps** : horizons *maintenant / prochainement / plus tard* pour les roadmaps ; dates précises pour les jalons et échéances.
- **Santé** (initiative, application) : trois états (conforme / sous vigilance / critique) **calculés par règles paramétrables** et justifiés (RG-08).
- **Criticité** : échelle à 4 niveaux (continuité du service rendu), déduite des services rendus servis et confirmable par le responsable.
