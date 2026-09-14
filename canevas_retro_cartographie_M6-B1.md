# Canevas de rétro-cartographie — M6-B1

> **À remplir d'abord SANS regarder ton notebook.** L'objectif n'est pas d'avoir
> tout juste, c'est de voir ce qui est ancré et ce qui ne l'est pas. C'est ce qui
> est flou qui est intéressant — tu en parles vendredi en RDV.
>
> Temps : 15 min seul·e (mémoire) → 15 min avec ton notebook (compléter) → 15 min en binôme (s'expliquer).

---

## Ton parcours sur M6-B1, en 6 étapes

| # | Étape | Ce que j'ai fait concrètement | Fonction / méthode | Pourquoi cette étape ? | Ce sur quoi j'ai buté |
|---|---|---|---|---|---|
| 1 | **Explorer les données de prod (distributions feature par feature)** |  |  |  |  |
| 2 | **Détecter la dérive (PSI, KS, Chi²)** |  |  |  |  |
| 3 | **Vérifier la calibration du modèle** |  |  |  |  |
| 4 | **Diagnostiquer : data drift vs concept drift** |  |  |  |  |
| 5 | **Étendre le dashboard Grafana (panels de dérive)** |  |  |  |  |
| 6 | **Rédiger la note de recommandation chiffrée** |  |  |  |  |

---

## Trois questions courtes

**1. Si un autre modèle en prod se mettait à dériver (un modèle de recommandation), quelles étapes de ton diagnostic resteraient identiques ?**

> _Réponds en 2-3 lignes_

---

**2. Quelle conclusion de ton diagnostic n'es-tu pas sûr·e d'avoir bien étayée ?**
*(Ex : trancher data drift vs concept drift, le seuil PSI retenu, la remédiation recommandée, l'estimation du coût…)*

> _Réponds en 2-3 lignes_

---

**3. Y a-t-il un concept que tu as mobilisé sans vraiment le maîtriser ?**
*(Ex : PSI, calibration / reliability diagram, distinction data drift / concept drift, pourquoi l'AUC stable révèle un data drift…)*

> _Un seul concept suffit — on peut le retravailler vendredi._

---

## En binôme (15 min, échange croisé)

Vous vous montrez votre travail et chacun pose ces 3 questions à l'autre :

1. *Comment as-tu **distingué** data drift et concept drift ? Quelle preuve chiffrée appuie ton verdict (et pas juste « je pense que ») ?*
2. *Tu recommandes une remédiation. Pourquoi celle-là **plutôt** qu'un réentraînement complet (ou qu'un simple ajustement de seuil) ? Est-elle **proportionnée** ?*
3. *Le PSI sur une feature vaut 0.18. C'est « stable », « suspect » ou « dérive » — et qu'est-ce que tu en fais concrètement ?*

Notez en bas du canevas **un point que votre binôme vous a aidé à clarifier**.

> Mon binôme m'a aidé·e à comprendre : ___________________________

---
