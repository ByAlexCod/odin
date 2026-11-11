# 01. Contraintes, qualités attendues et principes

Ce fichier dérive les **exigences d'architecture** des spécifications métier et des réponses du commanditaire. Chaque décision des fichiers suivants s'y rattache.

## 1. Contraintes données par le commanditaire

| # | Contrainte | Origine |
|---|---|---|
| K1 | **Front en Vue.js** | Réponse du 11/11/2026 |
| K2 | **Back en TypeScript, sans NestJS** (jugé trop lourd) | Idem |
| K3 | **Tout doit fonctionner avec un Docker Compose**, à l'exception du serveur de modèle de langue | Idem |
| K4 | **Service IA interne déjà fourni** (API de l'organisme ou de l'État) ; Odin le consomme, il ne l'héberge pas | Idem |
| K5 | **Équipe moyenne (6 à 15 personnes) avec une équipe de plateforme / exploitation** | Idem |
| K6 | **Auto-hébergé** chez chaque organisme ; contenus et traitements restent dans son infrastructure | D6 |
| K7 | **Environnement exact de l'organisme inconnu** (Kubernetes, VM, réseau isolé ?) : la solution doit rester **portable** | Idem |
| K8 | **~300 personnes** ; une instance = un organisme (pas de multi-organismes) | D3, D9 |
| K9 | **Sources identifiées** : Jira, imputation des temps, finances saisies à la main | D10 |

## 2. Exigences issues des spécifications

| # | Exigence | Source | Conséquence architecturale |
|---|---|---|---|
| X1 | **Cloisonnement strict** des contenus (N1 à N4, périmètres, habilitations) y compris vis-à-vis de l'IA | RG-04, IA-10/11, T-DRO, T-SEC | Contrôle d'accès **centralisé et testable**, appliqué **avant** toute récupération de contenu pour l'IA (jamais après) |
| X2 | **Traçabilité de bout en bout** : tout chiffre → faits → rapports → auteurs → valideurs | EX-AUD-04, RG-07 | Modèle de faits **historisé** ; liens de provenance **intègres** ; photo des données reproductible |
| X3 | **Journal immuable** (qui, quand, avant/après) | EX-AUD-01, T-AUD-04 | Journal **append-only**, chaîné, non modifiable par l'application |
| X4 | **Reproductibilité** d'une restitution ou d'une décision à une date donnée | ET-18/19 | Données **temporelles** ; paramètres **versionnés** ; calculs **déterministes** |
| X5 | **L'IA propose, l'humain dispose** ; aucun effet de bord déclenché par l'IA | IA-01, IA-12, T-SEC | Le modèle de langue n'a **aucun droit d'écriture** ni outil à effet de bord ; il renvoie des **propositions** validées par du code déterministe |
| X6 | **Mode dégradé sans IA** : tout parcours essentiel reste possible | IA-16, T-DEG | **Découplage** IA / cœur ; file d'attente tolérante aux pannes ; états « en attente » |
| X7 | **Analyse asynchrone** (minutes) avec retour de progression | ET-15, E-02 | Traitements en **tâches de fond** ; notification de l'avancement |
| X8 | **Règles et seuils en données**, modifiables sans développement, avec aperçu d'impact | EX-ADM-03/04 | Moteur de règles **paramétré par des jeux de paramètres versionnés** ; calcul « à blanc » (simulation) |
| X9 | **Recherche** texte intégral en français + recherche sémantique pour l'assistant | EX-RAP-10, EX-ASS | Index de texte et de **vecteurs** respectant les droits |
| X10 | **Sources de qualité inégale** : import de fichiers, Jira, temps | EX-ALI | **Couche d'alimentation** avec zone d'accueil, rapprochement, contrôles |
| X11 | **Accessibilité** et charte configurables | ET-11/12 | Composants accessibles ; thème paramétrable par l'organisme |
| X12 | **Réversibilité** : export intégral en formats ouverts | ET-20 | Modèle de données documenté ; export complet testé |
| X13 | **Opérable avec peu d'effort** par l'organisme | ET-27 | Peu de composants ; observabilité et sauvegarde **fournies** |
| X14 | **Tolérance au réseau isolé** (inconnu) | K7 | **Aucun appel externe à l'exécution** ; dépendances et modèles mis à disposition en interne |

## 3. Qualités attendues (par priorité)

| Rang | Qualité | Cible indicative | Commentaire |
|---|---|---|---|
| 1 | **Confidentialité** | 0 incident ; aucun contenu non autorisé jamais retourné, y compris via l'IA | Exigence absolue ; prime sur la performance |
| 2 | **Intégrité et traçabilité** | 100 % des chiffres explicables jusqu'aux sources | |
| 3 | **Simplicité d'exploitation** | Démarrage, mise à jour et restauration documentés, réalisables par une équipe plateforme sans expert Odin | Guide la minimisation des composants |
| 4 | **Maintenabilité et évolutivité** | Ajout d'un module sans toucher aux autres ; lots 2 à 6 sans refonte | Modularité stricte |
| 5 | **Résilience** | Pannes de l'IA et d'alimentations **sans perte** ; RPO ≤ 24 h, RTO ≤ 4 h (à confirmer, ET-17) | |
| 6 | **Performance perçue** | Écrans < 2 s ; confirmation de dépôt immédiate ; analyse en quelques minutes | Le débit est limité par le **service IA**, pas par Odin |
| 7 | **Accessibilité** | Niveau choisi par l'organisme (visée AA) | |

**Dimensionnement de référence** (hypothèses, à confirmer) : 300 utilisateurs, ≤ 100 simultanés ; ~50 à 200 rapports déposés par jour en régime établi ; documents ≤ 50 Mo ; ~100 000 faits au bout de 3 ans ; ~1 To de documents au maximum sur 5 ans. **Ces volumes sont modestes** : ils n'exigent ni cluster de données, ni bus de messages distribué, ni séparation en microservices.

## 4. Principes d'architecture

1. **Le plus simple qui tienne** : un cœur unique, une base de données, peu de composants. Toute pièce supplémentaire doit **justifier sa valeur** par une exigence (ADR).
2. **Modularité d'abord, distribution ensuite** : fronts internes stricts (modules) permettant d'extraire un service **plus tard** si nécessaire ; jamais l'inverse.
3. **Le contrôle d'accès est une fonction du noyau, pas une option** : un **point unique** décide et filtre ; les couches basses (base de données) **doublent** la protection.
4. **L'IA est un composant remplaçable derrière un port** : contrat d'interface stable ; modèles, versions et fournisseurs interchangeables ; **jamais** de logique métier dans les invites.
5. **Les propositions de l'IA sont des données non fiables** jusqu'à validation : schéma strict, preuves (extrait source vérifié), seuils de confiance, revue humaine.
6. **Les règles sont des données, les calculs sont des fonctions pures** : reproductibles, testables, explicables.
7. **Historique plutôt qu'écrasement** : on ajoute, on remplace logiquement, on n'efface pas (sous réserve des règles de conservation et de retrait).
8. **Événements sans contenu sensible** : un événement porte des **identifiants**, pas des contenus ; chaque consommateur relit **sous contrôle d'accès**.
9. **Portabilité** : images de conteneurs standard, configuration par variables, aucune dépendance à un service propriétaire de cloud.
10. **Sécurité de la chaîne d'approvisionnement** : dépendances verrouillées, miroir interne, SBOM, images épinglées, pas de téléchargement à l'exécution.
11. **Testabilité des exigences critiques** : les tests de droits, de non-évaluation des personnes et de qualité IA sont **automatisés** et **bloquants** (voir fichier 07).
