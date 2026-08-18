# Canevas de rétro-cartographie — M4-B1

> **À remplir d'abord SANS regarder ton notebook.** L'objectif n'est pas d'avoir
> tout juste, c'est de voir ce qui est ancré et ce qui ne l'est pas. C'est ce qui
> est flou qui est intéressant — tu en parles vendredi en RDV.
>
> Temps : 15 min seul·e (mémoire) → 15 min avec ton notebook (compléter) → 15 min en binôme (s'expliquer).

---

## Ton parcours sur M4-B1, en 6 étapes

| # | Étape | Ce que j'ai fait concrètement | Fonction / méthode | Pourquoi cette étape ? | Ce sur quoi j'ai buté |
|---|---|---|---|---|---|
| 1 | **Reprendre la baseline et identifier ses limites** |  |  |  |  |
| 2 | **EDA orientée saisonnalité (+ repérer la fuite de données)** |  |  |  |  |
| 3 | **Découper + introduire la validation croisée** |  |  |  |  |
| 4 | **Benchmarker ≥ 3 familles (même split, mêmes métriques)** |  |  |  |  |
| 5 | **Calculer MAE / RMSE / R² + tableau comparatif** |  |  |  |  |
| 6 | **Verdict + decision_card (sobriété + une menace de robustesse)** |  |  |  |  |

---

## Trois questions courtes

**1. Si on te donnait demain un problème de régression dans un autre domaine (prévoir la consommation électrique d'un bâtiment), quelles étapes resteraient identiques ?**

> _Réponds en 2-3 lignes_

---

**2. Quelle décision de ce benchmark n'es-tu pas sûr·e d'avoir bien tranchée ?**
*(Ex : le type de split — temporel ou aléatoire, le modèle retenu, l'inclusion/exclusion d'une feature, le seuil de « suffisamment bon »…)*

> _Réponds en 2-3 lignes_

---

**3. Y a-t-il un concept que tu as mobilisé sans vraiment le maîtriser ?**
*(Ex : validation croisée, R² vs RMSE, fuite de données, comparabilité des modèles…)*

> _Un seul concept suffit — on peut le retravailler vendredi._

---

## En binôme (15 min, échange croisé)

Vous vous montrez votre canevas et chacun pose ces 3 questions à l'autre :

1. *Ton dataset contenait une fuite (`casual` + `registered`). Comment l'as-tu repérée, et qu'aurait donné ton R² si tu l'avais laissée ?*
2. *Tu as retenu un modèle. Si je te dis « le client veut surtout de l'explicabilité », ta recommandation change-t-elle — et pourquoi ?*
3. *Pourquoi compares-tu tous les modèles sur le **même** split ? Que se passerait-il si chacun avait son propre découpage ?*

Notez en bas du canevas **un point que votre binôme vous a aidé à clarifier**.

> Mon binôme m'a aidé·e à comprendre : ___________________________

---
