# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Nature du dépôt

Ce dépôt ne contient **aucun code exécutable** : c'est une *marketplace* de plugins Claude Code
pour les enseignants du Collège de Bruxelles. Le « produit » est du Markdown avec frontmatter YAML,
consommé par Claude Code lui-même. Il n'y a donc ni build, ni lint, ni suite de tests — la
validation se fait avec le CLI `claude` et le test se fait en chargeant le plugin dans une session.

Le contenu est rédigé **en français** (français de Belgique, contexte Fédération Wallonie-Bruxelles).
Garder cette langue pour tout ce qui est destiné aux enseignants : skills, README, descriptions du
marketplace.

Seule exception au « pas de code » : le dépôt hébergera à terme les **PDF des référentiels FWB et
programmes SeGEC** sous `plugins/collegia-prof/skills/corpus/references/`. Ils sont volumineux et
versionnés délibérément — une réforme de programme se lit dans le diff. Les manuels scolaires, eux,
sont sous droits et ne doivent **jamais** être ajoutés au dépôt.

## Commandes

```bash
# Valider le manifeste du marketplace (à la racine)
claude plugin validate .

# Valider un plugin
claude plugin validate ./plugins/collegia-prof

# Tester un plugin sans l'installer : ouvre une session avec le plugin chargé
claude --plugin-dir ./plugins/collegia-prof
#   puis dans la session : /collegia-prof:<skill>  ·  /reload-plugins après chaque édition

# Tester le marketplace complet (résolution des entrées + sources)
#   dans une session Claude Code :
#   /plugin marketplace add /Users/hmkhallati/collegia-claude-plugins
#   /plugin install collegia-prof@collegia-claude-plugins
```

```bash
# Évaluations — trois cas, un par invariant (voir plugins/collegia-prof/evals/)
claude plugin eval ./plugins/collegia-prof
claude plugin eval ./plugins/collegia-prof --case garde-fou-matrice
```

`claude plugin eval` est en **accès anticipé** et peut ne pas être activé : dans ce cas, rejouer les
cas à la main selon `plugins/collegia-prof/evals/README.md`.

`claude plugin validate` ne vérifie que les manifestes JSON. Il **ne valide pas** le frontmatter des
`SKILL.md` : une skill au frontmatter cassé est ignorée silencieusement. Après toute édition de
skill, vérifier en session avec `/reload-plugins` puis `/help` (la skill doit apparaître sous
l'espace de noms du plugin).

**Piège de test :** un `claude --plugin-dir` lancé depuis un répertoire sans rapport ne peut pas lire
les fichiers `references/` du plugin — le bac à sable les bloque, et les skills semblent alors
échouer alors qu'elles se comportent correctement. Tester depuis la racine du dépôt.

## Architecture

Deux niveaux de manifeste, à garder synchronisés à la main :

- `.claude-plugin/marketplace.json` — le catalogue. Chaque entrée pointe vers un plugin via
  `"source": "./plugins/<nom>"`. **Ajouter un plugin sans ajouter son entrée ici le rend
  invisible** : le dossier existe mais n'est jamais servi.
- `plugins/<nom>/.claude-plugin/plugin.json` — l'identité du plugin. Son champ `name` est
  l'**espace de noms** de toutes ses skills : `/[nom-du-plugin]:[nom-de-la-skill]`. Le renommer
  casse toutes les invocations existantes.

Piège de structure : seul `plugin.json` va dans `.claude-plugin/`. `skills/`, `agents/`, `hooks/`,
`.mcp.json` vont à la **racine du plugin**, pas dedans.

Le `version` du plugin gouverne les mises à jour côté utilisateur : sans incrément, personne ne
reçoit les changements. L'incrémenter dans **les deux** manifestes (ils sont dupliqués) à chaque
modification de contenu destinée à être publiée.

### Le plugin `collegia-prof`

Tout est en **skills** ; pas de dossier `commands/` (les commandes personnalisées ont fusionné dans
les skills en amont ; `commands/` reste supporté mais est l'ancienne forme).

Le plugin est centré sur la **préparation de début d'année** et repose sur une chaîne à sens unique :

```
corpus  →  matrice  →  intentions-pedagogiques · planification · sequence → supports
```

- **`corpus`** porte le fonds documentaire **embarqué dans le plugin** (référentiels FWB, programmes
  SeGEC). Il se met à jour en modifiant ce dépôt, pas chez le prof.
- **`matrice`** produit la matrice de référence d'un cours-année : les attendus extraits et cités.
- Les **skills de production** lisent la matrice et **jamais le corpus directement**. Un attendu mal
  lu se corrige ainsi à un seul endroit.
- **`methode`** et **`charte`** sont des skills de référence : elles ne produisent rien et sont
  chargées par les autres.

Trois invariants qui ne doivent pas être affaiblis par une édition — ils sont la raison d'être du
plugin, pas des précautions de style :

1. **Analyser avant de proposer.** Chaque skill de production commence par vérifier qu'une matrice
   existe et **refuse de produire** sinon. Retirer ce garde-fou vide le plugin de son sens.
2. **Traçabilité.** Tout élément produit porte `[FWB §<id>]`, `[SeGEC p.<n>]`, `[COLLÈGE]` ou
   `[PROPOSITION]`. Un identifiant ne se fabrique jamais : en cas de doute,
   `[FWB — référence à vérifier]`. Voir `skills/corpus/references/conventions.md`.
3. **Ne rien fabriquer.** Source historique, statistique, page de manuel, date de calendrier : ce qui
   n'est pas dans le corpus est signalé comme manquant, jamais reconstitué de mémoire.

Le savoir ne se duplique pas dans une skill de production : une règle pédagogique ou déontologique
vit dans `methode`, une règle de mise en forme dans `charte`. Une règle ajoutée dans
`planification/SKILL.md` plutôt que dans `methode/SKILL.md` ne s'appliquera pas aux autres skills.

Le corpus est **volontairement vide** à ce stade : la structure, les conventions de nommage et le
format d'identifiant sont posés, les sources arrivent ensuite. `INDEX.md` est le seul fichier du
corpus lu systématiquement et doit rester court ; ne jamais charger un référentiel entier.
`references/_exemple-format/` contient un exemple **fictif** qui ne doit jamais être cité comme
source.

### Bonnes pratiques de rédaction des skills

Seuils issus de la [doc officielle](https://platform.claude.com/docs/fr/agents-and-tools/agent-skills/best-practices),
tous respectés aujourd'hui — à revérifier après chaque édition :

| Règle | Seuil | État du dépôt |
|---|---|---|
| `name` | ≤ 64 car., `[a-z0-9-]` uniquement, sans « claude » ni « anthropic » | 8/8 conformes |
| `description` | ≤ 1 024 caractères | max. 482 (`charte`) |
| Corps du `SKILL.md` | < 500 lignes | max. 99 (`matrice`) |
| Fichier de référence | table des matières au-delà de 100 lignes | `charte-college.md` en a une |
| Profondeur des références | **un seul niveau** depuis `SKILL.md` | respecté |

Points qui demandent une vigilance particulière dans ce dépôt :

- **Chemins relatifs.** Un lien écrit dans `supports/SKILL.md` se résout depuis `supports/`. Pour
  pointer vers un fichier d'une autre skill, écrire le chemin complet
  (`../charte/references/composants.md`), jamais `references/composants.md`. Erreur silencieuse : le
  fichier n'est simplement jamais lu.
- **Contenu périssable.** Ne pas écrire « cette année » ni une année scolaire dans une règle. Le
  régime pédagogique se déduit de l'**année d'étude**, pas du millésime. Le seul endroit qui date
  est le bloc « État du déploiement » de `methode/SKILL.md`, explicitement marqué comme à mettre à
  jour à chaque extension du tronc commun.
- **Concision.** Ne pas expliquer à Claude ce qu'il sait déjà. Ce qui mérite d'être écrit ici, c'est
  ce qui est propre au collège, à la FWB, ou contre-intuitif — pas la définition d'un objectif
  pédagogique.
- **Terminologie constante.** Toujours « attendu » (tronc commun) ou « UAA » (régime classique),
  jamais un mélange ; toujours « matrice de référence », jamais « socle » ni « cadrage » ; toujours
  « corpus », jamais « fonds » ni « base documentaire ».
- **Degrés de liberté.** Les invariants s'écrivent en impératif absolu (« ne produit aucune
  planification »), le pédagogique en heuristiques. Ne pas durcir le second ni assouplir le premier.
- **Une option par défaut, pas un catalogue.** Donner la voie recommandée et l'échappatoire, sans
  énumérer toutes les alternatives.

### Autres contraintes du frontmatter

- Le **nom du dossier** définit la commande tapée. Le champ `name:` n'est qu'un libellé d'affichage
  (il est présent ici et aligné sur le dossier, mais ne le renommer jamais seul en croyant renommer
  la commande).
- `description` est le seul contenu chargé en permanence ; c'est lui qui décide du déclenchement
  automatique. `description` + `when_to_use` sont tronqués à **1 536 caractères** dans la liste des
  skills — plafond de la liste, distinct de la limite de 1 024 du champ lui-même. Les descriptions
  doivent rester **disjointes** : celle de `matrice` doit gagner sur celles des skills de production
  quand un prof dit simplement « je dois préparer mon cours », sinon la chaîne est court-circuitée.
- `argument-hint` documente les arguments attendus. Substitutions disponibles dans le corps :
  `$ARGUMENTS`, `$0`/`$1` (indexés, guillemettage shell), `$name` si déclaré via `arguments:`.
- `disable-model-invocation: true` rend une skill invocable **uniquement** par l'utilisateur et sort
  sa description du contexte. Aucune skill ne l'utilise — c'est le levier à proposer si une skill à
  effets de bord ne doit plus se déclencher seule.

### Évaluations

`plugins/collegia-prof/evals/` contient trois cas, un par invariant : `garde-fou-matrice`,
`source-absente`, `charte-orange`. Ils testent ce que le plugin doit **refuser** de faire — c'est là
que se joue sa valeur. Les trois passent au dernier jeu manuel.

Toute modification d'un invariant doit s'accompagner du cas correspondant. Ajouter un cas est
préférable à assouplir un critère existant.

## Règles de contenu

Encodées dans `methode` et dans les skills de production :

- **Hiérarchie des sources** : le référentiel FWB fixe le niveau d'exigence, le programme SeGEC fixe
  la mise en œuvre. Une divergence réelle entre les deux se signale au prof, ne s'arbitre jamais en
  silence.
- **Deux régimes cohabitent en 2026-2027** : référentiels du tronc commun et vocabulaire d'*attendus*
  en 1-3 ; programmes classiques et *UAA* avec processus Connaître / Appliquer / Transférer en 4-6.
  Ne jamais transposer le vocabulaire d'un régime à l'autre.
- **Le prof est l'expert.** Le plugin fait gagner le temps de l'extraction, du croisement et de la
  mise en forme, pas celui du jugement pédagogique. Proposer des options argumentées, signaler ce
  qui manque pour décider.
- Objectifs formulés par des verbes observables ; alignement attendus ↔ activités ↔ évaluation.

## Hors périmètre assumé

Ressources personnelles du prof (manuel numérisé sous droits, anciens cours), évaluations et
correction, communication aux familles, conseil de classe. Ne pas les réintroduire sans demande
explicite : le plugin a été volontairement resserré de 14 skills à 8.
