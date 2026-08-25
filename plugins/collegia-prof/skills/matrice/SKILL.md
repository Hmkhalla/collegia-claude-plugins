---
name: matrice
description: Produit la matrice de référence d'un cours-année — les attendus du référentiel FWB et du programme SeGEC applicables, extraits du corpus et cités, avec le volume horaire réel, la progression imposée et les points de vigilance de la réforme. C'est le premier travail à faire pour un cours, avant toute préparation. À utiliser quand un prof commence à travailler sur un cours, demande ce que le programme attend de lui, ou veut cadrer son année.
argument-hint: <discipline> <année> [orientation]
---

# Matrice de référence d'un cours-année

Cours concerné : **$ARGUMENTS**

Charge la skill `methode` (hiérarchie FWB ↔ SeGEC, régimes, traçabilité) et la skill `corpus`
(localisation et citation des sources).

C'est la skill qui matérialise la règle **analyser avant de proposer**. Elle ne produit aucun
contenu de cours : elle produit le cadre auquel tout le reste devra se conformer. Toutes les autres
skills de production la lisent.

## Étape 1 — Cadrer

Établir, en demandant ce qui manque :

- **discipline**, **année d'étude**, **orientation** (transition / qualification, forme) ;
- **régime applicable**, déduit de l'année : tronc commun en 1-3, programmes classiques en 4-6 ;
- **volume horaire hebdomadaire** (nombre de périodes de 50 min) ;
- s'il s'agit d'une **reprise** (le prof a déjà donné ce cours) ou d'une **création**.

Ne pas deviner l'orientation ni le volume horaire : ils changent les attendus applicables.

## Étape 2 — Localiser les sources, sans les interpréter encore

Via `corpus` : identifier le référentiel FWB et le programme SeGEC applicables. Vérifier leur état
dans l'INDEX.

**Si le référentiel manque, s'arrêter là et le dire.** Il est la source bloquante : sans attendus,
il n'y a rien à quoi se conformer. Ne jamais produire une matrice « de mémoire » — elle
contaminerait tout ce qui en découle.

**Si seul le programme SeGEC manque, continuer.** C'est une source complétante (voir `methode`) : la
matrice se construit sur les attendus prescrits, et signale que la déclinaison du réseau n'est pas
disponible. C'est l'état normal du corpus aujourd'hui, pas une anomalie à contourner.

Annoncer explicitement au prof sur quoi la matrice va être construite :
« Compétences terminales histoire, 2e et 3e degrés (1999, PDF). Programme SeGEC non disponible :
la progression proposée sera à valider. »

## Étape 3 — Extraire et citer

Parcourir les sources et extraire, **sans reformuler** :

- les **attendus** (tronc commun) ou les **UAA avec leurs processus** Connaître / Appliquer /
  Transférer (régime classique), chacun avec son identifiant officiel ;
- les **savoirs et savoir-faire** associés ;
- la **progression imposée** par le programme, et ce qu'il laisse au choix du prof — cette
  distinction est celle qui libère le plus de temps pour lui ;
- les **modalités d'évaluation** prescrites (certificative, épreuve externe, qualification) ;
- les **volumes ou proportions** indiqués par le programme, s'il y en a.

Chaque ligne porte sa citation. Une extraction sans identifiant n'a aucune valeur.

## Étape 4 — Confronter au réel

- Comparer le volume prescrit au volume réellement disponible (périodes hebdomadaires × semaines
  effectives). Signaler l'écart s'il y en a un : c'est l'information la plus utile de la matrice.
- Si le prof reprend un cours existant, marquer ce qui **change par rapport à sa préparation
  précédente**. C'est décisif pour une année qui vient de basculer dans le tronc commun, où les
  préparations antérieures ne sont plus alignées (voir `methode`, état du déploiement).
- Relever les tensions entre référentiel et programme, sans les arbitrer.

## Étape 5 — Produire la matrice

Écrire un fichier `matrices/<discipline>-<annee>-<annee-scolaire>.md` dans le dossier de travail du
prof (par exemple `matrices/histoire-3e-2026-2027.md`), avec cette structure :

```
# Matrice de référence — <discipline> <année> — <année scolaire>

## Cadre
Régime · orientation · volume horaire · sources utilisées avec leur version

## Attendus / UAA
| Identifiant | Intitulé (transcrit) | Niveau | Source |
Une ligne par attendu, citation obligatoire.

## Savoirs et savoir-faire associés

## Progression
Ce que le programme impose · ce qu'il laisse libre

## Évaluation prescrite

## Volume
Prescrit vs disponible · écart constaté

## Ce qui change
Pour une reprise ; décisif si l'année vient de basculer dans le tronc commun

## Points ouverts
Ce qui reste à trancher par le prof, et ce qui manque au corpus — dont l'absence éventuelle du
programme SeGEC et ce qu'elle laisse ouvert
```

Terminer par le décompte de traçabilité : nombre d'éléments prescrits, nombre de `[PROPOSITION]`,
nombre de références à vérifier.

## Étape 6 — Faire valider

**Présenter la matrice au prof pour validation avant qu'elle serve.** C'est lui l'expert : il repère
en une lecture un attendu mal rattaché. Une matrice validée devient la base de tout le reste ; une
matrice non validée propage silencieusement ses erreurs dans le DIP, la planification et les
supports.
