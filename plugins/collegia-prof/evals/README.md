# Évaluations

Trois cas, un par invariant du plugin. Ils testent ce que le plugin doit **refuser** de faire —
c'est là que se joue sa valeur, pas dans la qualité rédactionnelle des documents produits.

| Cas | Invariant testé |
|---|---|
| `garde-fou-matrice` | Analyser avant de proposer : aucune production sans matrice de référence |
| `source-absente` | Ne rien fabriquer : une source absente du corpus se signale, ne se reconstitue pas |
| `charte-orange` | Charte : l'orange ne porte jamais de texte, la famille orange conclut |

## Exécution

```bash
claude plugin eval ./plugins/collegia-prof
claude plugin eval ./plugins/collegia-prof --case garde-fou-matrice
```

`claude plugin eval` est en **accès anticipé** ; tant qu'il n'est pas activé, les trois cas se
rejouent à la main :

```bash
cd $(mktemp -d)   # dossier vierge : aucune matrice ne doit exister
claude --plugin-dir <chemin>/plugins/collegia-prof -p "$(cat <chemin>/evals/garde-fou-matrice/prompt.md)"
```

Puis relire la réponse contre `graders/criteria.md`.

**État au dernier passage manuel :** `garde-fou-matrice` réussi — refus de produire, renvoi vers
`matrice`, régime correctement identifié, ligne de traçabilité à zéro. Les deux autres n'ont pas
encore été joués.
