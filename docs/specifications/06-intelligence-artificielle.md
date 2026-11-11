# 06. L'intelligence artificielle dans Odin : comprendre et produire

Ce fichier décrit **ce que l'IA doit faire et ne pas faire du point de vue métier**. Il ne choisit ni modèle, ni hébergement, ni technique (phase ultérieure).

## 1. Rôle de l'IA

| Fonction | Description | Contrôle humain |
|---|---|---|
| **Comprendre** | Lire un rapport, en extraire des faits typés, les rattacher aux objets du SI, détecter écarts et signaux faibles, résumer | L'auteur confirme ; le responsable de l'objet valide |
| **Produire** | Rédiger des synthèses, notes de décision, rapports de direction, présentations, reformulations | L'utilisateur relit, modifie, valide avant diffusion |
| **Répondre** | Répondre aux questions en langage naturel avec sources | L'utilisateur vérifie les sources ; retour qualité |
| **Alerter** | Proposer des signaux et demandes de précision | Un humain décide de donner suite |

L'IA **n'est jamais décisionnaire** : elle ne valide aucun fait pour un indicateur de direction, ne prend aucune décision, n'évalue aucune personne.

## 2. Règles IA (IA-nn)

| ID | Règle |
|---|---|
| IA-01 | **L'IA propose, l'humain dispose.** Tout fait extrait démarre au niveau F0 (proposé). |
| IA-02 | **Chaque fait cite son extrait source** et le rapport d'origine. Un fait sans source n'existe pas. |
| IA-03 | **Aucun indicateur de direction** n'utilise un fait F0 ; les faits F1 sont affichés comme « déclaratifs » ; la référence est F2 ou F3 (RG-05). |
| IA-04 | **Chaque chiffre produit** (restitution, réponse) provient d'indicateurs ou de faits existants ; l'IA ne produit pas de chiffre libre. Si aucun chiffre n'existe, elle le dit. |
| IA-05 | **Chaque affirmation** d'une réponse ou d'un document généré est reliée à au moins une source consultable. Une affirmation non sourcée est marquée comme telle ou supprimée. |
| IA-06 | L'IA **exprime l'incertitude** : confiance par fait, mention « information insuffisante », « sources contradictoires ». Elle ne comble pas les lacunes. |
| IA-07 | L'IA **suggère** un niveau de classification (ex. contenu de sécurité → N4) ; l'auteur ou un référent **confirme**. En cas de doute, le niveau le plus protecteur est proposé. |
| IA-08 | **Aucune évaluation de personne** : l'IA ne produit ni fait, ni score, ni jugement, ni classement portant sur une personne identifiable ; les passages évaluatifs nominatifs sont **ignorés pour l'extraction** et **signalés à l'auteur** (qui peut les pseudonymiser). Les mentions de personnes sont **remplacées par leur rôle** dans les faits et dans les vues. |
| IA-09 | L'IA **ne détecte pas** et **ne suit pas** le comportement ou la productivité d'individus (volume de contributions, heures, rythme) ; les statistiques de contribution sont **agrégées** (RG-02). |
| IA-10 | **Droits d'accès respectés** : l'IA n'utilise, pour une réponse ou un document, que les contenus que l'utilisateur est autorisé à voir (RG-04). |
| IA-11 | Le **niveau de classification d'un résultat** est le plus élevé des sources utilisées. |
| IA-12 | Les contenus déposés sont **des données, jamais des instructions** : un document contenant des consignes adressées à l'IA est traité comme du contenu ; la tentative est consignée et signalée à l'administrateur. |
| IA-13 | Les **transformations** apportées par l'IA (reformulation, résumé) sont **signalées** (« généré avec l'aide de l'IA ») et **non destructives** (le texte original de l'auteur est conservé). |
| IA-14 | Les **retours utilisateurs** (rejet, correction, « inexact ») sont **conservés et mesurés** ; un fait rejeté n'est pas reproposé à l'identique. |
| IA-15 | L'**usage de l'IA est journalisé** (analyses réalisées, périmètres, versions de l'outil d'IA utilisées, corrections) et consultable par le DPO et l'auditeur (RG-22). |
| IA-16 | **Mode dégradé** : si l'IA est indisponible ou refusée, déposer, saisir, valider, décider, restituer restent possibles manuellement. |
| IA-17 | Les **données personnelles** détectées sont signalées ; l'utilisateur peut les masquer avant publication ; l'IA ne les réutilise pas pour d'autres finalités. |
| IA-18 | L'IA ne **transmet pas** à l'extérieur de l'organisme des contenus de l'organisme sans règle explicite (contrainte à instruire en phase technique : souveraineté, hébergement). |
| IA-19 | **Transparence** : chaque utilisateur peut consulter une page expliquant ce que fait l'IA, avec quelles limites, comment contester, et à qui s'adresser (DPO). |
| IA-20 | **Évaluation de la qualité** régulière (jeux de rapports de référence, taux d'erreurs par nature de fait) avant toute évolution de l'IA ; une dégradation constatée déclenche un retour à la version précédente de configuration. |
| IA-21 | Un **fait comportant des données contradictoires** n'est jamais « arbitré » par l'IA ; il est signalé et envoyé à un humain. |
| IA-22 | L'IA ne rédige **jamais seule** un texte engageant (décision, compte rendu, réponse à un contrôle) sans validation humaine tracée. |

## 3. Catalogue des natures de faits

Chaque nature indique : ce que l'IA cherche, les champs, l'objet de rattachement, le validateur.

| Nature | Ce qui est extrait | Champs principaux | Objet rattaché | Valideur (F2) |
|---|---|---|---|---|
| **Avancement** | Avancement déclaré, état d'une initiative | % ou statut, période, commentaire | Initiative | Responsable de projet |
| **Jalon** | Date prévue ou réelle, atteint, décalé | Libellé, date, écart | Initiative / jalon | Responsable de projet |
| **Risque** | Événement redouté, cause, effet, mesure évoquée | Intitulé, gravité/vraisemblance estimées, objet | Application / initiative | Responsable de l'objet ; RSSI si sécurité |
| **Incident / événement** | Panne, interruption, retour d'expérience | Date, durée, impact, cause, enseignements | Application / service rendu | Responsable d'application |
| **Dépendance** | Dépend de / bloque / attend | Objet source, objet cible, nature, échéance | Initiative / application / fournisseur | Responsables concernés |
| **Ressources** | Besoin, manque, surcharge, vacance, dépendance à un rôle ou prestataire | Profil, équipe, ETP, période (jamais de nom) | Équipe / initiative | Responsable d'équipe ; RH |
| **Budget / dépense** | Montant consommé, prévu, dépassement, demande de crédits | Montant, nature, exercice, imputation | Initiative / application | Contrôle de gestion |
| **Dette** | Dette technique ou autre, obsolescence | Type, description, intérêt, effort, échéance | Application / technologie | Responsable d'application |
| **Sécurité** | Vulnérabilité, constat d'audit, écart, homologation, exception | Gravité, objet, échéance, statut | Application | RSSI |
| **Conformité** | Obligation citée, écart, échéance | Texte, exigence, état | Obligation / application | Référent conformité / DPO |
| **Continuité** | Test, objectif de reprise, résultat | Date, résultat, objectif | Application / service rendu | Responsable d'application / RSSI |
| **Bénéfice** | Gain constaté ou attendu | Type, valeur, date | Initiative | Responsable de projet / contrôle de gestion |
| **Fournisseur / contrat** | Échéance, dépendance, difficulté, renouvellement | Fournisseur, date, montant, objet | Contrat / fournisseur | Achats |
| **Décision** | Décision évoquée ou prise | Objet, choix, date, instance | Décision | Secrétaire d'instance |
| **Demande / besoin** | Besoin exprimé de service, évolution | Service rendu, urgence, échéance | Demande | PMO |
| **Satisfaction / qualité de service** | Retour d'usage, qualité de démarche | Indicateur, valeur, période | Service rendu | Responsable du service |
| **Alerte / signal faible** | Préoccupation exprimée sans fait précis | Thème, objet | Objet | Référent du domaine |

L'administrateur peut **ajouter ou ajuster** des natures de faits sans développement (EX-ADM-01).

## 4. Comprendre : comportements attendus

### 4.1 À chaque dépôt

1. **Classer** le rapport (type, période, objets concernés).
2. **Extraire** les faits selon le catalogue (§3).
3. **Rattacher** chaque fait à l'objet le plus probable ; proposer des alternatives ; en cas d'ambiguïté, mettre en file de curation.
4. **Détecter** : données personnelles, contenus sensibles, passages évaluatifs nominatifs, consignes adressées à l'IA, doublons, informations contradictoires avec l'existant.
5. **Résumer** en 3 à 5 lignes (résumé du rapport) et générer un **résumé exécutif** optionnel.
6. **Préparer la revue** : trier les faits (contradictions, faible confiance en premier) ; proposer les **confirmations en lot** pour les faits fiables.

### 4.2 Détection d'écarts et de signaux

| Signal | Exemple | Réaction |
|---|---|---|
| Contradiction entre rapports | Deux dates de mise en production différentes | Signal + demande de précision |
| Statut déclaré incompatible avec les faits | Projet « vert » avec jalon dépassé de 30 jours, budget consommé hors tendance | Signal avant publication de la santé |
| Dérive progressive | Même difficulté signalée dans 3 rapports successifs | Signal faible au référent |
| Absence d'information | Application critique sans rapport depuis 90 jours | Signal de couverture ; demande de rapport |
| Information périmée | Fait antérieur à la durée de validité | Fait marqué à revalider |
| Écart avec source objective (F3) | Budget déclaré ≠ comptabilité | Signal ; priorité à la source objective |
| Échéance externe proche | Obligation, contrat, fin de support | Alerte |

### 4.3 Résumés multi-rapports

L'IA synthétise par objet, période ou thème en **citant** les rapports. Elle **distingue** : consensus, désaccords, éléments uniques, éléments anciens.

## 5. Produire : comportements attendus

| Production | Contenu | Règles spécifiques |
|---|---|---|
| **Résumé d'un rapport** | 3 à 5 lignes | Ne modifie pas le rapport |
| **Synthèse d'un objet** (application, projet, équipe, thème) | Situation, évolutions, points d'attention, décisions attendues | Sources citées ; fiabilité et fraîcheur |
| **Note de décision** | Décision demandée, contexte, options (dont « ne rien faire » et son coût), impacts, recommandation motivée | Recommandation **présentée comme une proposition** ; impacts issus des indicateurs et scénarios |
| **Rapport de direction** | Selon le type (fichier 09) | Chiffres issus des indicateurs ; niveau hérité |
| **Présentation** | Plan, diapositives avec titres-messages, graphiques, notes d'orateur | Titres factuels ; **chaque chiffre cliquable** vers sa source |
| **Compte rendu de comité** | Brouillon (points traités, décisions, actions) à partir des saisies | Validation du secrétaire obligatoire |
| **Narration d'un tableau de bord** | Explication en langage simple des variations | Pas d'extrapolation non sourcée |
| **Reformulation** | Rendre plus concis / plus exécutif / plus technique | Conserve les faits ; original conservé |
| **Réponse à une question** | Réponse courte, détails, sources, fiabilité | Voir ASS |

Ton et vocabulaire : l'IA adapte le registre à l'audience (direction : enjeux de service rendu, risque, coût, délai ; équipes : détails opérationnels) et évite le jargon injustifié.

## 6. Contrôles avant diffusion

Avant tout export ou partage d'un document produit avec l'IA, Odin vérifie et affiche :

1. **Niveau de classification** (hérité) vs audience.
2. **Fiabilité des chiffres** : liste des faits F0/F1 utilisés ; option de les exclure ou de les marquer.
3. **Fraîcheur** : faits plus anciens que le seuil.
4. **Informations nominatives** et sensibles détectées.
5. **Mention IA** : présente ou non selon la configuration.
6. **Validation humaine** : requise pour certains types (RG-26 pour les décisions, workflow de restitution).

## 7. Mesure de la qualité de l'IA (visible pour l'administration et les curateurs)

| Mesure | Définition | Usage |
|---|---|---|
| Taux de faits confirmés tels quels | Part des faits F0 confirmés sans correction | Mesure de pertinence |
| Taux de corrections / de rejets | Par nature de fait et par type de rapport | Cibler les améliorations |
| Taux de rattachements corrigés | Part des rattachements modifiés | Qualité du lien au référentiel |
| Taux de réponses jugées inexactes | Retours de l'assistant | Qualité des réponses |
| Délai entre dépôt et revue | Médiane | Fluidité |
| Faux positifs de détection | Signaux clos sans suite | Pertinence des signaux |
| Détections de contenu sensible manquées | Signalées par l'utilisateur ou le DPO | Sécurité |

## 8. Cas particuliers et comportements limites

| Cas | Comportement attendu |
|---|---|
| Rapport très long ou composé de plusieurs sujets | Découpe en parties thématiques proposées à l'auteur ; faits regroupés par partie |
| Rapport en langue étrangère | Traitement possible avec indication ; faits en français ; original conservé |
| Tableur avec chiffres sans contexte | L'IA demande un contexte (période, périmètre) avant de proposer des faits budgétaires |
| Rapport sans informations exploitables | Résumé seulement ; aucun fait ; indication « pas de fait détecté » |
| Rapport contenant des faits graves sur des personnes ou une infraction | Message dirigeant vers la procédure d'alerte protégée ; pas d'analyse (RG-24) |
| Documents contradictoires de niveaux de classification différents | Fait au niveau le plus élevé ; avertissement |
| Contenu possiblement classifié de défense | Rejet avec message ; avertissement tracé |
| Auteur qui conteste un fait extrait | Rejet et retour qualité ; jamais d'insistance |
| Demande de résumé d'un contenu hors droits | Refus neutre (RG-04) |
| Demande d'évaluation de personnes | Refus expliqué (RG-01) |
| IA indisponible | Dépôt sans analyse, rappel quand disponible, saisie manuelle possible |

## 9. Ce que l'IA ne fait pas

- Elle ne note, ne classe, ne surveille aucune personne.
- Elle ne tranche pas entre des faits contradictoires.
- Elle ne valide pas un fait pour un indicateur de direction.
- Elle ne prend aucune décision ni n'engage l'organisme.
- Elle n'invente aucune donnée chiffrée ni source.
- Elle ne contourne pas les droits d'accès.
- Elle ne traite pas d'informations classifiées de défense.
- Elle ne remplace pas la procédure d'alerte protégée.
