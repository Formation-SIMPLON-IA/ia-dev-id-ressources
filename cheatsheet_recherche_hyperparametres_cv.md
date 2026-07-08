# Cheatsheet — recherche d'hyperparamètres + validation croisée

> **Ressource transverse — mobilisée à partir de M1, approfondie en M6.** Réf rapide,
> pas un cours : *comment régler des hyperparamètres sans se mentir, et à quel coût*.
>
> Version condensée du mini-cours bonus `06_RechercheHyperparam_CV_essentiel.md` du repo
> `ia-dev-id-parcours-m1-b1`. À garder ouverte en révision. Compagnon du
> [`glossaire_IA.md`](./glossaire_IA.md).

---

## 0. Le schéma mental (tout en découle)

Le **test set n'est touché qu'une seule fois, tout à la fin**. Tout le réglage se fait
sur le train, via validation croisée.

```
train ──▶ recherche + validation croisée   (on explore, on compare)
                │
                ▼
           best_params_         (le meilleur jeu SELON la CV)
                │
                ▼
     modèle final réentraîné sur TOUT le train
                │
                ▼
           test  ◀── UNE seule fois, pour le verdict
```

> 💡 **La phrase à retenir** : le tuning ne rend pas le modèle meilleur « en soi »,
> il **réduit la variance du choix des paramètres** sous contrainte des données. Ce
> n'est pas de la magie, c'est de la sélection prudente.

---

## 1. Validation croisée (CV) — pourquoi et comment

On ne règle **jamais** les hyperparamètres sur le test 🎓 : sinon on optimise sur les
données d'évaluation → scores optimistes et faux. La CV résout ça :

- On découpe le **train** en `k` plis (typiquement 5), on entraîne sur `k-1`, on valide
  sur le dernier, on **répète `k` fois**, on **moyenne** les scores.
- Déséquilibre → **`StratifiedKFold`** (même proportion de classes dans chaque pli).
- La CV est **plus stable qu'un holdout simple**, **mais garde une variance propre** :
  le score CV est une **estimation, pas la vérité**. Donc `best_params_` n'est pas un
  absolu, c'est **le meilleur jeu sous le bruit de la CV et l'espace de recherche
  exploré** (deux dépendances : les plis *et* les plages testées).
- **Non-déterminisme à assumer** : relancer la recherche avec un autre `random_state`
  ou un autre découpage CV peut désigner un gagnant **légèrement différent**. Ne pas
  sur-interpréter un écart de 0,2 point — regarder l'ordre de grandeur, pas la 3ᵉ décimale.

---

## 2. Grid vs Random — choisir la méthode

| Méthode | Principe | Quand |
|---|---|---|
| **Réglage manuel** | 2-3 jeux à la main | Premiers pas, comprendre les leviers. Toujours commencer là. |
| **`GridSearchCV`** | balaye **toutes** les combinaisons (produit cartésien) | Espace **petit et discret** (< 30 combos), debug, analyse systématique |
| **`RandomizedSearchCV`** | échantillonne `n_iter` combinaisons dans des plages | **Réflexe par défaut** dès que l'espace grandit |
| Optimisation bayésienne (Optuna) | 🔭 culture, **M6** | Espaces énormes, entraînements coûteux — **sur-dimensionné en M1** |

> 💡 **Explosion combinatoire** : 4 hyperparamètres × 4 valeurs = 256 combos × 5 folds
> = **1280 entraînements**. C'est pour ça que le random gagne à grande échelle.
>
> ⚠️ **Ne pas sur-généraliser** : « random > grid » n'est vrai que **quand l'espace est
> grand**. Sur un petit espace discret, grid reste pertinent (exhaustif + reproductible).
> Pourquoi random marche si bien ? Parce que les hyperparamètres **ne sont pas
> indépendants** : le tirage explore des **régions cohérentes** au lieu des nœuds
> rigides d'une grille (Bergstra & Bengio, 2012).

---

## 3. `scoring` — tu optimises ce que tu déclares 🎓

La recherche maximise **la métrique que tu lui passes**. Mais une métrique est un
**proxy d'une décision métier**, jamais l'objectif :

| `scoring` | Ce qu'il privilégie | Message métier implicite |
|---|---|---|
| `accuracy` | % correct global | « j'ignore le coût asymétrique d'une erreur » → **piège en déséquilibre** |
| `f1_macro` | équilibre **strict** des classes | « la classe minoritaire compte autant » |
| `f1_weighted` | pondéré par la fréquence | « moins sévère sur la minoritaire » |
| `roc_auc` | qualité du **classement** des probas | « je veux bien ordonner les risques » (suppose des `predict_proba` exploitables) |

> 💡 En doute sur un cas déséquilibré (scoring crédit, fraude, panne) : **`f1_macro`**.
> `scoring="accuracy"` sur du déséquilibre → modèle qui prédit tout le temps la classe
> majoritaire.

---

## 4. Le vrai critère : coût vs gain

Optimiser est une **décision économique**, pas un réflexe automatique.

```
   gain de F1 faible  +  coût CPU élevé   →   NE PAS tuner (garder le défaut)
   gain de F1 net     +  coût acceptable  →   tuner et documenter le choix
```

- Toujours reporter dans `experiments.md` : **score par défaut ET score tuné**, avec
  le temps passé. Sans le défaut, impossible de juger si ça valait le coup.
- **Piège cognitif** : « plus je tune, meilleur ce sera » → **faux**. Au-delà d'un point,
  gain marginal nul **et** sur-ajustement indirect à la CV. Savoir s'arrêter fait partie
  du métier.

---

## 5. Pièges fréquents

| Piège | Conséquence | Réflexe |
|---|---|---|
| `scoring="accuracy"` en déséquilibre | modèle inutile qui « gagne » | `f1_macro` / `roc_auc` |
| Grille trop large | recherche interminable | `RandomizedSearchCV`, réduire l'espace |
| `.fit()` sur train **+ test** | fuite majeure | recherche sur le **train seul** |
| Préprocessing **avant** la CV | fuite subtile | encapsuler dans un `Pipeline` |
| `KFold` simple en déséquilibre | plis instables | `StratifiedKFold` |
| `n_iter` trop petit (random) | espace sous-exploré | monter `n_iter` (≥ 20-30) |
| Score tuné sans le défaut | impossible d'arbitrer | comparer **toujours** au modèle par défaut |
| `best_params_` sur une **borne** de la grille | l'optimum est au-delà | élargir la plage |

---

## 6. Snippet minimal (RandomizedSearchCV propre)

```python
from scipy.stats import randint
from sklearn.model_selection import RandomizedSearchCV, StratifiedKFold
from sklearn.ensemble import RandomForestClassifier

cv = StratifiedKFold(n_splits=5, shuffle=True, random_state=42)
search = RandomizedSearchCV(
    RandomForestClassifier(random_state=42, n_jobs=-1),
    param_distributions={
        "n_estimators": randint(100, 400),
        "max_depth": randint(5, 20),
        "min_samples_leaf": randint(1, 20),
        "class_weight": ["balanced", None],
    },
    n_iter=30, scoring="f1_macro", cv=cv,
    random_state=42, n_jobs=-1, refit=True,
)
search.fit(X_train, y_train)     # TRAIN uniquement
# search.best_estimator_ évalué UNE fois sur X_test → verdict
```

---

## 7. 🔭 Pont vers M6

À force de comparer beaucoup de modèles sur les **mêmes** plis de CV, on finit par
**sur-ajuster la validation elle-même** (score CV optimiste) — c'est un **biais de
sélection**. La parade — la *validation croisée imbriquée* (nested CV) — sépare la boucle
qui **choisit** les hyperparamètres de celle qui **estime** la performance, pour ne pas
optimiser sur la CV elle-même. On la voit en **M6**. En M1, il suffit de le savoir et de
garder le test **vraiment** pour la fin.

---

## 8. À retenir

- **Le test ne sert qu'une fois, à la fin.** Tout le réglage passe par la CV sur le train.
- **CV = estimation bruitée** : `best_params_` n'est pas un absolu.
- **`RandomizedSearchCV` par défaut** dès que l'espace grandit ; **grid** reste bon en
  petit/discret. Pas de dogme.
- **La métrique (`scoring`) est un choix métier**, pas un détail — `f1_macro` en déséquilibre.
- **Optimiser est une décision coût/gain** : comparer toujours au modèle par défaut,
  et savoir s'arrêter.
