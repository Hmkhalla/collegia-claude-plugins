# Conventions du corpus

Ces conventions existent pour qu'ajouter une source ne demande **aucune décision** : le chemin et le
nom du fichier se déduisent de la source elle-même.

## Arborescence

```
references/
  INDEX.md                    # la carte — seul fichier lu systématiquement
  conventions.md              # ce fichier
  fwb/<discipline>/<niveau>/
      fwb-<discipline>-<niveau>-<aaaa>.pdf       # source officielle, conservée
      md/                                        # découpage dérivé, quand il existe
          00-sommaire.md
          <nn>-<titre-de-section>.md
  segec/<discipline>/<niveau>/
      segec-<discipline>-<niveau>-<aaaa>.pdf
      md/
  college/
      <document>-<aaaa>.pdf
  _exemple-format/            # démonstration du format — contenu FICTIF, ne jamais citer
```

- **`<discipline>`** en minuscules sans accent ni espace : `histoire`, `francais`, `sciences`,
  `math`, `langues-modernes`, `education-physique`.
- **`<niveau>`** : `1`, `2`, `3` pour le tronc commun ; `d2`, `d3` pour les deuxième et troisième
  degrés. Reprendre le découpage du document : si un référentiel couvre 1-2-3 d'un bloc, utiliser
  `1-3`.
- **`<aaaa>`** : année de publication du document, pas l'année scolaire d'usage. C'est elle qui
  distingue une version d'une autre lors d'une réforme.

## Identifiants d'attendu et citations

**Règle absolue : reprendre la numérotation du document officiel. Ne jamais en fabriquer une.**

C'est ce qui rend une citation vérifiable : le prof doit pouvoir ouvrir le PDF et retrouver
exactement ce qui est cité. Un identifiant inventé, même cohérent, casse la seule chose que le
plugin promet.

| Cas | Forme de la citation | Exemple |
|---|---|---|
| Le document numérote ses attendus | `[FWB §<numéro officiel>]` | `[FWB §H.3.2.1]` |
| Le document n'a pas de numérotation | `[FWB <fichier md> § <titre de section>]` | `[FWB 04-temps-des-revolutions § Repères]` |
| Programme du réseau | `[SeGEC p.<page du PDF>]` | `[SeGEC p.47]` |
| Document du collège | `[COLLÈGE <document>]` | `[COLLÈGE calendrier 26-27]` |
| Numéro incertain | `[FWB — référence à vérifier]` | — |

Ne jamais résoudre une incertitude par un numéro plausible. `[FWB — référence à vérifier]` est une
sortie acceptable ; un faux numéro ne l'est pas.

## Découpage markdown

- **Un fichier par chapitre ou par groupe d'attendus.** Jamais un référentiel entier en un fichier :
  le but du découpage est de pouvoir charger une section sans les autres.
- Préfixe numérique à deux chiffres pour conserver l'ordre du document : `03-…`, `04-…`.
- En tête de chaque fichier, un bloc d'origine :

  ```
  > Source : fwb-histoire-3-2022.pdf, p. 45-52
  > Section : Le temps des révolutions
  > Régime : tronc commun
  ```

- Conserver la numérotation officielle des attendus **telle quelle** dans les titres, y compris si
  elle est irrégulière.
- Ne pas reformuler, ne pas résumer, ne pas moderniser le vocabulaire. Le markdown est une
  **transcription structurée**, pas une réécriture. Toute reformulation détruirait la valeur de
  citation.
- Signaler les passages illisibles ou ambigus du PDF par `<!-- ILLISIBLE p.<n> -->` plutôt que de
  les compléter.

## Mise à jour lors d'une réforme

1. Ajouter le nouveau document **à côté** de l'ancien, avec sa propre année de publication.
2. Ne pas supprimer l'ancien : il documente ce que les préparations existantes suivaient, et permet
   de répondre à « qu'est-ce qui change pour moi cette année ? ».
3. Mettre à jour `INDEX.md` : le nouveau document devient la source active, l'ancien passe en
   `archive` dans la colonne État.
4. Le découpage markdown de l'ancien document n'a pas besoin d'être maintenu.
