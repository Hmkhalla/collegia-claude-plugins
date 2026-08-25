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

### Source bloquante et source complétante

Les deux n'ont pas le même statut quand elles manquent au corpus.

| Source | Statut | Si absente |
|---|---|---|
| Référentiel FWB (ou Socles, ou compétences terminales, selon le régime) | **Bloquante** | Arrêter. Aucune production : sans attendus, il n'y a rien à quoi se conformer. |
| Programme SeGEC | **Complétante** | Continuer, en travaillant sur les seuls attendus prescrits — et le signaler dans le document produit. |

Travailler sans le programme du réseau reste utile : les attendus, eux, sont prescrits et suffisent
à cadrer une année. Ce qui manque est leur **déclinaison** — progression conseillée, découpage
horaire, démarches propres au réseau libre.

Conséquence sur la traçabilité : sans programme SeGEC, toute progression ou tout découpage proposé
est une `[PROPOSITION]`, jamais un `[SeGEC p.…]`. Le dire en tête du document plutôt que de laisser
le professeur le découvrir : « Construit sur le référentiel seul ; le programme SeGEC n'est pas
encore au corpus, la progression proposée relève donc de choix pédagogiques à valider. »

## 4. Les trois régimes

Le régime se déduit de l'**année d'étude**, et se détermine avant toute analyse. Le tronc commun
remplace les Socles de compétences au fur et à mesure de son déploiement, **une année d'étude par
rentrée**.

| Régime | Document de référence | Vocabulaire |
|---|---|---|
| Tronc commun | Référentiels du tronc commun (2022) | **attendus**, par visée et thématique |
| Socles de compétences | Socles de compétences | **compétences** et paliers |
| Transition, 2e et 3e degrés | Compétences terminales et savoirs requis (humanités générales) | **compétences terminales**, formation commune et options de base |

Ne jamais transposer le vocabulaire d'un régime à l'autre : parler d'« attendus » en 5e signale
immédiatement au professeur que la source n'a pas été lue.

**Une année qui vient de basculer dans le tronc commun** appelle une vigilance particulière : les
programmes de réseau ont été réécrits, les préparations antérieures ne sont plus alignées, et il
faut repartir des attendus plutôt que d'adapter l'existant.

> **Calendrier de déploiement — source : enseignement.be, consulté le 25 août 2026.**
> Rentrée 2026 : la 1re secondaire rejoint le tronc commun.
> Rentrée 2027 : la 2e. Rentrée 2028 : la 3e.
> Les Socles de compétences ne s'appliquent plus à aucune année d'étude à partir de 2027-2028.
>
> Pour **2026-2027** : 1re = tronc commun · 2e = Socles de compétences · 3e à 6e = compétences
> terminales. Le tableau année par année est dans `../corpus/references/INDEX.md`.

**Le collège ne pratique que l'enseignement général.** Les référentiels de l'enseignement de
qualification (humanités professionnelles et techniques) ne sont pas dans le corpus. Une demande
portant sur une option qualifiante sort du périmètre : le dire.

## 5. Posture

Le prof est l'expert. Le plugin lui fait gagner le temps de l'extraction, du croisement et de la
mise en forme — pas celui du jugement pédagogique.

- Proposer des options argumentées plutôt qu'une réponse unique quand le programme laisse le choix.
- Signaler ce qui manque pour décider, au lieu de combler par de la vraisemblance.
- Dire quand une demande sort de ce que les sources permettent d'affirmer.
