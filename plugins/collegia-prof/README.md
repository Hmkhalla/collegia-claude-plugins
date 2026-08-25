# collegia-prof

Plugin Claude Code pour les professeurs du secondaire en Fédération Wallonie-Bruxelles, centré sur
la **préparation de début d'année** : construire ses cours en restant ancré sur les **référentiels
FWB** et les **programmes SeGEC**.

## Le principe

Deux règles gouvernent tout le plugin :

1. **Analyser avant de proposer.** Les attendus du programme sont extraits et cités *avant* qu'une
   ligne de cours soit écrite. Jamais l'inverse.
2. **Distinguer le vérifié du proposé.** Chaque élément d'un document produit porte sa source —
   `[FWB §…]`, `[SeGEC p.…]`, `[COLLÈGE]` — ou est marqué `[PROPOSITION]`.

## Installation

```
/plugin marketplace add Hmkhalla/collegia-claude-plugins
/plugin install collegia-prof@collegia-claude-plugins
```

Les référentiels et programmes sont **embarqués dans le plugin** : rien à télécharger ni à
configurer. Ils se mettent à jour en mettant à jour le plugin.

## Le parcours

```
        corpus                    le fonds documentaire du collège, embarqué
          ↓
        matrice                   ← commencer ici, une fois par cours
          ↓
  ┌───────────────────────┬──────────────────┬────────────────────┐
  intentions-pedagogiques    planification      sequence → supports
```

| Skill | Ce qu'elle produit |
|---|---|
| `matrice` | La matrice de référence d'un cours-année : attendus cités, volume horaire réel, progression imposée, ce qui change avec la réforme |
| `intentions-pedagogiques` | Le document d'intention pédagogique |
| `planification` | La planification de l'année, sur les périodes réellement disponibles |
| `sequence` | L'architecture d'une séquence : attendus couverts, fil conducteur, découpage |
| `supports` | Support élève, support prof et préparation, dérivés d'un même contenu |
| `corpus` | Consultation et mise à jour du fonds documentaire |

Les skills de production **refusent de travailler sans matrice** et renvoient vers `matrice`. C'est
le garde-fou principal, pas une formalité.

Deux skills de référence se chargent seules et ne s'invoquent pas : `methode` (hiérarchie FWB ↔
SeGEC, régimes en vigueur, traçabilité) et `charte` (charte graphique, gabarits, export).

## Utilisation

```
/collegia-prof:matrice histoire 3e
/collegia-prof:planification histoire 3e 2026-2027
/collegia-prof:sequence histoire 3e — le temps des révolutions, 12 périodes
/collegia-prof:supports leçon 3 de la séquence sur les révolutions
```

Ou en langage naturel : « je dois préparer mon cours d'histoire de 3e cette année » déclenche
`matrice` en premier.

## Les deux régimes de 2026-2027

| Niveau | Régime | Conséquence |
|---|---|---|
| 1re, 2e, 3e | Nouveaux référentiels du tronc commun, organisés en **attendus** | Les préparations antérieures ne sont plus alignées : repartir des attendus |
| 4e, 5e, 6e | Programmes classiques, structurés en **UAA** | Régime stable, les préparations antérieures restent valides |

## État du corpus

**Le corpus est vide.** La structure, les conventions de découpage et le format d'identifiant de
citation sont posés (`skills/corpus/references/`) ; les sources se remplissent au fur et à mesure.
Une demande portant sur une discipline absente reçoit une réponse explicite — jamais une
reconstitution de mémoire.

Pour ajouter une source, voir `skills/corpus/references/conventions.md` : le nommage est
déterministe.

## À fournir

- Les PDF des référentiels FWB et programmes SeGEC.
- Ce qui manque à la charte : familles typographiques et géométrie de page, logo, jetons vert et
  rouge des paliers de différenciation, table des libellés d'encadrés par degré, et le fichier
  `charte-cdb.sty` cité comme référence de l'existant. Détail dans `skills/charte/SKILL.md`.
- Le calendrier scolaire 26-27 du collège, sans lequel `planification` travaille sur un calendrier
  générique dont toutes les dates sont marquées à vérifier.

## Hors périmètre

Ressources personnelles du prof (manuel numérisé, anciens cours), évaluations et correction,
communication aux familles, conseil de classe. Une itération ultérieure traitera l'intégration d'un
manuel de référence.
