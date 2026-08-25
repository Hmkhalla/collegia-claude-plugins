---
name: corpus
description: Fonds documentaire embarqué du collège — référentiels FWB et programmes SeGEC, leur index, leurs conventions de découpage et d'identifiants de citation, et la procédure de mise à jour lors d'une réforme. À charger pour localiser un référentiel ou un programme, citer un attendu précisément, savoir ce que le corpus contient ou non, ou ajouter une source au fonds.
argument-hint: [discipline] [année] — ou "ajouter" / "état du corpus"
---

# Corpus de référence

Demande : **$ARGUMENTS**

Le corpus est **embarqué dans le plugin** : il arrive constitué à l'installation et se met à jour en
modifiant le dépôt git. Le prof n'a rien à télécharger ni à configurer.

## Règle de chargement

`references/INDEX.md` est le **seul fichier à lire systématiquement**. C'est une carte : une ligne
par source, avec son chemin et son état. Tout le reste se charge à la demande, et uniquement le
fragment utile.

**Ne jamais charger un référentiel entier.** Un référentiel fait des centaines de pages ; le charger
pour en extraire trois attendus sature le contexte et dégrade tout ce qui suit. Le chemin est :
INDEX → le bon fichier → la bonne section.

## Consulter le corpus

1. Lire `references/INDEX.md` et identifier la ou les sources applicables au couple
   discipline × année demandé. Déterminer le **régime** au passage (tronc commun en 1-3, programmes
   classiques en 4-6) — voir la skill `methode`.
2. Vérifier l'**état** de la source dans l'index :
   - `markdown` — le découpage sémantique existe : aller directement au fichier de section dans `md/`.
   - `pdf` — seul le PDF est disponible : le lire par plage de pages ciblée, jamais en entier.
   - `manquant` — la source n'est pas encore dans le corpus. **Le dire explicitement au prof** et
     lui proposer de la fournir. Ne jamais compenser par de la mémoire ou une reconstitution
     plausible : un attendu inventé est pire que l'absence d'attendu.
3. Citer selon les conventions de `references/conventions.md`.

## Ajouter ou mettre à jour une source

Quand le prof fournit un nouveau PDF (référentiel révisé, programme du réseau, document du collège) :

1. Le placer selon l'arborescence décrite dans `references/conventions.md` — le nommage est
   déterministe, il n'y a aucune décision à prendre.
2. **Conserver la version précédente** plutôt que l'écraser. Avec une réforme en cours, pouvoir
   comparer l'ancien et le nouveau référentiel a une vraie valeur : c'est ce qui permet de dire à un
   prof de 3e ce qui a changé pour lui.
3. Ajouter la ligne correspondante dans `references/INDEX.md` avec l'état `pdf`.
4. Le découpage markdown vient ensuite, quand le besoin s'en fait sentir sur cette source.

## Convertir un PDF en markdown découpé

Opération de mainteneur, à faire source par source, pas en masse.

- Un fichier par chapitre ou par groupe d'attendus, jamais un référentiel entier en un fichier.
- **Reprendre la numérotation du document officiel.** Ne jamais en inventer une : c'est elle qui
  rend la citation `[FWB §<id>]` vérifiable par le prof dans le document d'origine.
- Conserver le PDF source à côté du markdown dérivé. Le prof doit toujours pouvoir remonter au
  document officiel.
- Passer l'état de la ligne d'`references/INDEX.md` à `markdown` une fois le découpage terminé.

`references/_exemple-format/` montre le format attendu sur un exemple **fictif** clairement marqué,
à ne jamais citer comme une source réelle.

## État du corpus

Quand le prof demande ce que contient le corpus, répondre depuis `references/INDEX.md` en distinguant nettement
ce qui est disponible en markdown, ce qui n'est qu'en PDF, et ce qui manque. Un corpus incomplet est
un état normal du projet ; le masquer ne l'est pas.
