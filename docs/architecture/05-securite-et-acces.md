# 05. Sécurité et contrôle d'accès

Priorité n°1 : **la confidentialité** (fichier 01, qualité 1). Ce fichier décrit comment les règles de droits des spécifications (RG-01 à RG-08, RG-23, RG-29, RG-32, RG-38 et les tests T-DRO, T-SEC, T-NOM) sont **garanties par construction**.

## 1. Authentification

| Sujet | Décision proposée | Justification |
|---|---|---|
| Protocole | **OpenID Connect** vers le fournisseur d'identité de l'organisme (ou SAML via un courtier d'identité) | Standard ; aucune gestion de mot de passe dans Odin |
| Comptes locaux | **Interdits en production** ; compte de secours d'administration **désactivable**, protégé et journalisé | Réduire la surface d'attaque |
| Session | Cookie de session **HttpOnly, Secure, SameSite** ; durée et inactivité paramétrables ; révocation immédiate au départ | Protection contre le vol de session |
| Authentification forte | **Déléguée** au fournisseur d'identité de l'organisme | Politique de l'organisme |
| Contributeurs externes | Comptes **créés par un administrateur**, **date de fin obligatoire** (EX-ACC-02), expiration automatique | Spécification |
| Développement local | **Fournisseur d'identité local** (profil de Compose) avec comptes de test | Ne jamais utiliser en production |
| Attribution automatique de rôles | À partir des **responsabilités du référentiel** (R03/R04 sur l'objet) et de **groupes** de l'annuaire | Spécification (lot 1 §18) |

## 2. Autorisation : un point unique, deux lignes de défense

### 2.1 Modèle

- **Principal** : l'utilisateur authentifié avec ses **rôles**, **périmètres**, **habilitations** et **délégations** actives.
- **Décision d'accès** : fonction **pure** `peut(principal, action, objet)` du module `access`, qui applique la **matrice des droits** (fichier 02 des spécifications §4), les **niveaux de classification** de l'organisme et les **règles d'héritage** (RG-04).
- **Filtres de lecture** : le module `access` fournit un **prédicat de filtre** utilisé par **toute requête de lecture** (rapports, faits, recherche, assistant, tableaux de bord) : **on ne lit que ce qui est autorisé**.
- **Données de droits dérivées** : `access.grants` (principal × objet × niveau), recalculée par événement (voir fichier 03 §6).

### 2.2 Première ligne : l'application

- Aucun accès direct aux tables depuis l'extérieur d'un module ; **tout passe par des « dépôts » (repositories) qui exigent un principal** : impossible d'écrire une lecture **sans** filtre de droits (le type du dépôt l'exige).
- **Les agrégats** (indicateurs, santé) pour les audiences sans droit nominatif sont **calculés sans exposer** de détail, et **masqués sous le seuil d'agrégation** (RG-02) par le **module des règles**.
- **Tests de propriété** : pour chaque requête de lecture, un test vérifie qu'**aucun** résultat n'appartient à un objet non autorisé pour un jeu de principaux de test (T-DRO).

### 2.3 Seconde ligne : la base de données

- **Sécurité par ligne** (RLS) activée sur les tables sensibles ; politiques exprimées sur les **droits dérivés** et le **niveau de classification** de la ligne.
- Le rôle de base utilisé par l'application **n'est pas propriétaire** des tables et **ne contourne pas** la sécurité par ligne ; un **rôle distinct** exécute les migrations.
- Chaque requête fixe le **contexte** de l'utilisateur (identifiant du principal) pour la transaction.
- **Effet** : même un **défaut du code applicatif** (filtre oublié) **ne livre pas** de ligne non autorisée. Les tests de droits vérifient **les deux lignes**.

### 2.4 Cas particuliers

| Cas | Traitement |
|---|---|
| **Contenu N4** | Ligne d'accès par habilitation nominative ; **non accessible** aux administrateurs par défaut (ET-03) ; accès journalisé (EX-AUD-01) |
| **Faits d'affectation nominatifs** | Droits restreints (responsable d'équipe, RH, PMO, décideur, personne concernée) ; **jamais** dans les agrégats larges (RG-38) |
| **Signalement discret** (RG-23) | L'**identité de l'auteur** est stockée **séparément** (table à droits restreints) ; les lecteurs voient le contenu sans l'auteur |
| **Alerte protégée** (RG-24) | Aucun traitement : le contenu reste en **brouillon privé** de l'auteur ; **non indexé**, **non envoyé** à l'IA |
| **Données personnelles masquées** | **Version masquée** stockée ; l'original reste **visible de l'auteur seul** selon politique |
| **Notifications** | Corps **neutre** : aucun contenu N3/N4 (RG-29) ; construit par du code, pas par l'IA |

## 3. Protection contre l'évaluation des personnes (D1) par construction

Les règles RG-01 et IA-08/IA-09 sont **intégrées au modèle**, pas seulement aux écrans :

1. **Aucun champ d'évaluation** n'existe dans le schéma de `persons` ni dans les faits (pas de colonne « note », « score », « classement »).
2. Les **API** n'exposent **aucun point d'accès** qui retourne un classement ou une comparaison de personnes ; une **revue de conception** et un **test automatisé de schéma d'API** le vérifient (liste blanche des routes).
3. Les **agrégats** passent par le **module des règles** qui applique le **seuil** et refuse les dimensions « personne » pour les indicateurs.
4. L'**IA** : invites d'extraction **excluant** les jugements nominatifs ; **filtre de sortie** déterministe ; **refus** des requêtes d'évaluation (§ fichier 04).
5. **Journal d'audit** : toute lecture de données nominatives de ressources est tracée.
6. **Tests bloquants** (T-NOM) dans la chaîne de livraison.

## 4. Contenus déposés : surface d'attaque principale

| Menace | Mesure |
|---|---|
| **Fichier malveillant** (macro, archive piégée, document malformé, bombe de décompression) | Contrôles de type **par contenu** ; **taille et profondeur bornées** ; **extraction dans un conteneur isolé** (réseau coupé, système de fichiers en lecture seule, ressources limitées, utilisateur non privilégié, délai maximal) ; **aucune exécution** de macro ; antivirus optionnel |
| **Injection de consignes dans un document** (IA) | Voir fichier 04 §2 : le modèle n'agit pas ; données délimitées ; détection ; validation déterministe |
| **Exfiltration par l'assistant** | Filtre de droits **avant** l'invite (fichier 04 §5) ; contrôle des références en sortie |
| **XSS** via contenu de rapport affiché | Rendu **contrôlé** : texte échappé ; aperçus de documents rendus en **conteneur isolé** ou convertis en texte ; **politique de sécurité du contenu (CSP)** stricte |
| **Téléchargement non autorisé** | Aucun accès direct au stockage ; **jetons d'accès à durée courte** après contrôle de droits |
| **Énumération d'objets** | Identifiants **non devinables** ; réponses **neutres** (RG-04) ; limitation de débit |
| **Déni de service** (dépôts massifs) | Limites de débit, de taille, de nombre ; file bornée ; analyses **dépriorisées** |
| **Falsification du journal** | Journal chaîné + droits d'ajout seul + points de contrôle exportés (§6) |
| **Compromission d'un worker** | Moindre privilège : base **par rôle**, pas d'accès aux secrets inutiles, **réseau interne cloisonné** |

## 5. Secrets, chiffrement, clés

| Sujet | Décision proposée |
|---|---|
| Secrets (base, IA, SMTP, connecteurs) | **Secrets du Compose** (fichiers montés en lecture seule) ou coffre de l'organisme ; **jamais** dans l'image ni les variables en clair ; rotation documentée |
| Transit | **TLS** au niveau du proxy ; connexions internes **cloisonnées** (réseau Compose interne) ; **mTLS** interne **optionnel** |
| Repos | Chiffrement du **support** par l'organisme ; **chiffrement d'enveloppe applicatif** **optionnel** pour N4 (clé de données par document, clé maîtresse hors base) |
| Clés | **Une clé maîtresse** fournie à l'exécution ; **rotation** prise en charge (rechiffrement progressif) |
| Mots de passe | Sans objet (OIDC) ; compte de secours : mot de passe long, stocké **condensé**, accès **journalisé** |

## 6. Journal d'audit immuable (X3)

- **Table en ajout seul** : droits `INSERT` seulement pour le rôle applicatif ; `UPDATE`/`DELETE` **révoqués** et **bloqués par déclencheur**.
- **Chaînage** : chaque entrée contient le **condensat** de l'entrée précédente et de son contenu canonique ; toute altération casse la chaîne.
- **Points de contrôle** périodiques (condensat de tête) **exportés** vers un support **hors base** (fichier signé ou système de l'organisme) ; **vérification** automatique de l'intégrité.
- **Contenu** : acteur, action, objet, avant/après (**sans contenu sensible** : identifiants et valeurs non confidentielles, ou **empreintes** pour N4), corrélation.
- **Accès** : lecture limitée aux rôles d'audit, DPO (périmètre données personnelles et IA), RSSI (sécurité), administration (limité).
- **Registre d'usage de l'IA** : métadonnées seulement (RG-22).

## 7. Données personnelles et droits des agents

- **Minimisation** : annuaire **minimal** ; aucune rémunération individuelle ; données de temps nominatives **à droits restreints** (RG-38).
- **Finalité** : planification, jamais évaluation (RG-01, ET-08).
- **Droits des personnes** (accès, rectification, retrait, information) : **outillés** dans « Mes droits » (E-34) et traités par un **circuit** responsable/DPO avec **délais** et **journal** (P-27).
- **Conservation** : politiques par type ; **effacement** tracé ; **sauvegardes** soumises au même régime (durée de rétention limitée, procédure d'expurgation après restauration).
- **Export** : l'agent peut obtenir **ses** contributions et **ses** données.
- **Registre** : Odin documente ses traitements (fichier à produire en phase de mise en service, recommandation ET-06).

## 8. Sécurité du cycle de développement et de la chaîne d'approvisionnement (principe 10)

- **Dépendances verrouillées** (fichier de verrouillage) et **miroir interne** ; **audit** automatique des vulnérabilités à chaque intégration ; **mise à jour planifiée**.
- **SBOM** généré à chaque version ; **images épinglées par condensat** ; **analyse** des images ; **signature** des images ; **registre interne**.
- **Revue de code obligatoire** ; **tests de sécurité** automatisés (analyse statique, dépendances, secrets) ; **modèle de menaces** tenu à jour (ce fichier §4 en est le point de départ).
- **Séparation des environnements** ; données de test **fictives** (jeu du fichier 05 du lot 1), jamais de données réelles en développement.
- **Journalisation sans secret** ni contenu : les journaux applicatifs **ne contiennent ni texte de rapport, ni question de l'assistant, ni donnée personnelle**.
- **Tests d'intrusion** avant la mise en service (recommandé) ; **procédure de correction** documentée.

## 9. Matrice synthétique : exigence → mécanisme

| Exigence | Mécanisme principal | Vérification |
|---|---|---|
| Aucun contenu hors droits, y compris via l'IA (RG-04, IA-10) | Filtre unique `access` + RLS + récupération filtrée avant invite | T-DRO, T-SEC, tests de propriété, tests RLS |
| N4 non administrable (ET-03) | Habilitations nominatives ; pas d'accès par défaut | T-DRO-15 |
| Non-évaluation des personnes (RG-01) | Schéma sans champ d'évaluation ; liste blanche d'API ; filtre IA | T-NOM, revue de schéma |
| Journal immuable (EX-AUD-01) | Ajout seul + chaînage + points de contrôle | T-AUD-04, vérification périodique |
| Aucune action par l'IA (IA-12) | Modèle sans outil ; validation déterministe | T-SEC-01/02 |
| Notifications neutres (RG-29) | Gabarits de code, sans contenu | T-DRO-08, T-NOT-07 |
| Alerte protégée (RG-24) | Détection + non-traitement + brouillon privé | T-DEP-10, T-SIG-03 |
| Mode dégradé (IA-16) | Découplage, file, disjoncteur | T-DEG |
