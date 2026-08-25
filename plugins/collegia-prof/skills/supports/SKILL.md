---
name: supports
description: Produit les trois vues d'une même leçon à partir d'un contenu source unique — support distribué aux élèves, support annoté du professeur, et fiche de préparation avec la conduite de la leçon. À utiliser quand un prof veut rédiger le document qu'il distribuera en classe, son propre exemplaire corrigé, ou sa préparation de leçon.
argument-hint: <séquence ou leçon> [élève | prof | préparation]
---

# Supports de leçon

Leçon demandée : **$ARGUMENTS**

Charge les skills `methode` (traçabilité) et `charte` (mise en forme, export, rendu des marques).

## Préalable bloquant

Vérifier qu'une **matrice de référence** existe pour ce cours-année, et de préférence une
**séquence** pour la leçon concernée. Sans matrice, **ne pas produire** : renvoyer vers `matrice`.
Sans séquence, proposer de la construire d'abord — produire un support isolé, hors architecture,
c'est reproduire le travail à la leçon près que le prof veut arrêter.

## Principe : un contenu source, trois vues

Les trois documents sont dérivés du **même contenu Markdown**. C'est ce qui garantit qu'ils ne
divergent jamais : une correction sur le fond se répercute partout.

| Vue | Pour qui | Contient |
|---|---|---|
| **Support élève** | Distribué en classe | Documents, consignes, espaces de réponse, trace écrite à compléter. Marques de traçabilité **retirées**. |
| **Support prof** | Le prof en classe | Le support élève + réponses attendues, points d'attention, erreurs fréquentes. Marques **conservées**. |
| **Préparation** | Le prof avant la leçon | Objectifs, déroulement minuté, questions de relance, matériel, plan B. Marques **conservées**. |

Par défaut, produire les trois. Si le prof n'en demande qu'un, le produire et rappeler que les
autres se dérivent du même source.

## Support élève

- Consignes à l'impératif, **une tâche par consigne**, verbe d'action en gras.
- **Zone de réponse proportionnée à la réponse attendue** : c'est sa forme qui dit à l'élève
  l'ampleur de ce qu'on lui demande. Le catalogue des six formes est dans `charte`
  (`../charte/references/composants.md`) — un mot, une réponse courte, une phrase, une justification, un
  schéma, un tableau. Ne pas en inventer d'autres.
- Trace écrite explicite : ce que l'élève doit avoir dans son cahier au terme de la leçon.
- **Trois paliers de différenciation quand la tâche s'y prête** — même objectif d'apprentissage,
  étayage différent. Ils se signalent par forme, couleur **et** chiffre (jamais la couleur seule) :
  voir `charte`. Ne pas les confondre avec la progression d'une année à l'autre.
- Mise en forme : ne rien décider ici. La densité et l'accessibilité sont deux réglages de la charte,
  à choisir avec le prof en fonction de sa classe.
- Aucune marque de traçabilité visible.

## Support prof

Le support élève, plus :

- les réponses attendues, y compris les réponses partielles acceptables ;
- les erreurs fréquentes et ce qu'elles révèlent ;
- les points où la classe décroche habituellement ;
- les citations d'attendus rattachées à chaque activité.

## Préparation

- Objectifs formulés par des **verbes observables** — pas « comprendre », mais « identifier »,
  « justifier », « comparer », « produire ».
- Déroulement minuté : temps · phase · activité de l'enseignant · **activité de l'élève** · support.
  Une phase qui ne dit pas ce que fait l'élève n'est pas préparée.
- Vérifier que le minutage tient dans la durée annoncée, entrée en classe et mise au travail
  comprises.
- Prévoir une question de relance si le dispositif prend moins de temps que prévu, et ce qu'on
  coupe s'il en prend plus.

## Contenu : ce qu'il ne faut jamais fabriquer

Un support de cours contient des documents, des sources, des données, des références.

**Ne jamais inventer une citation historique, une source, une statistique, une référence de manuel
ou une date.** Quand un document est nécessaire, décrire précisément ce qui est cherché
(nature, période, angle) et le marquer `[DOCUMENT À FOURNIR]` pour que le prof le sélectionne. Une
source inventée dans un support distribué à des élèves est le pire résultat possible de ce plugin.

## Sortie

- **Support élève** : HTML/CSS à la charte, ou LaTeX si la typographie est exigeante — puis PDF
  prêt à photocopier. Ne pas proposer Word pour un document distribué : il ne porte ni les zones
  proportionnées, ni la solidarité énoncé/réponse.
- **Support prof et préparation** : même chaîne ; Word possible si le prof veut les annoter
  lui-même, en lui disant ce qui est perdu.

Vérifier avant de produire que la **solidarité question / lignes de réponse** tient à la pagination :
c'est la contrainte la plus fragile en HTML, et une question séparée de ses lignes rend le support
inutilisable. Voir `../charte/references/production.md`.

Conserver le Markdown source des trois, marques intactes.
