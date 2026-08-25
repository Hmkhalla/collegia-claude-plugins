---
name: planification
description: Construit la planification annuelle d'un cours — périodes réellement disponibles à partir du calendrier scolaire, répartition des attendus de la matrice, placement des évaluations certificatives avant les conseils de classe. À utiliser quand un prof planifie son année, répartit sa matière sur les périodes, ou veut savoir si son programme tient dans l'horaire.
argument-hint: <discipline> <année> [année scolaire]
---

# Planification annuelle

Cours concerné : **$ARGUMENTS**

Charge les skills `methode` (traçabilité) et `charte` (mise en forme et export).

## Préalable bloquant

Vérifier qu'une **matrice de référence** existe pour ce cours-année. Sans elle, la planification
répartit des contenus dont personne n'a vérifié qu'ils correspondent aux attendus — le pire des
documents, parce qu'il a l'air rigoureux. **Ne pas produire ; renvoyer vers `matrice`.**

## Étape 1 — Le budget de périodes réel

C'est l'étape que les planifications ratent, et celle qui produit le plus de valeur.

Partir du **calendrier scolaire réel du collège** : congés, sessions d'examens, conseils de classe,
retraites, voyages, journées pédagogiques, épreuves externes (CE1D, CE2D, CESS selon l'année).

Si le calendrier du collège n'est pas disponible, le demander. À défaut, travailler sur la structure
générique de l'année en Fédération Wallonie-Bruxelles (rentrée fin août, congé d'automne, vacances
d'hiver, congé de détente, vacances de printemps, session de juin) en **marquant explicitement
toutes les dates comme à vérifier** — ne jamais présenter des dates reconstituées comme établies.

Calculer :

```
périodes hebdomadaires × semaines effectives
− périodes perdues (congés tombant sur le jour de cours, activités, examens)
= périodes réellement disponibles
```

Confronter au volume prescrit relevé dans la matrice. **Si l'écart est négatif, le dire d'emblée** :
c'est l'information qui change les décisions du prof, et la cacher lui coûtera son année.

## Étape 2 — Répartir

- Répartir les attendus de la matrice sur les **périodes de bulletin**, pas sur les mois.
- Placer les évaluations **certificatives avant les conseils de classe** correspondants.
- Réserver explicitement des périodes de **remédiation** et de **battement** : une planification
  sans marge est fausse dès octobre. Compter au minimum une période de battement par mois.
- Respecter la progression imposée par le programme ; signaler quand un ordre est un choix du prof
  et non une contrainte.
- Si l'année relève d'un tronc commun récemment déployé, marquer les parties **nouvelles ou
  modifiées** : ce sont celles qui demanderont le plus de temps de préparation.

## Étape 3 — Produire

```
# Planification — <discipline> <année> — <année scolaire>

## Budget de périodes
Périodes hebdomadaires · semaines effectives · pertes identifiées · total disponible
Volume prescrit vs disponible — écart

## Vue d'ensemble
| Période de bulletin | Semaines | Attendus couverts | Périodes | Évaluations |

## Détail par période de bulletin
Séquences, nombre de périodes, attendus avec leurs citations, évaluations, remédiation

## Marges
Battement prévu · ce qui sautera en premier si l'année dérape

## Points de vigilance
Écarts, dates à vérifier, parties nouvelles de la réforme
```

Terminer par la ligne de traçabilité : combien d'éléments prescrits, combien de `[PROPOSITION]`,
combien de dates à vérifier.

## Sortie

La planification est un document vivant, corrigé toute l'année : Word est ici légitime, puisque c'est
le prof qui l'amende. Le dire, et proposer le rendu à la charte pour la version partagée avec
l'équipe ou la direction.
