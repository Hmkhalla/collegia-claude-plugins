---
name: sequence
description: Construit l'architecture d'une séquence d'apprentissage — attendus couverts, fil conducteur, découpage en leçons, documents mobilisés, dispositif d'évaluation — ancrée sur la matrice de référence. À utiliser quand un prof prépare un chapitre, une séquence ou une partie de son programme, avant d'en rédiger les supports.
argument-hint: <discipline> <année> <thème de la séquence> [nombre de périodes]
---

# Architecture d'une séquence

Séquence demandée : **$ARGUMENTS**

Charge la skill `methode` (traçabilité, analyser avant de proposer).

## Préalable bloquant

Vérifier qu'une **matrice de référence** existe pour ce cours-année. Sans elle, **ne pas produire** :
renvoyer vers `matrice`.

Si une **planification** existe, la lire aussi : elle fixe le nombre de périodes allouées à cette
séquence et sa place dans l'année. Ne pas la contredire en silence — si la séquence ne tient pas
dans l'enveloppe prévue, le dire.

## Étape 1 — Ancrer avant de concevoir

Commencer par extraire de la matrice les **attendus que cette séquence doit couvrir**, avec leurs
citations, et les présenter au prof. Rien d'autre.

C'est le moment où la règle « analyser avant de proposer » se joue concrètement : la tentation est
de partir d'une belle idée de séquence et de lui rattacher des attendus après coup. L'ordre inverse
donne des séquences moins spectaculaires et beaucoup plus solides.

Signaler aussi ce que la séquence **ne couvre pas** et qui devra l'être ailleurs.

## Étape 2 — Concevoir

- **Fil conducteur** : une question ou un problème qui tient la séquence. Une séquence sans fil
  conducteur est une liste de leçons.
- **Découpage en leçons**, avec le nombre de périodes de chacune, dans l'enveloppe disponible.
- **Progression des niveaux** sur la séquence : Connaître → Appliquer → Transférer (régime
  classique), ou la progression des attendus (tronc commun). Une séquence qui reste au niveau
  restitution ne travaille pas l'attendu.
- **Documents et ressources** mobilisés. S'ils viennent d'un manuel ou d'une ressource du prof,
  citer précisément. **Ne jamais inventer une référence de document historique, de source ou de
  page de manuel** — proposer un type de document recherché et laisser le prof le fournir.
- **Dispositif d'évaluation** : ce qui est évalué en cours de séquence (formatif) et au terme
  (certificatif), rattaché aux attendus.
- **Différenciation** : où sont les points de décrochage prévisibles, et ce qu'on prévoit.

## Étape 3 — Produire

```
# Séquence — <titre>
<discipline> <année> · <n> périodes · place dans l'année

## Attendus couverts
| Identifiant | Intitulé | Niveau visé | Source |

## Fil conducteur
La question qui tient la séquence.

## Découpage
| Leçon | Titre | Périodes | Attendu(s) | Dispositif dominant | Trace écrite |

## Documents et ressources
Ce qui est nécessaire, avec ce qui reste à fournir par le prof.

## Évaluation
Formatif en cours de séquence · certificatif au terme · critères

## Différenciation
Points de décrochage attendus et réponses prévues

## Non couvert par cette séquence
Attendus laissés à d'autres séquences
```

Terminer par le décompte de traçabilité.

## Suite

Une fois la séquence validée par le prof, proposer de produire les supports leçon par leçon avec la
skill `supports`. Ne pas enchaîner sans validation : une architecture corrigée coûte cinq minutes,
des supports à refaire coûtent une soirée.
