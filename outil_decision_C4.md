# Outil de décision C4 — passer un cas au crible

> **Compagnon de [`grille_decision_C4.md`](grille_decision_C4.md).**
> La grille dit *quelles familles existent selon quel axe*. Cet outil dit
> **comment s'en servir sur un cas qu'on n'a jamais vu**, en 5 minutes.
>
> **Statut** : 🔨 **à outiller** — la partie 2 (la règle de combinaison) est
> **vide exprès**. C'est vous qui l'écrivez en M4-B1, et c'est elle qui
> transforme quatre tableaux en outil utilisable.
>
> Réutilisé en M4-B2 (vision), M7 (architecture), M8 (cas tiré au sort) et
> au **notebook de certification**.

---

## Pourquoi cet outil existe

Prends la grille C4 telle quelle et applique-la à un cas nouveau. Tu obtiens
quatre réponses qui ne s'accordent pas :

- l'axe **volume** te dit « boosting » ;
- l'axe **complexité** te dit « ensemble » ;
- l'axe **explicabilité** te dit « modèle linéaire » ;
- l'axe **latence** te dit « n'importe lequel ».

Quatre réponses, aucune décision. Il manque **la règle qui dit comment les
combiner** — et c'est le cœur de la compétence C4. Un tableau qu'on lit n'est
pas un outil ; un outil, ça produit une sortie.

---

## Partie 1 · Fiche de qualification du cas

> À remplir **avant** de regarder le moindre modèle. 5 questions fermées,
> 3 minutes. Recopie ce bloc dans ton notebook et coche.

**Cas étudié** : ______________________  **Date** : __________

**Q1 · Volume de données exploitables**
`☐ < 1 k` `☐ 1 k – 100 k` `☐ 100 k – 1 M` `☐ > 1 M`
*Exploitables = après nettoyage et exclusion des fuites, pas le nombre de lignes du fichier.*

**Q2 · Nature du signal**
`☐ Linéaire` `☐ Non-linéaire faible` `☐ Non-linéaire forte` `☐ Structurel (image / texte / séquence)`

**Q3 · Contraintes dures** *(plusieurs possibles — c'est la question qui élimine)*
`☐ Justification individuelle obligatoire (réglementaire)`
`☐ Latence maximale imposée : ______ ms`
`☐ Données sensibles / RGPD`
`☐ Pas d'appel à un service externe`
`☐ Aucune contrainte dure`

**Q4 · Budget**
`☐ Train et inférence quasi nuls` `☐ Train modéré` `☐ Train lourd (GPU)` `☐ Facturation à la requête`

**Q5 · Fréquence de réentraînement attendue**
`☐ Jamais` `☐ Trimestrielle` `☐ Mensuelle` `☐ Continu`

---

## Partie 2 · La règle de combinaison · 🔨 *à construire en M4-B1*

> C'est **la** pièce manquante. Sans elle, la grille reste un catalogue.

### 2.1 Quels axes éliminent, quels axes classent ?

Tous les axes n'ont pas le même pouvoir. Certains **barrent** des familles
entières — aucun score ne les rattrape. D'autres **ordonnent** ce qui reste.

| Critère | Éliminatoire ou préférentiel ? | Pourquoi |
|---|---|---|
| Justification individuelle obligatoire | *(à trancher)* | *(à justifier)* |
| Latence maximale imposée | *(à trancher)* | *(à justifier)* |
| Volume de données | *(à trancher)* | *(à justifier)* |
| Complexité du signal | *(à trancher)* | *(à justifier)* |
| Budget | *(à trancher)* | *(à justifier)* |
| Fréquence de réentraînement | *(à trancher)* | *(à justifier)* |

### 2.2 L'ordre d'application

> Écrivez la séquence que vous appliquerez systématiquement. Une phrase par
> étape, à l'impératif.

1. *(à écrire)*
2. *(à écrire)*
3. *(à écrire)*
4. *(à écrire)*

### 2.3 Les cas où la règle ne suffit pas

> Deux familles arrivent à égalité. Qu'est-ce qui départage, et dans quel
> ordre ? *(à construire — vos mesures M4-B1 sont un bon point de départ)*

---

## Partie 3 · La sortie attendue

> Un outil produit toujours la même forme de résultat. Voici la vôtre :
> recopie-la et remplis les blancs.

**Familles éliminées** : ______________ **parce que** ______________

**Candidats retenus** (2 à 3, jamais plus) : ______________

**Protocole de comparaison** : même split (`____________`), mêmes métriques
(`____________`), même préparation.

**Verdict** :
> Je recommande **____________**, qui obtient **____** sur **____**
> (vs **____** pour l'alternative la plus proche).
> Je changerais d'avis si **____________**.

⚠️ Une sortie sans le « je changerais d'avis si » n'est pas une décision
professionnelle : c'est une préférence.

---

## Partie 4 · Le test de validation · 🔨 *à faire en M4-B1*

> Un outil de décision se teste comme du code : on le fait tourner sur un cas
> **dont on connaît déjà la bonne réponse**, et on vérifie qu'il la retrouve.

**Cas de test** : *(à choisir parmi les cas déjà tranchés du parcours)*

| Étape | Résultat |
|---|---|
| Fiche de qualification remplie | *(à faire)* |
| Sortie produite par l'outil | *(à faire)* |
| Décision réellement prise à l'époque | *(à retrouver)* |
| **Verdict du test** | *(à conclure)* |

> **Si l'outil ne retrouve pas une décision qu'on sait juste, c'est l'outil
> qu'on corrige — pas la décision.** Notez ci-dessous ce que le test vous a
> obligé à changer :
>
> *(à remplir)*

---

## 🔁 Évolution

| Version | Moment | Modifications | Auteur·rice |
|---|---|---|---|
| amorce | M4-B1 (avant atelier) | Structure et fiche de qualification posées | Marianne (formatrice) |
| v1.0 | M4-B1 (atelier outillage) | Règle de combinaison + test de validation | Promo Dev-id |

---

*Compagnon de la grille C4 — construit avec la promo Dev-id.*