---
name: methode
description: Doctrine de travail du plugin — hiérarchie entre référentiels FWB et programmes SeGEC, régimes en vigueur (tronc commun en 1-3, programmes classiques en 4-6), règle « analyser avant de proposer », convention de traçabilité vérifié/proposé. Base de connaissances chargée par toutes les autres skills du plugin ; à charger aussi dès qu'il est question de conformité au programme, de citation d'un attendu, ou de ce qui est prescrit par rapport à ce qui est proposé.
---

# Méthode de travail

Cette skill ne produit aucun document. Elle fixe les règles auxquelles toutes les autres se
conforment. Elle s'applique dès qu'un document destiné à un élève, à un collègue ou à la direction
est en jeu.

## 1. Analyser avant de proposer

**Aucune production de contenu de cours n'est autorisée tant que les attendus applicables n'ont pas
été extraits, cités et validés par le prof.** L'ordre est :

```
lire le corpus  →  extraire et citer les attendus  →  faire valider  →  proposer
```

Jamais l'inverse. Générer une séquence puis vérifier après coup qu'elle « colle au programme » est
explicitement interdit : ça produit des documents plausibles mais non ancrés, et ça reporte sur le
prof le travail de contrôle qu'il cherche justement à ne plus faire.

Concrètement, une skill de production commence par vérifier qu'une **matrice de référence** existe
pour le cours-année concerné (voir la skill `matrice`). Si elle est absente, elle **refuse de
produire** et renvoie vers `matrice`. Ce n'est pas une politesse : c'est le garde-fou principal.

## 2. Traçabilité — distinguer le vérifié du proposé

Toute affirmation d'un document produit porte l'une de ces marques :

| Marque | Signification | Origine |
|---|---|---|
| `[FWB §<id>]` | Attendu prescrit par le référentiel | Corpus, identifiant officiel |
| `[SeGEC p.<n>]` | Élément du programme du réseau libre | Corpus, page du programme |
| `[COLLÈGE]` | Règle propre au collège | Charte, calendrier, décision d'équipe |
| `[PROPOSITION]` | Proposition pédagogique assumée | Aucune source — c'est un choix |

Trois règles absolues :

- **Ne jamais inventer une référence.** Un identifiant d'attendu se reprend du document officiel ;
  il ne se fabrique pas. En cas de doute sur un numéro, écrire `[FWB — référence à vérifier]` plutôt
  qu'un numéro plausible.
- **Ne jamais laisser un élément non marqué.** Ce qui n'est rattachable à aucune source est
  `[PROPOSITION]`. C'est une position honorable, pas un aveu de faiblesse.
- **Ne jamais présenter une proposition comme prescrite.** C'est la seule erreur qui coûte vraiment
  au prof : elle lui fait défendre devant un inspecteur ou un collègue un choix qui n'engage que le
  plugin.

Quand un document contient beaucoup de propositions, le dire en tête plutôt que de le diluer :
« Ce document contient N éléments prescrits et M propositions pédagogiques, signalées comme telles. »

## 3. Hiérarchie référentiel FWB ↔ programme SeGEC

Les deux sources ne sont pas au même niveau et ne servent pas au même usage :

- Le **référentiel FWB** dit *ce qui doit être atteint*. Il est prescrit par la Fédération
  Wallonie-Bruxelles et s'impose à tous les réseaux. C'est la référence pour la certification.
- Le **programme SeGEC** dit *comment le réseau libre décline ces attendus* : progression, contenus,
  démarches, découpage horaire. C'est le document de travail quotidien d'un professeur du collège.

**En cas de divergence apparente**, l'ordre est : le référentiel fixe le niveau d'exigence, le
programme fixe la mise en œuvre. Un programme ne peut pas retirer un attendu du référentiel ; il
peut en revanche l'ordonner, le contextualiser et aller au-delà. Toute divergence réelle constatée
entre les deux doit être **signalée au prof**, jamais arbitrée en silence.

Un attendu cité dans un document produit se cite depuis le **référentiel**. La progression et le
découpage se citent depuis le **programme**.

## 4. Les deux régimes

Deux régimes cohabitent dans le même établissement. **Le régime se déduit de l'année d'étude**, et
se détermine avant toute analyse.

| Année d'étude | Régime | Vocabulaire |
|---|---|---|
| Tronc commun | Référentiels du tronc commun (Pacte pour un Enseignement d'excellence) | **attendus**, par visée et thématique |
| Au-delà du tronc commun | Programmes classiques | **UAA**, avec processus Connaître / Appliquer / Transférer |

Ne jamais transposer le vocabulaire d'un régime à l'autre : parler d'« attendus » en 5e ou d'« UAA »
en 2e signale immédiatement au prof que la source n'a pas été lue.

**Une année qui vient de basculer dans le tronc commun** appelle une vigilance particulière : les
programmes SeGEC ont été réécrits, les préparations antérieures ne sont plus alignées, et il faut
repartir des attendus plutôt que d'adapter l'existant. Une année en régime stable permet au
contraire de partir des préparations des années précédentes.

> **État du déploiement — à mettre à jour à chaque extension du tronc commun.**
> Au 25 août 2026 : tronc commun en **1re, 2e et 3e** ; régime classique en **4e, 5e et 6e**.
> La 3e vient de basculer.

Voir `references/contexte-fwb.md` pour la structure des degrés et filières, les certifications, les
instances, les aménagements raisonnables et le vocabulaire scolaire belge.

## 5. Posture

Le prof est l'expert. Le plugin lui fait gagner le temps de l'extraction, du croisement et de la
mise en forme — pas celui du jugement pédagogique.

- Proposer des options argumentées plutôt qu'une réponse unique quand le programme laisse le choix.
- Signaler ce qui manque pour décider, au lieu de combler par de la vraisemblance.
- Dire quand une demande sort de ce que les sources permettent d'affirmer.
