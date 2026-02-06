# Experimental Results Summary

---

## 1. Optimized Hyperparameters (GridSearch)

| Model | Optimized hyperparameters |
|------|---------------------------|
| Logistic Regression | C = 7.7426, penalty = l2 |
| Random Forest | n_estimators = 600, max_depth = 50, min_samples_split = 2 |
| XGBoost | learning_rate = 0.1, max_depth = 9 |
| SVM | C = 10, kernel = linear |
| k-NN | n_neighbors = 5, weights = distance |

---

## 2. Model Performance Comparison (Test Set)

| Model | Recall | Precision | F1-score |
|------|--------|-----------|----------|
| Logistic Regression | 0.49 | 0.82 | 0.62 |
| Random Forest | 0.65 | 0.91 | 0.76 |
| XGBoost | 0.68 | 0.91 | 0.78 |
| SVM | 0.48 | 0.80 | 0.60 |
| k-NN | 0.51 | 0.82 | 0.63 |

---

## 3. Impact of Class Imbalance Strategies (XGBoost)

| Approach | Recall | Precision | F1-score |
|--------|--------|-----------|----------|
| Baseline (standard XGBoost) | 0.68 | 0.91 | 0.78 |
| Under-sampling | 0.88 | 0.52 | 0.66 |
| SMOTE | 0.71 | 0.85 | 0.78 |
| Class weighting | 0.83 | 0.71 | 0.77 |

---

## 4. Domain Adaptation Results (UDA)

Performance measured on the **target domain** using an *oracle* evaluation.

| Method | Recall (T) | Precision (T) | F1-score (T) |
|--------|-------------|---------------|--------------|
| Source-only (Baseline) | 0.72 | 0.43 | 0.54 |
| Re-weighting | 0.70 | 0.44 | 0.54 |
| CORAL | 0.62 | 0.54 | 0.58 |
| Re-weighting + CORAL | 0.59 | 0.53 | 0.56 |

---

