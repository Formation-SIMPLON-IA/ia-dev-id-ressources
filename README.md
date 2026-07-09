# Ressources publiques — Parcours IA Dev-id

> Repo `ia-dev-id-ressources` — ressources transverses, partagées entre tous les
> briefs du parcours **« Concevoir et implémenter une solution d'IA »**
> (CISIA / OPCO ATLAS, Parcours 2 — Professionnels IT).

Ce repo est complémentaire des repos de briefs `ia-dev-id-parcours-*`, qui
contiennent chacun le squelette de code et les mini-cours d'un brief.

> 📌 Ce repo grandit **au rythme des modules**. Ce qui est présent ci-dessous
> couvre le **socle transverse + la transition M0 → M1**. Les fiches-patterns,
> cheatsheets, canevas de consolidation et étagères async de chaque module
> seront ajoutés **quand la promo ouvrira le module concerné**. Fais `git pull`
> au début de chaque module.

---

## 📁 Contenu

| Fichier | Quand le mobiliser ? |
|---|---|
| [`00_competences_referentiels.md`](./00_competences_referentiels.md) | **Source de vérité des compétences** — 9 C techniques (CISIA) + 9 CT transversales (OPCO ATLAS) avec intitulés officiels, niveaux Simplon et mapping par module. À garder sous la main pendant tout le parcours. |
| [`glossaire_IA.md`](./glossaire_IA.md) | **Glossaire vivant** — vocabulaire data/IA démystifié (1-2 lignes/terme), tagué par module, 🎓 sur les termes du questionnaire C1/C2/C4. À garder ouvert dès M0, enrichi à chaque module. |
| [`recap_M0_vers_M1.md`](./recap_M0_vers_M1.md) | **Pont entre M0 et M1** — cycle ML, technos vues vs à venir, compétences cochées. À lire entre la fin de M0 et le démarrage de M1. |
| [`decouverte_pandas.ipynb`](./decouverte_pandas.ipynb) | **Découverte express (~20 min, hands-on)** — lire et explorer un tableau : `read_csv`, `head`/`info`, `describe`, `value_counts`, `groupby`, une visu. Données FastIA (tickets support). À *faire tourner* avant M1 — c'est le *contenant* (la table) avant le modèle. |
| [`decouverte_scikit_learn.ipynb`](./decouverte_scikit_learn.ipynb) | **Découverte express (~15 min, hands-on)** — la grammaire scikit-learn `fit`/`predict`/`score` sur un petit dataset embarqué. À *faire tourner* une fois avant M1 si tu n'as jamais entraîné de modèle. Ne fait **pas** la vraie démarche (ça, c'est M1-B1). À faire **après** le notebook pandas. |
| [`conventions_commit.md`](./conventions_commit.md) | **Format des messages de commit** — type, scope, description + exemples. À garder ouvert pendant les briefs avec rendu Git. |
| [`cheatsheet_git_template_workflow.md`](./cheatsheet_git_template_workflow.md) | **Workflow « Use this template »** — le cycle repo template → repo perso → clone → commits, étape par étape. Démarre en **M1** (premier brief de code). À garder ouvert au démarrage de chaque brief de code. |
b| [`aide_memoire_M1.pdf`](./aide_memoire_M1.pdf) | **Aide-mémoire M1 (une page) — entraîner & évaluer proprement** — le fil rouge du module : workflow en 7 étapes (EDA → split scellé → pipeline → fit → predict → métrique → verdict), la règle d'or « on n'apprend que sur le train », tableau des métriques, fuite de données, pièges. À imprimer et garder sous les yeux pendant tout M1. |
| [`fiche_pattern_ML_supervise.md`](./fiche_pattern_ML_supervise.md) | **Fiche-pattern du geste ML supervisé** — les étapes d'un pipeline d'apprentissage supervisé (split → entraînement → évaluation), le geste C5 travaillé dès **M1-B1**. Référence de consolidation post-brief. |
| [`galerie_reentrainement/`](./galerie_reentrainement/) | **Étagère async optionnelle post-M1-B1** — 4 notebooks à autonomie croissante (🟢 résolu → 🟠 à trous → 🔴 énoncé seul) pour **rejouer le pattern d'entraînement** sur d'autres domaines et types de problème (classification, régression, multiclasse). Datasets sklearn embarqués. Pas de livrable, pas de note — juste de la répétition pour ancrer C5. À ouvrir après M1-B1. |
| [`cheatsheet_metriques.md`](./cheatsheet_metriques.md) | **Cheatsheet métriques d'évaluation** — quelle métrique pour quel problème, comment la lire, le piège à éviter. Transverse **M1 → M9** (classification déséquilibrée en M1, régression M4, exploitation M6). 🎓 sur les métriques du questionnaire certif C4. |
| [`canvas-cas-usage-v2.ipynb`](./canvas-cas-usage-v2.ipynb) | **Trame du notebook certif M9** — à utiliser comme grille de référence dès M0, sections ouvertes module par module (cf. tableau « Mobilisation » à l'intérieur). |
| [`matrice-notebook-initiale.ipynb`](./matrice-notebook-initiale.ipynb) | **Matrice initiale du notebook** — version brute distribuée en amont, à mettre en regard du canvas pour comprendre l'évolution attendue. |
| [`journal-de-bord.ipynb`](./journal-de-bord.ipynb) | **Journal quotidien** à tenir au fil du parcours — sera fusionné avec le canvas en M9. |

---

## 📄 Série ML — aide-mémoires une page

Une collection de **12 aide-mémoires format une page**, un par grand geste du
parcours, à imprimer et garder sous les yeux. Chaque fiche synthétise un
concept clé : workflow, métriques, pièges, correctif. Elles sont publiées
**au fil des modules** — cette section grandit à chaque nouveau lot.

| Fiche | Titre | Module | Statut |
|---|---|---|---|
| 5/12 | [`aide_memoire_M1.pdf`](./aide_memoire_M1.pdf) — Entraîner & évaluer un modèle proprement | M1 | ✅ disponible |
| autres | Publiées au rythme des modules | M0 → M9 | 🔜 à venir |

> 🔜 Les prochaines fiches de la série apparaîtront ici et dans le tableau
> « Contenu » ci-dessus dès qu'elles sont prêtes. `git pull` en début de module.

---

## 🚀 Utilisation pour les apprenants

1. **Clone ce repo une fois**, ou utilise les liens directs partagés par la formatrice.
2. **Garde [`00_competences_referentiels.md`](./00_competences_referentiels.md)
   ouvert dès le démarrage** — il te dit où tu vas et quelles compétences tu
   travailles à quel niveau.
3. **Récupère le canvas** dans ton repo perso au démarrage de M0 — tu l'enrichis
   au fur et à mesure que les modules avancent (sections à ouvrir selon le module
   en cours).
4. **Tiens le journal de bord** au quotidien : 1 entrée par jour de formation,
   pas plus de 10 lignes — actions du jour, difficultés, prochain pas.
5. **En M9** : fusion automatique du canvas et du journal en un seul notebook certif.

---

## 🔄 Mise à jour

Ce repo évolue **module par module**. `git pull` au début de chaque module pour
récupérer les nouvelles fiches, cheatsheets et canevas de consolidation.

---

## 📜 Licence & statut

Repo de travail pédagogique, usage interne formation Dev-id (parcours CISIA
Pro IT). Pour toute réutilisation extérieure, contacter la formatrice.