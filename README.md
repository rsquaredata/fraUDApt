# Fraud Detection under Class Imbalance and Domain Shift

This repository contains the experimental code associated with a Master 2 SISE project (*Statistique et Informatique pour la Science des Données*, Université Lumière Lyon 2),
focused on **fraud detection in imbalanced settings** and **unsupervised domain adaptation (UDA)**.

The project investigates two complementary challenges commonly encountered in real-world transactional fraud detection:
- severe **class imbalance**, where fraudulent events are rare,
- **distribution shift** between historical labeled data and future unlabeled data.

---

## Project structure

```text
.
├── notebooks/
│   ├── 01_supervised_learning_imbalanced_fraud.ipynb
│   └── 02_unsupervised_domain_adaptation.ipynb
│
├── results/
│
├── README.md
├── environment.yml
└── .gitignore
```

Only two notebooks are used in this project:
- **Notebook 01**: supervised learning under class imbalance
- **Notebook 02**: unsupervised domain adaptation

This separation reflects the conceptual structure of the report.

---

## Data availability

The datasets used in this project are **not included in this repository**.

All data originate from the **SCDA (Shifted Credit Card Dataset for Domain Adaptation)** repository: https://github.com/lmuxz/SCDA

The data are kept external to ensure compliance with licensing constraints and to avoid versioning large files.

---

## Data download and setup

To reproduce the experiments, clone the SCDA repository separately:

```bash
git clone https://github.com/lmuxz/SCDA.git
```

The datasets are located in:

```text
SCDA/data/
```

The experiments rely in particular on:
- `kaggle_source_cate_0` (source domain, labeled)
- `kaggle_target_cate_0` to `kaggle_target_cate_3` (target domains)

A recommended local structure is:

```text
project-root/
├── data/
│   └── SCDA/
│       └── data/
│           ├── kaggle_source_cate_0
│           └── kaggle_target_cate_*
```

The `data/` directory is intentionally excluded from version control via `.gitignore`.

Paths to the datasets must be updated accordingly in the notebooks.

---

## Notebook overview

### 01 — Supervised learning under class imbalance

This notebook addresses fraud detection in a **stationary supervised setting**.

Main steps:
- exploratory analysis of class imbalance,
- comparison of multiple classifiers:
  - Logistic Regression
  - Random Forest
  - XGBoost
  - Support Vector Machine
  - k-Nearest Neighbors
- hyperparameter optimization via stratified cross-validation,
- evaluation using recall, precision, F1-score and PR-oriented metrics,
- comparison of imbalance-handling strategies:
  - under-sampling,
  - SMOTE,
  - class weighting.

The goal is to identify a robust baseline model for fraud detection under imbalance.

---

### 02 — Unsupervised domain adaptation

This notebook investigates the **generalization gap induced by distribution shift**.

Main steps:
- definition of source and target domains,
- evaluation of a source-only baseline,
- implementation of unsupervised domain adaptation methods:
  - instance re-weighting (importance weighting),
  - CORAL (Correlation Alignment),
  - combined strategies,
- oracle evaluation on the target domain (labels used only for assessment, never during adaptation).

The focus is on preserving detection performance when labels are unavailable in the target domain.

---

## Requirements

Once the environment is created and the data paths are configured, the experiments can be reproduced by running the notebooks in numerical order.

The project relies on standard Python scientific libraries.

A non-exhaustive list includes:
- `numpy`
- `pandas`
- `scikit-learn`
- `xgboost`
- `imbalanced-learn`
- `matplotlib`
- `seaborn`

All dependencies are listed in `environment.yml`.

```bash
conda env create -f environment.yml
conda activate fraudapt
```

---

## Reproducibility

To ensure reproducibility:
- all random processes use a fixed `random_state`,
- stratified cross-validation is applied where relevant,
- no data leakage occurs between source and target domains,
- target labels are never used during adaptation (oracle evaluation only).

---

## Academic context

This repository accompanies a written report submitted as part of the **Master 2 SISE (2025–2026)** program at Université Lumière Lyon 2.

The work is intended for academic and educational purposes.

---

## Authors

Rina Razafimahefa • Anne-Camille Vial
