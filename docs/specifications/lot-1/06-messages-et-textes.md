# Lot 1. Messages et textes de l'interface

Textes de référence (français, ton **simple, factuel, non accusatoire**, vouvoiement). Les libellés sont **paramétrables** par l'organisme (EX-ADM-09). Les `[crochets]` sont des variables.

**Règles de rédaction**
1. Dire **ce qui s'est passé**, **pourquoi** si utile, et **ce que l'utilisateur peut faire**.
2. Jamais de code ou de jargon technique ; jamais de reproche (« vous n'avez pas… ») ; parler des **objets** et des **rôles**, pas des fautes de personnes.
3. Les messages touchant un contenu non autorisé sont **neutres** (RG-04, RG-29) : ils ne révèlent ni le contenu ni son existence détaillée.
4. Les refus **expliquent** et **proposent une alternative**.

---

## 1. Messages d'information permanents

| ID | Où | Texte |
|---|---|---|
| MSG-01 | E-01, E-34, bas d'E-02 | « Odin évalue des applications et des équipes, jamais des personnes. L'IA propose, vous décidez. » |
| MSG-02 | E-02 | « Tous les contenus sont acceptés. Qui peut les voir dépend de la visibilité choisie. [Mes droits] » |
| MSG-03 | E-05 | « Pour des faits graves concernant des personnes, utilisez la procédure d'alerte de votre organisme. [Voir la procédure] » |
| MSG-04 | Contenus générés | « Généré avec l'aide de l'IA. À relire avant diffusion. » |

## 2. Confirmations

| ID | Contexte | Texte |
|---|---|---|
| MSG-10 | Rapport partagé | « Rapport partagé. Odin l'analyse ; vous serez prévenu(e) quand les faits seront prêts à relire. » |
| MSG-11 | Brouillon enregistré | « Brouillon enregistré à [heure]. » |
| MSG-12 | Revue terminée | « Merci. [N] faits confirmés. Ils mettent à jour : [objets]. » |
| MSG-13 | Revue incomplète | « [N] faits restent à relire. Nous vous le rappellerons. Tant qu'ils ne sont pas confirmés, ils ne sont pas utilisés. » |
| MSG-14 | Signalement envoyé | « Signalement transmis à [rôle]. Vous serez informé(e) de la suite. » |
| MSG-15 | Réponse à une précision | « Merci. La précision a été prise en compte. » |
| MSG-16 | Retour qualité | « Merci pour votre retour. Il aide à améliorer l'analyse. » |
| MSG-17 | Import terminé | « Import terminé : [x] créés, [y] mis à jour, [z] rejetés. Vous pouvez l'annuler pendant 24 h. » |

## 3. États vides

| ID | Écran | Texte |
|---|---|---|
| MSG-20 | Accueil (rien à faire) | « Rien à faire pour l'instant. Merci ! » |
| MSG-21 | Mes rapports | « Aucun rapport pour le moment. Partagez le premier : glissez un document ici. » |
| MSG-22 | Fiche application sans fait | « Pas encore d'information sur cette application. [Demander un rapport] » |
| MSG-23 | Indicateur sans donnée | « Pas assez de faits pour calculer cet indicateur. [Demander un rapport] » |
| MSG-24 | Revue sans fait | « Aucun fait détecté dans ce rapport. Il reste consultable. Vous pouvez en ajouter un manuellement. » |

## 4. Avertissements (non bloquants)

| ID | Contexte | Texte |
|---|---|---|
| MSG-30 | Données personnelles détectées | « Ce document semble contenir des données personnelles (noms, dates de naissance…). Vous pouvez les masquer avant de partager. [Voir et masquer] » |
| MSG-31 | Passage évaluatif nominatif | « Un passage portait un jugement sur une personne. Odin l'a ignoré : il ne sert pas à évaluer les personnes. Vous pouvez le reformuler en décrivant les causes (processus, outils, organisation). » |
| MSG-32 | Tentative d'instruction | « Ce document contient des consignes adressées à l'IA. Elles ont été traitées comme du texte et n'ont eu aucun effet. L'administrateur en a été informé. » |
| MSG-33 | Doublon probable | « Ce rapport ressemble à « [titre] » déposé le [date]. Que souhaitez-vous faire ? [Remplacer] [Garder les deux] [Annuler] » |
| MSG-34 | Baisse d'avancement | « L'avancement passe de [x] % à [y] %. Pouvez-vous le confirmer ? » |
| MSG-35 | Contexte manquant | « Pour comprendre ces montants, il manque : période, périmètre, HT ou TTC. [Compléter] » |
| MSG-36 | Écart déclaré / calculé | « Vous avez indiqué « [déclaré] ». D'après les faits ([règle]), la situation semble « [calculé] ». Voulez-vous confirmer ou préciser ? » |
| MSG-37 | Niveau de confidentialité proposé | « Odin propose le niveau [N4] : [motif]. Vous pouvez demander une revue au référent [rôle]. » |

## 5. Messages de renvoi (alerte protégée)

| ID | Contexte | Texte |
|---|---|---|
| MSG-40 | Contenu relevant de l'alerte protégée | « Ce message concerne des faits graves. Odin n'est pas fait pour cela. Pour être protégé(e) et entendu(e), utilisez la procédure d'alerte de votre organisme : [lien]. Votre texte n'a pas été analysé ni diffusé ; vous seul(e) pouvez le voir. » |

## 6. Refus

| ID | Contexte | Texte |
|---|---|---|
| MSG-50 | Demande d'évaluation de personnes | « Odin n'évalue pas les personnes : il ne les note, ne les classe ni ne les compare. Je peux en revanche vous montrer [les incidents par application / les difficultés par projet]. » |
| MSG-51 | Hors droits | « Cette information n'est pas accessible avec vos droits. Vous pouvez en demander l'accès à [rôle]. » |
| MSG-52 | Demande de contournement | « Je ne peux pas faire cela : cela contournerait les règles de confidentialité. » |
| MSG-53 | Validation de son propre fait | « Vous ne pouvez pas valider votre propre fait. Il sera validé par [rôle]. » |
| MSG-54 | Baisse d'un niveau N4 | « Ce niveau ne peut être modifié que par [rôle]. Une revue a été demandée. » |
| MSG-55 | Seuil d'agrégation | « Cette valeur concerne moins de [seuil] personnes. Elle est présentée au niveau supérieur pour protéger les personnes concernées. » |

## 7. Erreurs

| ID | Contexte | Texte |
|---|---|---|
| MSG-60 | Format illisible | « Nous n'avons pas pu lire ce fichier. Vous pouvez coller le texte ou le convertir dans un autre format. » |
| MSG-61 | Taille dépassée | « Ce fichier dépasse [taille]. Vous pouvez le découper ou en déposer une version allégée. » |
| MSG-62 | Champ obligatoire | « [Champ] est nécessaire pour confirmer ce fait. » |
| MSG-63 | IA indisponible | « L'analyse automatique est momentanément indisponible. Votre rapport est bien enregistré ; l'analyse reprendra dès que possible. Vous pouvez aussi saisir les faits vous-même. » |
| MSG-64 | Connexion perdue | « Connexion interrompue. Votre brouillon est conservé. » |
| MSG-65 | Conflit de modification | « [Nom] a modifié ce texte en même temps. Voici les différences. » |
| MSG-66 | Date impossible | « La date de fin est antérieure à la date de début. » |

## 8. Relances et notifications (modèles)

| ID | Notification | Texte |
|---|---|---|
| MSG-70 | N-01 faits à relire | « Votre rapport « [titre] » a été analysé. [N] faits sont prêts à relire (environ [x] minutes). » |
| MSG-71 | N-03 demande de précision | « Une précision est utile sur [objet] : [question en une phrase]. [Répondre] » |
| MSG-72 | N-04 relance | « Pour mémoire : une précision attend votre réponse sur [objet]. Merci. » |
| MSG-73 | N-05 escalade | « Une précision sur [objet] est restée sans réponse. Pouvez-vous orienter vers la personne la plus à même d'y répondre ? » |
| MSG-74 | N-06 rapport attendu | « Le rapport mensuel de [objet] est attendu le [date]. Le modèle est prêt, avec les derniers éléments déjà renseignés. [Ouvrir] » |
| MSG-75 | N-09 fiche périmée | « La fiche de [application] n'a pas reçu d'information depuis [n] jours. [Demander un rapport] » |
| MSG-76 | N-07 signalement traité | « Votre signalement du [date] a été [pris en compte / converti en … / clos : motif]. Merci. » |
| MSG-77 | N-11 habilitation | « [Prénom Nom] demande l'accès au domaine [domaine]. [Accorder] [Refuser] » |
| MSG-78 | Notification pour contenu restreint | « Un élément de votre périmètre nécessite votre attention. Connectez-vous pour le consulter. » |

## 9. Libellés de boutons et de statuts

| Élément | Libellé |
|---|---|
| Bouton principal d'en-tête | **Partager un rapport** |
| Revue | ✓ Confirmer · ✎ Corriger · ✗ Rejeter · Demander à quelqu'un… · Confirmer les faits fiables ([N]) · Terminer · Je reviendrai plus tard |
| Statuts de rapport | Brouillon · Déposé · Analysé · À relire · Publié · Périmé · Remplacé · Retiré · Archivé |
| Fiabilité | Proposé · Déclaré · Validé · Vérifié |
| Santé | Conforme · Sous vigilance · Critique · Non évaluée |
| Confiance | Haute · Moyenne · Faible |
| Badges | Orpheline · Fiche périmée · En cours de clarification · Déclaratif · Généré avec l'aide de l'IA |
