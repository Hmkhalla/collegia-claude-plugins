---
name: charte
description: Charte graphique du Collège de Bruxelles et production des documents — palette et contrastes, densité et accessibilité, espacement, catalogue fermé d'encadrés, zones à compléter, paliers de différenciation, pagination et chaîne de sortie (HTML/CSS, LaTeX, artifact). Base de connaissances chargée par toutes les skills qui produisent un document destiné aux élèves, aux collègues ou à la direction ; à charger aussi pour mettre en forme, exporter ou imprimer un document du collège.
---

# Charte et production de documents

Cette skill gouverne la **sortie**. Elle est chargée au moment de produire un document, jamais au
moment d'analyser un référentiel.

## Une source, plusieurs sorties

Le contenu s'écrit **une fois en Markdown**, marques de traçabilité intactes. Le rendu vient après.
Ne jamais rédiger directement dans le format de sortie : on perdrait la régénération, la comparaison
entre versions et le lien aux citations.

```
contenu Markdown tracé  →  charte  →  HTML/CSS · LaTeX · artifact · (Word, dégradé)
```

## Ce qui ne se négocie pas

Six règles suffisent à faire qu'un document soit à la charte ou non. Elles sont détaillées dans les
fichiers de référence ; les enfreindre produit un document qu'il faudra refaire.

1. **L'orange ne porte jamais de texte.** `--orange` (#FF8E06) donne 2,30:1 sur blanc. Sur un aplat
   orange, le texte est **bleu** (6,85:1), jamais blanc. `--orange-texte` (#B35F00) existe pour les
   cas où l'orange doit être écrit — et **uniquement sur blanc pur**.
2. **L'orange veut dire « regarde ici ».** Il ne décore pas. Réservé aux propositions en attente, aux
   compétences non couvertes, aux reproductions sous droits.
3. **Aucun espacement n'est saisi dans le contenu.** Cinq jetons, appliqués par voisinage. Pas de
   `\vspace` ni de marge à la main : c'est la première cause d'irrégularité entre chapitres.
4. **Le catalogue des composants est fermé.** Six encadrés, six formes de zone à compléter, trois
   paliers. Un besoin non couvert se signale au prof, il ne s'invente pas.
5. **Les lignes de réponse restent solidaires de leur énoncé.** Une question séparée de ses lignes
   par un saut de page est inutilisable.
6. **Densité et accessibilité sont deux axes indépendants**, pas les crans d'un même réglage. Un
   élève dyslexique de 17 ans a besoin des deux.

## Références

| Fichier | Contenu |
|---|---|
| `references/charte-college.md` | Palette et contrastes vérifiés · densité × accessibilité · les cinq crans d'espacement · typographie et page |
| `references/composants.md` | Les six encadrés et leurs règles d'emploi · zones à compléter · paliers de différenciation |
| `references/production.md` | Pagination CSS vs LaTeX · noyau et extensions · chaîne de sortie et ce que chaque voie porte |

Charger le fichier utile, pas les trois.

## Choisir la sortie

| Document | Voie |
|---|---|
| Support distribué aux élèves | **HTML/CSS à la charte**, ou LaTeX si la typographie est exigeante |
| Support prof, préparation | HTML/CSS ; **Word** si le prof doit le retoucher lui-même |
| Document d'intention pédagogique, planification | HTML/CSS, PDF pour la version déposée |
| Document à faire relire | **artifact** — lien partageable, itération rapide |

**Word ne porte pas cette charte** : ni l'espacement par voisinage, ni les zones proportionnées, ni
la solidarité énoncé/réponse, ni les deux axes de réglage. Le proposer quand le prof doit modifier
le contenu lui-même, **en disant ce qui est perdu**. Jamais par défaut pour un document distribué.

Vérifier la voie disponible dans la session avant de l'annoncer. Si aucune ne l'est, livrer le
Markdown mis en forme et le dire.

## Traçabilité au rendu

Les marques `[FWB §…]`, `[SeGEC p.…]`, `[PROPOSITION]` sont un outil de travail du **prof**, pas une
information pour l'élève.

- **Support élève** : marques retirées du rendu.
- **Support prof, préparation, DIP, planification** : marques conservées, rendues discrètement — note
  de marge, `--bleu`, 8-9 pt.
- Le **Markdown source conserve toujours les marques**, quel que soit le rendu.

Une exception d'usage : l'orange signalant une reproduction sous droits ou une compétence non
couverte reste visible sur le support prof — c'est ce qu'il doit voir avant de photocopier.

## Ce qui manque encore

Ne pas combler ces trous en choisissant à la place du collège ; les signaler.

- Les **familles typographiques** et la géométrie de page réelles.
- Le **logo**, dans `assets/`.
- Les jetons **vert** et **rouge** des paliers de différenciation — d'ici là, produire les paliers en
  forme et chiffre uniquement, ce qui suffit.
- La table des **libellés d'encadrés par degré et par discipline** — demander au prof le libellé
  qu'il emploie plutôt que d'en choisir un.
- Le fichier **`charte-cdb.sty`**, cité comme source de vérité de l'existant mais absent du dépôt.
