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
| [`aide_memoire_M1.pdf`](./aide_memoire_M1.pdf) | **Aide-mémoire M1 (une page) — entraîner & évaluer proprement** — le fil rouge du module : workflow en 7 étapes (EDA → split scellé → pipeline → fit → predict → métrique → verdict), la règle d'or « on n'apprend que sur le train », tableau des métriques, fuite de données, pièges. À imprimer et garder sous les yeux pendant tout M1. |
| [`fiche_pattern_ML_supervise.md`](./fiche_pattern_ML_supervise.md) | **Fiche-pattern du geste ML supervisé** — les étapes d'un pipeline d'apprentissage supervisé (split → entraînement → évaluation), le geste C5 travaillé dès **M1-B1**. Référence de consolidation post-brief. |
| [`galerie_reentrainement/`](./galerie_reentrainement/) | **Étagère async optionnelle post-M1-B1** — 4 notebooks à autonomie croissante (🟢 résolu → 🟠 à trous → 🔴 énoncé seul) pour **rejouer le pattern d'entraînement** sur d'autres domaines et types de problème (classification, régression, multiclasse). Datasets sklearn embarqués. Pas de livrable, pas de note — juste de la répétition pour ancrer C5. À ouvrir après M1-B1. |
| [`galerie_explicabilite/`](./galerie_explicabilite/) | **Étagère async optionnelle dès M6** — expliquer une décision de modèle : importance globale honnête (permutation vs impureté), **SHAP local** traduit en phrase pour le client, détection d'une **variable proxy** (passerelle C2), LIME en contraste. 1 notebook résolu 🟢 + 1 notebook à faire sur ton propre modèle 🟠. Sert la ligne « explicabilité » de la grille C4 et l'arbitrage du cas d'usage. Pas de livrable. |
| [`fiche_pattern_preparation_donnees.md`](./fiche_pattern_preparation_donnees.md) | **Fiche-pattern de la préparation de données** — la séquence audit → nettoyage → encodage → split, et la règle « on n'apprend que sur le train ». Le geste C3 travaillé en **M2-B1**, à re-mobiliser à chaque brief qui touche un dataset. |
| [`cheatsheet_recherche_hyperparametres_cv.md`](./cheatsheet_recherche_hyperparametres_cv.md) | **Cheatsheet recherche d'hyperparamètres + validation croisée** — `GridSearchCV` / `RandomizedSearchCV`, choix des folds, et le piège de la fuite via le preprocessing. À ouvrir dès **M1-B1** (réglage) et re-mobiliser en **M4** (benchmark comparable). |
| [`cheatsheet_sobriete_couts.md`](./cheatsheet_sobriete_couts.md) | **Cheatsheet sobriété et coûts** — ordres de grandeur (temps de train, inférence, empreinte), et comment chiffrer une alternative avant de la proposer. À mobiliser dès qu'une décision engage du calcul : **M4**, M5, M7, M8. |
| [`cheatsheet_metriques.md`](./cheatsheet_metriques.md) | **Cheatsheet métriques d'évaluation** — quelle métrique pour quel problème, comment la lire, le piège à éviter. Transverse **M1 → M9** (classification déséquilibrée en M1, régression M4, exploitation M6). 🎓 sur les métriques du questionnaire certif C4. |
| [`grille_decision_C4.md`](./grille_decision_C4.md) | **Grille de décision C4 — choisir un modèle** — les familles candidates selon 4 axes (volume, complexité du signal, contraintes métier, maintenance), plus la cartographie des modèles et les cas types. Amorcée par la formatrice, **co-construite avec la promo** à partir de **M4-B1** puis enrichie à chaque module (M4-B2, M7, M8). Réutilisée au notebook certif. |
| [`outil_decision_C4.md`](./outil_decision_C4.md) | **Compagnon de la grille C4 — passer un cas au crible** — la fiche de qualification en 5 questions, la règle de combinaison des axes (ce qui élimine vs ce qui classe) et la forme de verdict attendue. À mobiliser dès qu'il faut **trancher** sur un cas nouveau : **M4-B2**, M7, M8 et le cas d'usage certif. |
| [`grille_decision_stockage.md`](./grille_decision_stockage.md) | **Grille de décision — où et comment stocker les données** — le pendant *amont* de la grille C4 (fichier, base relationnelle, entrepôt…). À ouvrir en **M3** au moment de choisir un support de stockage, et à re-mobiliser en M5. |
| [`cheatsheet_mlops_deploiement.md`](./cheatsheet_mlops_deploiement.md) | **Cheatsheet MLOps & déploiement** — la chaîne du commit au réentraînement, et ce que chaque brique DevOps que tu connais déjà devient côté ML. À ouvrir en **M5** (industrialisation) et re-mobiliser en M6. |
| [`fiche_donnees_synthetiques.md`](./fiche_donnees_synthetiques.md) | **Données synthétiques & augmentation** — pourquoi générer (rareté, confidentialité, rééquilibrage, tests), techniques par famille (Faker/SMOTE tabulaire, augmentation image, paraphrase texte), limites et pièges. Exemple SMOTE copiable. Point flash M6. |
| [`fiche_cycle_vie_donnee.md`](./fiche_cycle_vie_donnee.md) | **Fiche cycle de vie et lignage de la donnée** — le flux collecte → prod → feedback → oubli. Utile en **M3** (provenance) et en **M5**, où tu le documentes dans le runbook. |
| [`cheatsheet_cloud_hyperscalers.md`](./cheatsheet_cloud_hyperscalers.md) | **Cheatsheet cloud & hyperscalers** — culture : à quoi correspond, chez AWS/Azure/GCP, chaque brique que tu montes en local. À lire en **M5**, hors temps de brief. |
| [`panorama_modeles_ML.md`](./panorama_modeles_ML.md) | **Carte des familles de modèles** — situer les grandes familles ML/DL, ce que chacune sait faire et ce qu'elle coûte. Compagnon de la grille C4, à ouvrir en **M4** et re-mobiliser en M7-M8. |
| [`panorama_huggingface_hub.md`](./panorama_huggingface_hub.md) | **Carte du Hub HuggingFace** — comment chercher, lire une fiche de modèle et juger si un modèle pré-entraîné convient. À ouvrir en **M4**, réutilisé quand un modèle sur étagère est envisagé. |
| [`panorama_genai_llm_rag_agents.md`](./panorama_genai_llm_rag_agents.md) | **Carte GenAI** — situer LLM / SLM / RAG / agents, *quand c'est pertinent et quand c'est du sur-engineering*. Arbre de décision « ai-je besoin de GenAI ? » + glossaire express. Amorcé en **M4-B2**, **central en M7-M8**. |
| [`canevas_retro_cartographie_M5-B1.md`](./canevas_retro_cartographie_M5-B1.md) | **Canevas de rétro-cartographie M5-B1** — re-dérouler à froid les étapes de la chaîne de production que tu viens de construire. À remplir après **M5-B1**, exploité au RDV du vendredi. |
| [`canevas_retro_cartographie_M6-B1.md`](./canevas_retro_cartographie_M6-B1.md) | **Canevas de rétro-cartographie M6-B1** — re-dérouler à froid le diagnostic de dérive : détection, calibration, triangulation, recommandation. À remplir après **M6-B1**, exploité au RDV du vendredi. |
| [`fiche_feuille_de_route_cas_usage.pdf`](./cas_usage_certif/fiche_feuille_de_route_cas_usage.pdf) | **Plan de vol du cas d'usage certif (Bank Marketing)** — les 2 parties (été : phases 1→5 ; rentrée : 6→8), le calendrier, quelle fiche ouvrir à quel moment. À imprimer et garder sous les yeux pendant tout le chantier d'été. |
| [`canvas-cas-usage-v2.ipynb`](./cas_usage_certif/canvas-cas-usage-v2.ipynb) | **Trame du notebook certif M9** — à utiliser comme grille de référence dès M0, sections ouvertes module par module (cf. tableau « Mobilisation » à l'intérieur). |
| [`matrice-notebook-initiale.ipynb`](./cas_usage_certif/matrice-notebook-initiale.ipynb) | **Matrice initiale du notebook** — version brute distribuée en amont, à mettre en regard du canvas pour comprendre l'évolution attendue. |
| [`journal-de-bord.ipynb`](./cas_usage_certif/journal-de-bord.ipynb) | **Journal quotidien** à tenir au fil du parcours — sera fusionné avec le canvas en M9. |
| [`fiches-revision-certif/`](./fiches-revision-certif/) | **Fiches de révision CISIA (C1, C2, C4, cadre juridique + synthèse anti-confusion)** — construites depuis le référentiel, avec auto-tests à correction dépliable. Pour le questionnaire (15 questions, 45 min) et la partie cadrage du cas d'usage. Version HTML (référence, à ouvrir depuis ton clone) + PDF (hors ligne, impression). À ouvrir dans la dernière ligne droite avant la certif. |

---

## 📄 Série ML — aide-mémoires une page

Une collection de **12 aide-mémoires format une page**, un par grand geste du
parcours, à imprimer et garder sous les yeux. Chaque fiche synthétise un
concept clé : workflow, métriques, pièges, correctif. Elles sont publiées
**au fil des modules** — cette section grandit à chaque nouveau lot.

> 🗺️ **Vue d'ensemble** : [`00_sommaire_serie_ML.pdf`](./00_sommaire_serie_ML.pdf)
> — la carte des 12 fiches en 5 étapes (cadrer → préparer → entraîner → fiabiliser
> → industrialiser), avec les statuts ✅ dispo / 🔜 à venir. **9/12 disponibles
> aujourd'hui** ; les autres arrivent au module indiqué.

Disponibles maintenant : [`fiche_choix_famille_ML.pdf`](./fiche_choix_famille_ML.pdf)
· [`cheatsheet_algos_ML_FR.pdf`](./cheatsheet_algos_ML_FR.pdf)
· [`fiche_preprocessing.pdf`](./fiche_preprocessing.pdf)
· [`aide_memoire_M1.pdf`](./aide_memoire_M1.pdf)
· [`fiche_validation_reglage.pdf`](./fiche_validation_reglage.pdf)
· [`fiche_biais_variance.pdf`](./fiche_biais_variance.pdf)
· [`fiche_desequilibre_classes.pdf`](./fiche_desequilibre_classes.pdf)
· [`fiche_interpretabilite_xai.pdf`](./fiche_interpretabilite_xai.pdf)
· [`fiche_notebook_a_prod.pdf`](./fiche_notebook_a_prod.pdf)
· [`fiche_genai_llm_agents.pdf`](./fiche_genai_llm_agents.pdf)
· [`fiche_techniques_rag.pdf`](./fiche_techniques_rag.pdf).

> 🔜 Les prochaines fiches de la série apparaîtront dans le sommaire dès qu'elles
> sont prêtes. `git pull` en début de module.

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
