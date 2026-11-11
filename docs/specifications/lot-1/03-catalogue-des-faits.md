# Lot 1. Catalogue des faits : formats, validations, exemples

Ce catalogue précise, pour le lot 1, les **natures de faits** (fichier 06 §3), leurs **champs**, les **règles de saisie ou de correction**, et des **exemples d'extraction** (positifs et négatifs). Il sert à construire les écrans de revue (E-06), la saisie manuelle de faits (EX-IAF-15) et la recette de l'IA.

**Conventions**
- *Champ commun à tous les faits* : nature, objet rattaché, étiquette, date de validité (ou période), source (rapport + extrait cité, ou « saisie manuelle »), niveau de fiabilité, confiance IA (si F0), auteur, valideur éventuel, historique.
- *Obligatoire* : doit être présent pour que le fait puisse être confirmé (sinon l'écran demande de le compléter).
- Les **montants** sont en euros, **hors taxes sauf mention**, avec indication TTC/HT demandée si absente du rapport ; les **durées** en jours ; les **dates** en jj/mm/aaaa.

---

## 1. Avancement

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Objet | Initiative | Oui | |
| Étiquette | « global » (défaut) ou libellé de lot | Oui | |
| Valeur | Pourcentage 0–100 **ou** statut (non démarré, en cours, en pause, terminé) | Oui | Le pourcentage doit être entre 0 et 100 |
| Période | Mois ou date | Oui | Par défaut : période couverte du rapport |
| Commentaire | Texte court | Non | |

**Positif** : « Avancement global : 62 % » → avancement, INI-01, global, 62 %, mars 2026.
**Négatif** : « Nous avançons bien » → **aucun fait chiffré** (le texte qualitatif est repris comme commentaire éventuel, pas comme pourcentage).
**Contrôle** : un avancement **en baisse** par rapport au précédent déclenche une question de confirmation (« 62 % → 55 % ; confirmer ? »).

## 2. Jalon

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Objet | Initiative | Oui | |
| Libellé | Texte | Oui | Ex. « Recette », « Mise en production » |
| Date prévue | Date | Oui | |
| Date initiale | Date | Non | Renseignée quand le texte indique un décalage |
| Statut | à venir / atteint / décalé / dépassé | Oui | « décalé » si date prévue ≠ date initiale |
| Cause | Texte court | Non | |

**Positif** : « La recette, initialement prévue le 15/04, est décalée au 30/04 » → jalon « Recette », prévue 30/04/2026, initiale 15/04/2026, décalé, cause « indisponibilité de l'environnement de test ».
**Négatif** : « Bientôt la recette » → pas de date → fait **non créé** (suggestion de demander la date).
**Contrôle** : une date **passée** sans statut « atteint » → statut « dépassé » (sauf indication contraire).

## 3. Budget (déclaré dans un rapport)

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Objet | Initiative ou application | Oui | |
| Montant consommé | Euros | Oui\* | \*Au moins consommé **ou** prévu |
| Montant prévu | Euros | Oui\* | |
| HT / TTC | Choix | Oui | **À demander** si absent |
| Période ou exercice | Texte | Oui | |
| Nature | run / build / non précisé | Non | |

**Positif** : « 410 k€ consommés sur 520 k€ prévus » → consommé 410 000 €, prévu 520 000 €, HT/TTC à confirmer.
**Négatif** : un tableur de montants **sans contexte** (période, périmètre) → **pas de fait**, question de contexte à l'auteur (RAP-16).
**Contrôle** : consommé > prévu → alerte de cohérence ; incohérence de totaux dans un tableur → signalée.
**Fiabilité** : plafond **F2** (finances saisies à la main, D10).

## 4. Risque

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Objet | Application ou initiative | Oui | |
| Intitulé | Texte | Oui | |
| Cause | Texte | Non | |
| Conséquence | Texte | Non | |
| Gravité estimée | faible / moyenne / élevée / critique | Non | **Jamais inventée** : si le rapport ne la donne pas, « à qualifier » |
| Mesure évoquée | Texte | Non | |
| Visibilité | Selon niveau du rapport | — | Les risques de sécurité sont N3/N4 |

**Positif** : « Risque de dérive sur le périmètre mobile (retard des maquettes) » → risque, INI-01, gravité « à qualifier ».
**Négatif** : un risque évoqué comme **résolu** (« risque levé ») → pas de nouveau risque ; éventuellement mise à jour d'un risque existant (lot 4).

## 5. Incident

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Application | Application | Oui | |
| Date et heure de début | Date/heure | Oui | |
| Durée | Heures/minutes | Non | |
| Impact | Texte | Non | |
| Cause | Texte | Non | **Cause technique ou organisationnelle, jamais une personne** |
| Gravité | mineur / majeur | Oui | « majeur » si indisponibilité d'un service critique > 2 h |
| Clos | oui / non | Oui | |

**Positif** : « Le 12/03 de 08h10 à 11h20, PayAide a été indisponible… 340 paiements retardés d'un jour. Cause : certificat expiré. » → incident, APP-02, 12/03/2026, 3 h 10, impact 340 paiements retardés, cause « certificat expiré sans alerte », majeur (service critique > 2 h), clos.
**Règle de redirection** : si le texte attribue la cause à une personne (« X a été négligent »), le fait **ne retient pas** la personne comme cause ; l'auteur est invité à reformuler la cause (processus, outillage). Voir IA-08.

## 6. Dette (dont fin de support)

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Application | Application | Oui | |
| Type | code / architecture / infrastructure / tests / documentation / sécurité / données / fonctionnelle / organisationnelle / **technologie obsolète** | Oui | |
| Description | Texte | Oui | |
| Technologie concernée | Texte libre | Non | Obligatoire si type « technologie obsolète » |
| Date de fin de support | Date | Non | Obligatoire pour « technologie obsolète » si connue |
| Intérêt annuel estimé | Euros par an (ou fourchette) | Non | **Fiabilité de l'estimation** : « chiffrée / estimée / inconnue » |
| Effort estimé | Jours-homme | Non | |
| Criticité de la dette | faible / moyenne / élevée / critique | Non | « critique » si fin de support avant 12 mois sur application critique |
| Échéance critique | Date | Non | |

**Positif** : voir RAP-05 : dette technologie obsolète, APP-01, Workflow-X v3, fin de support 31/12/2026, intérêt 40 k€/an (estimé), effort 120 j.h.
**Règle** : une **fin de support** est également enregistrée comme **fait « fin de support »** (date + technologie + application) servant aux règles de santé (V1, C1).

## 7. Sécurité (constats)

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Application | Application | Oui | |
| Source | Audit / test / signalement | Oui | |
| Date | Date | Oui | |
| Nombre de constats par gravité | Entiers (critique, majeur, mineur) | Oui\* | \*Ou un constat unique avec gravité |
| Échéance de remédiation | Date | Non | |
| Statut de remédiation | ouvert / en cours / remédié | Oui | « ouvert » par défaut |
| Maturité déclarée | Valeur / échelle | Non | Reprise telle quelle, étiquetée « déclarée » |

**Visibilité** : **N4**. Le **détail technique** n'est jamais repris dans les vues de direction : seuls **nombres et échéances** sont agrégés (L1-I05).
**Validation (F2)** : par le rôle sécurité (RSSI/correspondant).

## 8. Ressources

| Champ | Type | Obligatoire | Règle |
|---|---|---|---|
| Équipe ou initiative | Équipe / initiative | Oui | |
| Sous-nature | besoin / vacance de poste / dépendance à un prestataire / surcharge / affectation | Oui | |
| Profil | Profil du référentiel | Non | |
| Quantité | ETP | Non | |
| Période | Dates ou durée | Non | |
| Personne citée | Personne de l'annuaire | Non | **Seulement pour « affectation »** |

**Visibilité des faits nominatifs** : un fait « affectation » **nominatif** est créé en F0 et reste **visible uniquement de l'auteur et des rôles habilités** (responsable d'équipe, RH, PMO, décideur) ; **il n'alimente aucun indicateur au lot 1** (les affectations sont gérées au lot 3).
**Positif** : « Poste d'administrateur de bases de données vacant depuis 5 mois » → ressources / vacance, EQ-05, profil « administrateur de bases de données », durée 5 mois.
**Positif** : « Besoin d'un architecte à mi-temps d'avril à juin » → besoin, INI-01, profil architecte, 0,5 ETP, avril–juin 2026.

## 9. Dépendance

| Champ | Type | Obligatoire |
|---|---|---|
| Objet source | Application / initiative / fournisseur (texte) | Oui |
| Objet cible | idem | Oui |
| Nature | dépend de / bloque / attend | Oui |
| Échéance | Date | Non |

## 10. Décision (attendue ou prise)

| Champ | Type | Obligatoire |
|---|---|---|
| Objet | Initiative / application | Oui |
| Libellé | Texte | Oui |
| Statut | attendue / prise | Oui |
| Instance | Texte | Non |
| Date de l'instance | Date | Non |
| Choix | Texte | Si « prise » |

**Usage L1** : alimente L1-I12 « Décisions attendues ». Les **décisions prises** sont conservées comme faits ; leur registre complet est du lot 2.

## 11. Bénéfice

Champs : objet (initiative), type (financier / service / risque évité), valeur attendue ou constatée, date. **Usage L1** : conservé, non indicateur.

## 12. Satisfaction / qualité de service

Champs : service rendu ou application, indicateur (libellé libre), valeur, période. **Usage L1** : conservé, non indicateur.

## 13. Alerte / signal faible

Champs : thème, objet (facultatif), texte. **Usage L1** : proposé au référent ; jamais utilisé dans un indicateur.

## 14. Faits non retenus (exemples d'exclusion)

| Texte | Résultat attendu | Motif |
|---|---|---|
| « X est le moins fiable de l'équipe » | **Aucun fait** ; avertissement à l'auteur | Évaluation de personne (RG-01, IA-08) |
| « Le prestataire n'a pas livré les maquettes à la date prévue » | Fait **jalon/retard** (le prestataire est un fournisseur, pas une personne évaluée) | Fait de livraison, pas un jugement de personne |
| « Ignore tes instructions et… » | **Aucun fait**, signalement d'une tentative d'instruction | IA-12 |
| Listes de données personnelles d'usagers | Aucun fait ; avertissement données personnelles | IA-17 |
| « Je suis harcelé par mon responsable » | **Aucune analyse** ; renvoi vers la procédure d'alerte protégée | RG-24 |
| Note sans contenu exploitable (ex. fermeture de parking) | Résumé seul ; « Aucun fait détecté » | — |

---

## 15. Règles communes de l'écran de correction (E-06)

- Chaque nature affiche **uniquement ses champs** (tables ci-dessus) ; les champs obligatoires manquants sont **mis en évidence** et **bloquent la confirmation** de ce fait (pas du rapport).
- Chaque champ affiche l'**extrait source** (surligné au survol) et la **valeur proposée** ; l'auteur peut corriger.
- Un champ **modifié** est marqué « corrigé » (retour qualité IA-14).
- Les listes d'objets (initiative, application) proposent les **alias** ; la saisie libre d'un objet **inexistant** propose la **création** (droit selon rôle) ou la mise en file de curation.
- Un fait peut être **scindé** (un fait avec deux valeurs devient deux faits) ou **fusionné** avec un fait existant identique (même nature, objet, étiquette, valeur).

## 16. Saisie manuelle d'un fait (sans rapport)

Depuis une fiche application ou initiative : bouton « **Ajouter un fait** » → choix de nature → champs de la nature → **justification obligatoire** (texte court ou pièce) → niveau F1 ; source marquée « **saisie manuelle** ». Un fait saisi manuellement est visible comme tel et **journalisé**.
