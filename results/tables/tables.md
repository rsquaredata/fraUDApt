
# Résumé des résultats expérimentaux

---

## 1. Hyper-paramètres optimisés (GridSearch)

| Modèle | Hyper-paramètres optimisés |
|------|----------------------------|
| Régression Logistique | C = 7.7426, penalty = l2 |
| Random Forest | n_estimators = 600, max_depth = 50, min_samples_split = 2 |
| XGBoost | learning_rate = 0.1, max_depth = 9 |
| SVM | C = 10, kernel = linear |
| k-NN | n_neighbors = 5, weights = distance |

---

## 2. Performances comparées des modèles (jeu de test)

| Modèle | Recall | Précision | Score F1 |
|------|--------|-----------|----------|
| Régression Logistique | 0.49 | 0.82 | 0.62 |
| Random Forest | 0.65 | 0.91 | 0.76 |
| XGBoost | 0.68 | 0.91 | 0.78 |
| SVM | 0.48 | 0.80 | 0.60 |
| k-NN | 0.51 | 0.82 | 0.63 |

---

## 3. Impact des stratégies de gestion du déséquilibre (XGBoost)

| Approche | Recall | Précision | Score F1 |
|--------|--------|-----------|----------|
| Baseline (XGBoost standard) | 0.68 | 0.91 | 0.78 |
| Under-sampling | 0.88 | 0.52 | 0.66 |
| SMOTE | 0.71 | 0.85 | 0.78 |
| Class Weighting | 0.83 | 0.71 | 0.77 |

---

## 4. Résultats en adaptation de domaine (UDA)

Performances mesurées sur le **domaine cible** (évaluation Oracle).

| Méthode | Recall (T) | Précision (T) | Score F1 (T) |
|--------|-------------|---------------|--------------|
| Source-only (Baseline) | 0.72 | 0.43 | 0.54 |
| Re-weighting | 0.70 | 0.44 | 0.54 |
| CORAL | 0.62 | 0.54 | 0.58 |
| Re-weighting + CORAL | 0.59 | 0.53 | 0.56 |

---

