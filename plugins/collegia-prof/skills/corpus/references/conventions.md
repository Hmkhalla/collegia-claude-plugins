# Conventions du corpus

Ces conventions existent pour qu'ajouter une source ne demande **aucune décision** : le chemin et le
nom du fichier se déduisent de la source elle-même.

## Arborescence

Organisée par **régime**, parce que c'est ainsi que les documents existent : un référentiel du tronc
commun couvre M1 à S3 d'un bloc, une compétence terminale couvre les 2e et 3e degrés. Il n'existe
pas de document « par année d'étude », et en forcer un dans le chemin serait une invention.

```
references/
  INDEX.md                          # la carte — seul fichier lu systématiquement
  conventions.md                    # ce fichier
  fwb/
    tronc-commun/                   # référentiels 2022 — 1re en 2026-2027
    socles-de-competences/          # 2e en 2026-2027, dernière année
    competences-terminales/         # transition, 2e et 3e degrés — 3e à 6e
    brochures/                      # compléments transversaux, non prescriptifs
  segec/                            # programmes du réseau libre — à fournir
  college/                          # documents propres au collège — à fournir
  _exemple-format/                  # démonstration du format — contenu FICTIF, ne jamais citer
```

**Les noms de fichiers officiels sont conservés tels quels** (`2022_REF_Hist-geo-FHGES.pdf`,
`CT_HGT_Histoire.pdf`). Ne pas les renommer : c'est ce qui permet au professeur de retrouver le
document sur enseignement.be et de vérifier une citation. L'INDEX porte l'intitulé lisible et
l'année de publication.

Pour une source qui n'a pas de nom officiel — un document du collège — nommer
`<document>-<aaaa>.<ext>`, en minuscules sans accent.

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

Le tronc commun se déploie une année d'étude par rentrée : le corpus doit porter **simultanément**
l'ancien et le nouveau régime pendant toute la transition. Ce n'est pas un état provisoire à nettoyer.

1. Ajouter le nouveau document **à côté** de l'ancien, dans le dossier de son régime.
2. Ne jamais supprimer l'ancien tant qu'une année d'étude en relève encore. Même après, le conserver
   permet de répondre à « qu'est-ce qui change pour moi cette année ? ».
3. Mettre à jour le tableau « Quel régime pour quelle année » d'`INDEX.md` — c'est lui qui fait
   autorité, et il doit avancer d'une ligne à chaque rentrée.
4. Mettre à jour le calendrier de déploiement dans `../../methode/SKILL.md`, qui porte la même
   information sous forme de règle.
