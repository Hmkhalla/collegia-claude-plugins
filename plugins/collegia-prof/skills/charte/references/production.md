# Production et pagination

## Le point faible : la pagination

C'est la vraie régression du passage de LaTeX au web, et elle doit être annoncée plutôt que
découverte.

| | Ce que le moteur sait faire |
|---|---|
| **LaTeX** | **Mesure** un exercice et le reporte en bloc s'il ne tient pas — sauf s'il dépasse une page entière |
| **CSS** | Sait seulement **interdire** une coupure (`break-inside: avoid`). Il ne mesure ni n'arbitre |

**Conduite :** `@page` et règles de rupture d'abord ; **Paged.js** en recours si la solidarité
question / lignes de réponse ne tient pas.

**Régression assumée face à LaTeX** : pas de signets PDF à deux niveaux, pas d'onglets de
navigation. Le dire au prof plutôt que de le laisser le constater sur un document distribué.

## Noyau et extensions

`charte-cdb.sty` mélange les deux : il contient `\droite`, `\fr`, `\thermometre`, propres aux
mathématiques du premier degré, et code en dur un pied de page à sa ligne 149.

**Le portage sépare :**

- le **noyau commun** — couleurs, espacement, encadrés, zones à compléter, paliers, en-tête et pied
  de page composés depuis les métadonnées ;
- les **extensions disciplinaires** — commandes propres à une discipline et à un degré, chargées
  séparément.

Une commande utile à une seule discipline ne rejoint jamais le noyau. Inversement, un besoin qui
apparaît dans deux disciplines est un signal de remontée vers le noyau.

## Chaîne de sortie

Ce plugin est utilisé dans Claude Code, Claude web et Claude desktop. La voie disponible varie ;
la **vérifier avant de l'annoncer**.

| Voie | Quand | Ce qu'elle porte |
|---|---|---|
| **HTML + CSS à la charte** | Voie normale | Jetons, `data-densite`, `data-accessibilite`, espacement par voisinage, `break-inside` |
| **HTML + Paged.js** | Quand la solidarité question/réponse ne tient pas | Idem, plus un contrôle réel de la pagination |
| **LaTeX** | Documents à typographie exigeante, chaîne existante | Tout, y compris la mesure et le report de blocs |
| **Artifact** | Faire relire, itérer avant de figer | Le rendu HTML, partageable par lien |
| **Word** | Sur demande explicite du prof | **Ne porte pas la charte** — voir ci-dessous |

### Word ne porte pas cette charte

À dire clairement quand un prof le demande. Word ne peut exprimer ni l'espacement par voisinage, ni
les zones à compléter proportionnées, ni la solidarité énoncé/réponse, ni les deux axes densité ×
accessibilité. Un `.docx` produit ici est une **approximation retouchable**, pas un document à la
charte.

Le proposer quand le prof doit modifier lui-même le contenu, en disant ce qui est perdu. Pour tout
document distribué à des élèves, la voie est HTML/CSS ou LaTeX.

Si aucune voie n'est disponible dans la session, livrer le Markdown source et le dire — plutôt que
de promettre un fichier qui n'arrivera pas.
