# Canevas de rétro-cartographie — M5-B1

> **À remplir d'abord SANS regarder ton repo.** L'objectif n'est pas d'avoir tout
> juste, c'est de voir ce qui est ancré et ce qui ne l'est pas. C'est ce qui est
> flou qui est intéressant — tu en parles vendredi en RDV.
>
> Temps : 15 min seul·e (mémoire) → 15 min avec ton repo (compléter) → 15 min en binôme (s'expliquer).

---

## Ton parcours sur M5-B1, en 6 étapes

| # | Étape | Ce que j'ai fait concrètement | Outil / fichier | Pourquoi cette étape ? | Ce sur quoi j'ai buté |
|---|---|---|---|---|---|
| 1 | **Architecturer 3 services (frontend / backend / model)** |  |  |  |  |
| 2 | **Faire démarrer la stack `docker-compose`** |  |  |  |  |
| 3 | **Pipeline CI/CD (tests + contract test + build + push)** |  |  |  |  |
| 4 | **Instrumenter `/metrics` + métriques métier** |  |  |  |  |
| 5 | **Construire le dashboard Grafana (vie / vitesse / qualité)** |  |  |  |  |
| 6 | **Rédiger le runbook d'astreinte (4 procédures)** |  |  |  |  |

---

## Trois questions courtes

**1. Si on te demandait demain de déployer un autre modèle (un classifieur d'images), quelles briques de ta chaîne resteraient identiques ?**

> _Réponds en 2-3 lignes_

---

**2. Quelle décision d'architecture ou de CI/CD n'es-tu pas sûr·e d'avoir bien tranchée ?**
*(Ex : ce que fait le contract test, le découpage des 3 services, les métriques métier choisies, le seuil d'une procédure du runbook…)*

> _Réponds en 2-3 lignes_

---

**3. Y a-t-il un concept ou un outil que tu as utilisé sans vraiment le comprendre ?**
*(Ex : contract test du modèle, endpoint `/metrics` Prometheus, healthcheck, push vers GHCR…)*

> _Un seul concept suffit — on peut le retravailler vendredi._

---

## En binôme (15 min, échange croisé)

Vous vous montrez votre travail et chacun pose ces 3 questions à l'autre :

1. *Quelle est la différence entre le **contract test** du modèle et l'**évaluation continue** (M5-B2) ? Lequel bloque la release, et sur quel critère ?*
2. *Ton dashboard répond à 3 questions (en vie / rapide / prédit bien). Montre-moi le **panel** qui répond à « prédit-il toujours bien ? » — et d'où vient sa donnée.*
3. *Une procédure de ton runbook se déclenche : à quel **seuil** précis, et quelle est la **première action** ? Un SRE qui ne connaît pas le ML la comprendrait-il ?*

Notez en bas du canevas **un point que votre binôme vous a aidé à clarifier**.

> Mon binôme m'a aidé·e à comprendre : ___________________________

---
