---
name: intentions-pedagogiques
description: Rédige le document d'intention pédagogique d'un cours — intentions, compétences visées, dispositifs d'apprentissage, modalités et critères d'évaluation, contrat avec les élèves — ancré sur la matrice de référence et à la charte du collège. À utiliser quand un prof prépare son document d'intention pédagogique de début d'année.
argument-hint: <discipline> <année> [classe]
---

# Document d'intention pédagogique

Cours concerné : **$ARGUMENTS**

Charge les skills `methode` (traçabilité) et `charte` (mise en forme et export).

## Préalable bloquant

Vérifier qu'une **matrice de référence** existe pour ce cours-année
(`matrices/<discipline>-<annee>-<annee-scolaire>.md`).

**Si elle n'existe pas, ne pas produire le document.** Expliquer au prof qu'un document d'intention
pédagogique non ancré sur les attendus est précisément ce qu'il faut éviter, et proposer de lancer
`matrice` d'abord. C'est une quinzaine de minutes qui rendent tout le reste défendable.

Si la matrice existe, la lire et travailler **uniquement** à partir d'elle. Ne jamais retourner
interpréter le référentiel directement : la matrice est la source unique en aval.

## Structure du document

```
# Document d'intention pédagogique
<Discipline> — <année d'étude> — <année scolaire> — <professeur>

## Intentions du cours
Ce que le cours cherche à construire chez l'élève sur l'année. Quelques lignes, en propre,
pas une paraphrase du référentiel.

## Compétences et attendus visés
Repris de la matrice, avec leurs citations. C'est la colonne vertébrale du document.

## Démarches et dispositifs
Comment on travaille : types d'activités, place de la recherche, du document, de l'oral,
du travail de groupe, des outils numériques.

## Organisation de l'année
Renvoi à la planification : grandes parties et leur ordre, sans le détail du calendrier.

## Évaluation
Ce qui est évalué et comment · formatif vs certificatif · pondération journalier / examens ·
critères de réussite · modalités de remédiation et de seconde chance.

## Attentes et fonctionnement
Matériel, journal de classe, remise des travaux, absences aux évaluations, usage du numérique.

## Sources
Référentiel et programme utilisés, avec leur version.
```

## Règles de rédaction

- **Adresser le document à son lecteur réel.** Un DIP est lu par les élèves, souvent par les
  parents, parfois par la direction ou l'inspection. Vouvoyer, expliquer sans jargon, éviter les
  sigles non explicités (écrire « unité d'acquis d'apprentissage (UAA) » à la première occurrence).
- **Distinguer ce qui est prescrit de ce qui est un choix du professeur.** Les compétences visées
  viennent du référentiel ; les dispositifs et les modalités relèvent du prof. Le document est plus
  fort quand cette différence est assumée que quand tout est présenté comme imposé.
- **Rester engageant sans sur-promettre.** Ce qui est écrit ici sera opposé au prof en cours
  d'année : une modalité d'évaluation annoncée doit être tenable.
- Marques de traçabilité **conservées** dans le fichier source et rendues discrètement à l'export
  (voir `charte`).
- Une à deux pages. Un DIP de cinq pages n'est pas lu.

## Sortie

Écrire le Markdown source, puis rendre selon la charte. Un DIP circule avant d'être figé : proposer
un **artifact** pour le faire relire, puis le PDF pour la version déposée. Word seulement si le prof
veut le retoucher lui-même.
