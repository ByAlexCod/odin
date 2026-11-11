# Lot 1. Règles précises et calculs

Ce fichier fixe les **valeurs par défaut** et les **algorithmes métier** du lot 1. Toutes les valeurs chiffrées sont des **paramètres initiaux, modifiables par l'administrateur** (EX-ADM-03) et **à calibrer** avec de vrais rapports pendant la recette. Aucune ne préjuge de la technique.

**Date de référence des exemples et des tests** : 15/04/2026.

---

## 1. Paramètres initiaux

| Code | Paramètre | Valeur initiale | Remarque |
|---|---|---|---|
| PAR-01 | Confiance **haute** (IA) | ≥ 85 % | Calibrable ; sert au tri et aux confirmations en lot |
| PAR-02 | Confiance **moyenne** | de 60 % à moins de 85 % | |
| PAR-03 | Confiance **faible** | moins de 60 % | Jamais confirmable en lot |
| PAR-04 | Fraîcheur attendue, application **critique ou élevée** | 90 jours | |
| PAR-05 | Fraîcheur attendue, autres applications | 180 jours | |
| PAR-06 | Relance 1 d'une demande de précision | J+5 | Depuis l'envoi |
| PAR-07 | Relance 2 | J+10 | |
| PAR-08 | Escalade au responsable de l'objet (rôle) | J+15 | Tracée, non accusatoire |
| PAR-09 | Nombre maximal de relances par personne | 1 par semaine | Hors alerte critique |
| PAR-10 | Rappel d'un rapport périodique | J-3, J, J+7 | Par rapport à l'échéance du gabarit |
| PAR-11 | Délai avant publication d'un rapport non relu | 10 jours ouvrés | Publié sans faits (voir §7) |
| PAR-12 | Seuil d'agrégation | 5 (minimum 3) | RG-02 |
| PAR-13 | Taille maximale d'un dépôt | 50 Mo par fichier | À confirmer |
| PAR-14 | Similarité pour la détection de doublon | ≥ 90 % | |
| PAR-15 | Fenêtre de contradiction | 14 jours | Voir §5 |
| PAR-16 | Rapport d'application sans mise à jour : « fiche périmée » | selon PAR-04/05 | |
| PAR-17 | Durée de conservation d'un brouillon | 30 jours | |
| PAR-18 | Fin de support « proche » | moins de 12 mois | |
| PAR-19 | Fin de support « imminente » | moins de 3 mois | |

---

## 2. Gabarits : valeurs par défaut

| Gabarit | Niveau de classification proposé | Durée de validité | Périodicité attendue | Valideur du rapport « officiel » |
|---|---|---|---|---|
| G-01 Rapport d'avancement de projet | N2 | 45 jours | Mensuelle (échéance le 5 du mois suivant) | Responsable de projet |
| G-02 Retour d'expérience / post-mortem | N2 | 12 mois | À l'événement | Responsable d'application |
| G-04 Fiche de risque | N3 (visibilité restreinte au périmètre et au référent sécurité) | 6 mois | À l'événement | Référent du domaine |
| G-05 Fiche de dette | N2 | 12 mois | À l'événement | Responsable d'application |
| G-09 État d'une application | N2 | 120 jours | Trimestrielle | Responsable d'application |
| G-18 Document libre | N2 | 12 mois | — | — |
| *Types détectés hors bibliothèque L1* : synthèse d'audit ou de test de sécurité (G-06), compte rendu de comité (G-03), point budgétaire (G-14) | G-06 : **N4** ; G-03 : N2 ; G-14 : N3 | 12 mois ; 12 mois ; 45 jours | — | — |

Même si les gabarits G-03, G-06, G-14 ne sont pas dans la bibliothèque guidée du lot 1, Odin **reconnaît** ces types à l'extraction.

---

## 3. Suggestion de niveau de classification

L'IA **propose** ; l'auteur ou un référent **confirme**. Règle : en cas de doute, proposer le niveau le plus protecteur.

| Condition détectée | Niveau proposé | Motif affiché |
|---|---|---|
| Type « synthèse d'audit ou de test de sécurité » | N4 | « Contenu de sécurité » |
| Mention de vulnérabilités, d'identifiants, de configuration d'accès, d'adresses d'administration | N4 | « Éléments de sécurité sensibles » |
| Présence de données personnelles d'usagers ou d'agents (identité, date de naissance, numéro de dossier, santé…) | N3 | « Données personnelles détectées » |
| Fiche de risque (G-04) | N3 | « Fiche de risque » |
| Marquage de classification de l'organisme présent dans le document (ex. mention de diffusion restreinte) | niveau correspondant configuré | « Marquage détecté » |
| Aucun des cas ci-dessus | niveau par défaut du gabarit | — |

Règles :
- Un auteur **ne peut pas** baisser un niveau N4 proposé sans rôle habilité (A-08) : il peut seulement demander une revue.
- L'auteur peut **augmenter** le niveau (jusqu'à N3 selon ses droits) ; pour N4 il passe par le référent sécurité.
- Un niveau proposé par l'IA mais refusé par l'auteur est **consigné** (retour qualité, IA-14).

---

## 4. Cycle de vie des faits : transitions autorisées

| De | Vers | Qui peut | Condition |
|---|---|---|---|
| (création) | **Proposé (F0)** | Odin (IA) | À l'analyse d'un rapport |
| (création) | **Déclaré (F1)** | Auteur (saisie manuelle ou gabarit) | Valeur + objet + justification |
| F0 | **Déclaré (F1)** | Auteur du rapport | Action « Confirmer » (ou lot) |
| F0 | **Rejeté** | Auteur, responsable de l'objet, curateur | Motif facultatif |
| F0 / F1 | **Corrigé puis F1** | Auteur | Nouvelle valeur ; l'ancienne est conservée dans l'historique |
| F1 | **Validé (F2)** | Responsable de l'objet, curateur du domaine, rôle de validation de la nature (voir fichier 06 §3) | La personne est habilitée sur l'objet |
| F1 / F2 | **Périmé** | Odin | Date de validité dépassée (§6) ou fait remplacé |
| F1 / F2 | **Rejeté** | Responsable de l'objet, curateur | Motif obligatoire pour un fait déjà F2 |
| F2 | **Vérifié (F3)** | Odin | Lot 3 (sources objectives) : **non disponible au lot 1**, sauf alimentation par fichier explicitement déclarée « source outil » |

Règles :
- **L'auteur ne peut pas valider (F2) son propre fait** quand il est aussi le seul valideur possible ; dans ce cas la validation revient au curateur du domaine (séparation des rôles) **sauf** si l'organisme a désactivé cette règle (paramètre).
- Chaque transition est **journalisée** (qui, quand, ancienne et nouvelle valeur).
- Un fait **rejeté** n'est **pas reproposé à l'identique** pour le même rapport (IA-14).

---

## 5. Remplacement et contradiction

Un fait est identifié par **(nature, objet, étiquette)** ; l'étiquette précise (ex. jalon « Recette », avancement « global »).

**Remplacement (pas de signal)** : un fait plus récent, **du même auteur ou du même rapport périodique**, de même (nature, objet, étiquette), **remplace** l'ancien comme valeur courante ; l'ancien passe « Périmé » (historique conservé).

**Contradiction (signal + demande de précision)** : deux faits de même (nature, objet, étiquette), non périmés, de **valeurs différentes**, émis par des **auteurs différents** (ou de sources différentes) à **moins de 14 jours** d'écart (PAR-15) :
1. Odin crée un **signal** de type « contradiction » (gravité selon la nature : avancement/jalon = moyenne ; sécurité/budget = haute).
2. Odin crée une **demande de précision** adressée au responsable de l'objet (ou, à défaut, au PMO), avec choix prédéfinis (« le premier est correct », « le second est correct », « les deux, voir précision », « je ne sais pas, voir [rôle] »).
3. Tant que la contradiction est ouverte, la **valeur courante n'est pas utilisée** dans les indicateurs de direction ; l'indicateur mentionne « en cours de clarification ».
4. À la réponse : le fait retenu passe F1 (ou F2 si répondant valideur) ; l'autre passe « Rejeté » avec le motif. Le signal se ferme.

**Statut déclaré incompatible avec les faits** : si l'avancement déclaré est « conforme » mais qu'un jalon est dépassé de plus de 30 jours, Odin crée un signal « écart statut déclaré / calculé » et **demande une confirmation avant** de publier la santé déclarée.

---

## 6. Péremption

| Objet | Règle |
|---|---|
| Rapport | Passe à « Périmé » quand `date de publication + durée de validité du type` est dépassée |
| Fait lié à une **période** (ex. avancement de mars) | Périmé quand un fait plus récent le remplace, ou à la fin de la validité du rapport source |
| Fait **daté** (jalon, échéance, fin de support) | N'est pas périmé par l'écoulement du temps ; il est périmé uniquement s'il est remplacé ou rejeté |
| Fiche application | « **Périmée** » si aucun fait ou rapport n'est confirmé depuis PAR-04 (critique/élevée) ou PAR-05 (autres) |

Un rapport **périmé** reste consultable ; ses faits cessent d'alimenter les indicateurs « à jour » (RG-11).

---

## 7. Cycle d'un rapport : conditions des changements d'état

| Transition | Déclencheur | Conditions et effets |
|---|---|---|
| Brouillon → Déposé | Clic « Partager » | Type, rattachements (ou « aucun »), niveau choisis ; analyse lancée |
| Déposé → Analysé | Fin d'analyse | Faits F0 créés ; notification à l'auteur |
| Analysé → En revue | Ouverture de l'écran de revue | |
| En revue → Publié | « Terminer » par l'auteur **ou** expiration PAR-11 | Faits confirmés → F1 ; faits non traités restent F0 et ne sont **pas utilisés** ; le rapport est lisible selon son niveau |
| Publié → Périmé | Voir §6 | |
| Publié → Remplacé | Nouvelle version déposée par l'auteur | L'ancienne version reste en historique |
| * → Retiré | Auteur | Voir RG-20/21 ; les faits F2 validés par un tiers restent, avec mention « source retirée » |
| Périmé → Archivé | Règle de conservation | |

**Rapport officiel** : si le gabarit exige une validation (G-01), le rapport est « Publié » mais **non officiel** tant que le valideur n'a pas validé ; l'indicateur « avancement officiel » utilise uniquement les rapports officiels.

---

## 8. Rattachement automatique

Pour chaque rapport et chaque fait, l'IA propose des rattachements (applications, initiatives, équipes, services rendus).

- **Rattachement certain** : une seule candidate de confiance haute (nom exact ou alias connu) → rattaché, marqué « proposé » dans la revue.
- **Ambigu** : plusieurs candidates de confiance moyenne ou haute, ou une seule de confiance moyenne → le fait est mis en **file de curation** (E-27) ; il n'alimente aucun indicateur (RG-33).
- **Aucun** : le fait reste « sans objet » ; l'auteur est invité à choisir ; sinon curation.
- **Alias** : chaque objet peut avoir des **alias** (ex. « PayAide », « Paiement des aides ») gérés dans le référentiel.

---

## 9. Criticité d'une application

1. Prendre les **services rendus** servis par l'application.
2. Criticité = **la plus haute** des criticités de ces services (Critique > Élevée > Moyenne > Faible).
3. Aucun service rattaché → « **Moyenne (non déterminée)** » avec invitation à rattacher un service.
4. Le responsable peut **ajuster** la criticité avec un **motif** ; l'ajustement est tracé et visible.

---

## 10. Santé d'une application (règles par défaut)

La santé est **calculée**, jamais saisie. À chaque calcul, Odin conserve la **liste des règles et des faits** qui l'ont déclenchée (justification affichable).

**Critique** si **au moins une** condition est vraie :
- C1. Fin de support d'une technologie portée par l'application dans **moins de 3 mois** (PAR-19) **et** criticité ≥ Élevée ;
- C2. **Constat de sécurité critique** ouvert (fait de nature sécurité, gravité « critique », niveau F2) ;
- C3. **Incident majeur** (indisponibilité d'un service critique supérieure à 2 h) survenu depuis moins de 30 jours **et** non clos.

**Sous vigilance** si aucune condition Critique, et **au moins une** :
- V1. Fin de support dans **moins de 12 mois** (PAR-18) ;
- V2. Au moins **2 éléments de dette** « critique » (F1 ou plus) ;
- V3. **Aucun fait ni rapport confirmé** depuis PAR-04 / PAR-05 (fiche périmée) ;
- V4. Incident (quelle que soit la gravité) depuis moins de 30 jours ;
- V5. Application **orpheline** (sans responsable) ;
- V6. Contradiction ouverte sur un fait de l'application.

**Conforme** si aucune condition Critique ni Vigilance et au moins un fait F1+ à jour.
**Non évaluée** si aucun fait F1+ n'existe pour l'application (pas de donnée, pas de santé).

Seuls les faits **F1 ou plus** comptent ; les faits **F0 ne comptent jamais**. La condition C2 exige un fait F2.

### Exemple (jeu de données, date de référence 15/04/2026)

| Application | Faits | Santé attendue | Justification |
|---|---|---|---|
| APP-01 InstructPro | Fin de support de Workflow-X v3 au 31/12/2026 (8,5 mois) ; 1 dette critique ; criticité Critique | **Sous vigilance** | V1 (fin de support < 12 mois) |
| APP-03 PortailUsagers | 2 constats de sécurité critiques (F2) | **Critique** | C2 |
| APP-02 PayAide | Incident du 12/03 (34 jours, clos) ; rapports récents | **Conforme** | Aucune règle déclenchée |
| APP-13 ArchiveLegacy | Aucun rapport depuis 14 mois ; sans responsable | **Sous vigilance** | V3, V5 |
| APP-04 GEDoc | Aucun fait | **Non évaluée** | — |

---

## 11. Santé d'une initiative (fiche légère)

**Critique** si : un jalon est **dépassé de plus de 30 jours**, ou le budget consommé dépasse le budget prévu de **plus de 20 %**.
**Sous vigilance** si : un jalon est dépassé de **1 à 30 jours**, ou le budget consommé dépasse le prévu de **plus de 10 %**, ou une contradiction est ouverte, ou aucun rapport officiel depuis 45 jours.
**Conforme** sinon, avec au moins un fait F1+ à jour. **Non évaluée** sans fait F1+.

La **santé déclarée** (par le responsable, dans le gabarit) est affichée **à côté** ; tout **écart** (déclarée meilleure que calculée) est signalé.

---

## 12. Doublons

Deux rapports sont des **doublons probables** quand : même auteur **et** (contenu identique à ≥ 90 % **ou** même fichier) **et** périodes qui se recouvrent. Odin propose : *Remplacer la version existante* / *Garder les deux* / *Annuler*. Rien n'est supprimé sans choix de l'auteur.

---

## 13. Demande de précision : cycle

1. **Création** : signal (contradiction, écart statut, donnée manquante) ou demande manuelle (« Demander à quelqu'un »).
2. **Destinataire** : le responsable de l'objet (rôle) ; à défaut le PMO ; jamais plus de **un destinataire principal**.
3. **Relances** : PAR-06, PAR-07 ; **escalade** PAR-08 vers le responsable hiérarchique **du rôle** (formulation neutre, tracée).
4. **Clôture** : réponse, ou fait rendu obsolète (remplacé), ou annulation par l'émetteur.
5. **Traçabilité** : question, réponse, date, répondant.

---

## 14. Notifications du lot 1 : déclencheurs

| Code | Événement | Destinataire | Canal par défaut | Regroupable | Contenu |
|---|---|---|---|---|---|
| N-01 | Analyse terminée, faits à relire | Auteur | Appli + courriel | Non | « N faits à relire pour votre rapport » |
| N-02 | Faits à valider (F1 en attente de F2) | Responsable de l'objet | Appli ; courriel regroupé quotidien | Oui | Résumé et lien |
| N-03 | Demande de précision | Répondant | Appli + courriel | Non | Question + choix |
| N-04 | Relance de précision | Répondant | Appli | Non | Rappel neutre |
| N-05 | Escalade de précision | Responsable hiérarchique du rôle | Appli | Non | Message neutre, sans contenu N3/N4 |
| N-06 | Rapport périodique attendu | Responsable de l'objet | Courriel | Non | Gabarit prérempli (PAR-10) |
| N-07 | Signalement traité | Auteur du signalement | Appli | Non | Issue du signalement |
| N-08 | Application ou initiative sans responsable | PMO | Appli | Oui | Liste |
| N-09 | Fiche périmée | Responsable de l'application | Appli | Oui | Liste ; proposition de demander un rapport |
| N-10 | Rapport publié sans relecture | Auteur ; responsable | Appli | Non | Information |
| N-11 | Habilitation demandée / accordée | Demandeur / habilitant | Appli | Non | Décision |
| N-12 | Résumé hebdomadaire de direction | Décideur, lecteur | Courriel | Non | Résumé (RST-02) ; **sans contenu N3/N4** |

Règles : jamais de contenu N3/N4 dans le corps d'une notification ni d'un courriel (RG-29) ; limite de relances PAR-09 ; préférences utilisateur (EX-NOT-02) respectées sauf notifications obligatoires (N-03, N-11).

---

## 15. Indicateurs du lot 1 : définitions précises

Tous les indicateurs affichent **valeur, fiabilité (répartition F1/F2), fraîcheur, complétude**.

| ID | Indicateur | Formule | Données | Affichage |
|---|---|---|---|---|
| L1-I01 | **Santé du parc applicatif** | Nombre d'applications par état (Conforme / Sous vigilance / Critique / Non évaluée) | Santé calculée (§10) | Répartition + liste |
| L1-I02 | **Écart déclaré / calculé (initiatives)** | Nombre d'initiatives dont santé déclarée meilleure que calculée | §11 | Liste |
| L1-I03 | **Applications critiques avec fin de support proche** | Nombre d'applications de criticité Critique ou Élevée dont une fin de support < 12 mois (F1+) | Faits « fin de support » | Valeur + liste |
| L1-I04 | **Applications orphelines** | Nombre d'applications sans responsable | Référentiel | Valeur + liste |
| L1-I05 | **Constats de sécurité critiques ouverts** | Nombre de constats critiques (F2) non remédiés ; **valeur agrégée** pour les audiences sans habilitation N4 | Faits sécurité | Valeur seule pour la direction ; détail pour R07 |
| L1-I06 | **Couverture** (I-90) | (Applications critiques ou élevées avec un rapport publié depuis ≤ 90 j) / (applications critiques ou élevées) | Rapports | % + liste des manquantes |
| L1-I07 | **Fraîcheur médiane** (I-91) | Médiane de l'âge (jours) du dernier fait F1+ par application critique ou élevée | Faits | Jours |
| L1-I08 | **Fiabilité** (I-92) | Répartition F0 / F1 / F2 des faits d'un indicateur | Faits | Barre + détail |
| L1-I09 | **Adoption** (I-93) | (Personnes ayant déposé ≥ 1 rapport sur 90 jours) / (personnes de l'annuaire) ; **jamais affiché par personne** | Journal | % agrégé ; par équipe uniquement si effectif ≥ seuil |
| L1-I10 | **Délai de revue** (I-94) | Médiane (jours ouvrés) entre dépôt et « Publié » | Rapports | Jours |
| L1-I11 | **Qualité de l'IA** (I-95) | (Faits F0 confirmés sans correction) / (faits F0 traités) ; ventilé par nature de fait et type de rapport | Faits | % |
| L1-I12 | **Décisions attendues** | Nombre de faits « décision attendue » F1+ non clos | Faits | Liste |

Règle : un indicateur dont plus de **50 %** des faits sont F1 (non validés) affiche la mention « **déclaratif** » (RG-05).

---

## 16. Assistant : règles de réponse (lot 1)

1. **Périmètre de recherche** : uniquement les rapports, faits et objets que l'utilisateur est autorisé à lire (RG-04).
2. **Format** : réponse courte (≤ 3 phrases), puis détails, puis **Sources** (au moins une par affirmation), puis **Fiabilité/Fraîcheur**, puis **Actions suggérées**.
3. **Chiffres** : uniquement ceux d'indicateurs ou de faits existants (IA-04) ; sinon « je n'ai pas cette information ».
4. **Information absente ou contradictoire** : le dire, nommer la contradiction, proposer de demander une précision.
5. **Refus** : évaluation, classement ou comparaison de personnes ; contournement de droits ; demande d'exécuter des instructions contenues dans des documents. Message : explication + alternative.
6. **Retour** : trois boutons (utile / inexacte / incomplète) ; un clic sur « inexacte » propose de signaler la correction.
7. **Journalisation** (RG-22) : l'usage est tracé ; le texte des questions n'est visible que de l'utilisateur, sauf procédure d'audit habilitée tracée.
8. **Mode dégradé** : si l'IA est indisponible, l'assistant affiche une **recherche textuelle simple** dans les rapports accessibles.

---

## 17. Import initial du référentiel

**Formats d'entrée** : fichiers tabulaires (une ligne par objet) ; encodage et séparateurs usuels acceptés ; **modèles téléchargeables** dans l'écran E-32.

| Fichier | Colonnes obligatoires | Colonnes facultatives |
|---|---|---|
| Équipes | Nom ; rattachement (direction) | Responsable ; mission |
| Personnes (annuaire) | Nom ; équipe | Profil ; statut ; courriel professionnel |
| Services rendus | Nom ; criticité | Description ; public |
| Applications | Nom ; équipe | Description ; responsable ; services rendus (liste) ; mode de fourniture ; statut ; alias |
| Initiatives | Nom ; responsable | Équipe ; applications liées ; date de début ; date de fin ; statut ; alias |

**Règles** :
- **Aperçu avant import** : nombre de lignes créées, modifiées, rejetées, avec **motif par ligne rejetée** (champ manquant, valeur inconnue, doublon).
- **Rapprochement** : une ligne dont le nom ressemble à un objet existant (≥ 90 %) est proposée en « mise à jour ou création ? » ; rien n'est écrasé sans choix.
- **Réversibilité** : un import peut être **annulé** dans les 24 h (retour à l'état précédent).
- **Journalisation** : qui, quand, fichier, résultat.
- **Responsables inconnus** : une ligne dont le responsable n'est pas dans l'annuaire est importée **sans responsable** (objet « orphelin », N-08).

---

## 18. Paramètres de droits du lot 1 (cas particuliers)

- **Création du premier administrateur** : désigné à la mise en service par l'organisme ; il peut en nommer d'autres.
- **Rôle par défaut** à la première connexion : Contributeur (R01). Les autres rôles sont **attribués** par un administrateur ou automatiquement par une règle (ex. responsable d'application déclaré dans le référentiel → R03 sur cette application).
- **Rôle R03 / R04 automatique** : être désigné responsable d'une application / initiative dans le référentiel confère R03 / R04 **sur cet objet** uniquement.
- **Contributeur externe (R02)** : créé par un administrateur avec périmètre (initiatives/applications) et **date de fin obligatoire**.
- **Habilitation N4** : accordée par le rôle responsable du domaine (RSSI pour la sécurité), nominativement, avec date de fin facultative ; tracée et notifiée (N-11).
- **Délégation** : un responsable peut déléguer la validation à une autre personne pour une période ; tracée.
