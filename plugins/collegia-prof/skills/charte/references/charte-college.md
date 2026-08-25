# Charte graphique — Collège de Bruxelles

Référentiel visuel. Les valeurs de ce fichier font autorité : aucune couleur, taille ou valeur
d'espacement ne doit être écrite en dur ailleurs.

## Sommaire

- Couleurs — palette, contrastes vérifiés, deux limites mesurées, trois couleurs manquantes
- Densité et accessibilité — deux axes indépendants
- Espacement — cinq crans, appliqués par voisinage
- Typographie et géométrie de page (provisoire)
- À fournir

## Couleurs

| Jeton | Valeur | Contraste sur blanc | Usage |
|---|---|---|---|
| `--bleu` | `#0F1B5C` | **15,77:1** | la couleur du texte et de la structure |
| `--orange` | `#FF8E06` | 2,30:1 | aplats, filets, marqueurs — **jamais du texte** |
| `--orange-bis` | `#FBBB53` | 1,70:1 | décoratif seul |
| `--orange-texte` | `#B35F00` | **4,61:1** | l'orange quand il doit porter du texte |
| `--encre` | `#1A1A28` | 17,18:1 | noir adouci — jamais `#000` sur `#FFF` |

Ratios vérifiés par calcul WCAG 2.x. Combinaisons complémentaires mesurées :

| Combinaison | Ratio | Niveau |
|---|---|---|
| `--bleu` sur aplat `--orange` | **6,85:1** | AA |
| blanc sur aplat `--orange` | 2,30:1 | **échec** |
| `--encre` sur aplat `--orange` | 7,46:1 | AAA |
| `--bleu` sur `--orange-bis` | 9,26:1 | AAA |

**Défaut hérité, corrigé.** `charte-cdb.sty` compose la pastille de titre en texte blanc sur aplat
orange : 2,30:1, sous le seuil AA. Le bleu sur ce même aplat donne 6,85:1. La correction vaut pour
l'écran et pour l'impression.

**L'orange veut dire « regarde ici », et rien d'autre.** Il perd son sens s'il décore. Réservé aux
propositions en attente, aux compétences non couvertes, aux reproductions sous droits.

### Deux limites mesurées, absentes de la charte d'origine

- **`--orange-texte` ne tient qu'sur blanc pur.** 4,61:1 laisse 0,11 de marge au-dessus du seuil AA.
  Sur la moindre teinte il passe dessous : 4,38 sur une teinte orange à 3 %, 4,31 sur un gris très
  clair. Ne jamais le poser sur un fond autre que `#FFFFFF`. Sur fond teinté, utiliser `--bleu`.
- **`--orange-texte` échoue en AAA** (seuil 7,0). Acceptable pour un support de cours ; à signaler si
  un document doit viser AAA.

### Trois couleurs manquantes

Les paliers de différenciation exigent vert, orange et rouge (voir `composants.md`). Seul l'orange
existe dans la palette, et il est déjà chargé de sens. **Le vert et le rouge ne sont pas définis** :
ni jeton, ni valeur, ni contraste vérifié. À trancher avant de produire un support différencié —
d'ici là, s'appuyer sur la forme et le chiffre, qui suffisent seuls.

## Densité et accessibilité — deux axes indépendants

`data-densite` et `data-accessibilite` se combinent librement. Ce ne sont pas les crans d'un même
réglage : un élève dyslexique de 17 ans a besoin de `dense` **et** de `renforcee`.

| | `dense` (défaut, D2/D3) | `aeree` |
|---|---|---|
| corps · interligne | 11 pt · 1,12 | 12 pt · 1,5 |

| `accessibilite="renforcee"` | Effet |
|---|---|
| alignement | drapeau à droite — supprime les « rivières » |
| césure | désactivée |
| zones d'écriture | **trait plein** — les pointillés « sautent » à la relecture |
| italique | neutralisée en gras coloré |
| interlettrage | légèrement ouvert |

Les données disponibles montrent un bénéfice bien plus net pour ces réglages d'espacement et de mise
en page que pour les polices dites « dyslexiques ». Ne pas proposer de police spécialisée comme
réponse principale.

## Espacement — cinq crans, appliqués par voisinage

| Jeton | Valeur | S'applique |
|---|---|---|
| `--esp-xs` | 0,35 rem | entre items d'une même liste |
| `--esp-s` | 0,7 rem | après un paragraphe |
| `--esp-m` | 1,2 rem | autour d'un encadré, d'une figure, d'un tableau |
| `--esp-l` | 2,2 rem | avant un titre 2 |
| `--esp-xl` | 3,2 rem | avant un titre 1, avant un exercice |

**Aucun espacement n'est jamais saisi dans le contenu.** Il est produit par des sélecteurs de
voisinage. Les `\vspace{2em}`, `{1.6em}`, `{2.4em}` posés à la main dans les chapitres LaTeX
existants sont la principale source d'irrégularité d'un chapitre à l'autre : c'est précisément ce
que ces jetons suppriment.

Cas de voisinage documentés :

- deux encadrés consécutifs se collent ;
- un titre suivi d'un encadré n'ajoute rien ;
- un bloc en tête de page ne pousse pas de marge haute.

Les valeurs sont en `rem` : côté LaTeX, la table de correspondance est à établir une fois lors du
portage, pas à improviser document par document.

## Typographie et géométrie de page

> ⚠️ **Non couvert par la charte fournie.** Les valeurs ci-dessous sont provisoires et à remplacer.

| Usage | Provisoire |
|---|---|
| Titres | Police à empattement, 16-20 pt |
| Corps | Sans empattement, taille selon `data-densite` |
| Notes et citations de source | Sans empattement, `--bleu`, 8-9 pt |
| Marges | 2 cm · 2,5 cm côté reliure |
| En-tête | Nom du collège, discipline, année d'étude, année scolaire |
| Pied de page | Professeur, version, pagination `n / N` |

Le pied de page se compose **depuis les métadonnées du document**. `charte-cdb.sty` code en dur
« Chapitre 1 : le territoire des nombres » à sa ligne 149 : ce défaut ne doit pas être reporté.

## À fournir

- Les **familles typographiques** et la géométrie de page réelles.
- Le **logo** dans `../assets/`.
- Les **jetons vert et rouge** des paliers de différenciation, avec leurs contrastes.
- Le fichier **`charte-cdb.sty`** lui-même : il est cité comme source de vérité de l'existant mais
  n'est pas dans le dépôt. Le portage noyau/extensions ne peut pas être fait sans lui.
