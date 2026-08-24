# collegia-claude-plugins

Marketplace des plugins [Claude Code](https://claude.com/claude-code) du **Collège de Bruxelles**.

Ce dépôt regroupe les plugins (skills, commandes, serveurs MCP, hooks) mis à
disposition des enseignants de l'école.

## Installation

Dans Claude Code :

```
/plugin marketplace add Hmkhalla/collegia-claude-plugins
/plugin install <nom-du-plugin>@collegia-claude-plugins
```

## Plugins disponibles

Aucun plugin publié pour le moment.

## Structure du dépôt

```
.claude-plugin/
  marketplace.json    # catalogue des plugins exposés par ce marketplace
plugins/
  <nom-du-plugin>/    # un dossier par plugin
    .claude-plugin/
      plugin.json     # manifeste du plugin
    skills/           # skills (optionnel)
    commands/         # slash commands (optionnel)
    .mcp.json         # serveurs MCP (optionnel)
```

## Ajouter un plugin

1. Créer `plugins/<nom-du-plugin>/` avec son manifeste `.claude-plugin/plugin.json`.
2. Ajouter une entrée correspondante dans le tableau `plugins` de
   `.claude-plugin/marketplace.json`, avec `"source": "./plugins/<nom-du-plugin>"`.
3. Tester localement :

   ```
   /plugin marketplace add /chemin/vers/collegia-claude-plugins
   ```

4. Commiter et pousser — Claude Code récupère la version publiée depuis GitHub.

## Licence

MIT — voir [LICENSE](LICENSE).
