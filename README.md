# Credit Risk Probability of Default Modeling

![Python](https://img.shields.io/badge/Python-3.11-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-Gradient%20Boosting-green)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

An end-to-end Probability of Default (PD) modeling project for credit-risk classification. The project estimates whether a borrower is likely to default on a loan using leakage-safe preprocessing, model comparison, tuned XGBoost, validation-based threshold selection, and probability calibration.

## Overview

This project was completed as a credit-risk modeling assessment during an internship-style workflow. The objective was to build a binary classification model that estimates loan default risk and produces useful probability-of-default scores.

The final notebook improves the original workflow by correcting the target definition, using `Status` as the loan outcome target and keeping prior `Default` history as a predictor. It also avoids target leakage by fitting preprocessing and feature engineering only inside sklearn pipelines.

## Key Results

Final tuned XGBoost performance on the held-out test set:

| Metric | Value |
|---|---:|
| ROC-AUC | 0.9477 |
| PR-AUC | 0.8994 |
| Accuracy | 92.70% |
| Precision | 91.06% |
| Recall | 73.77% |
| F1-score | 81.51% |
| KS Statistic | 0.7572 |

Probability calibration improved Brier score from about `0.0704` to about `0.0597` with sigmoid calibration.

## What This Project Covers

- Data cleaning and missing-value handling
- Exploratory data analysis
- Feature engineering for credit-risk signals
- Logistic Regression baseline
- Tree-based model comparison
- XGBoost hyperparameter tuning
- Validation-based threshold selection
- ROC-AUC, PR-AUC, precision, recall, confusion matrix, and KS statistic
- Feature importance interpretation
- PD calibration and decile analysis

## Repository Structure

```text
credit-risk-pd-modeling/
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── credit_risk_pd_modeling_final.ipynb
├── data/
│   └── raw/
│       └── credit_risk.csv
├── docs/
│   ├── project_overview.md
│   ├── methodology.md
│   └── results.md
├── reports/
│   └── credit_risk_pd_modeling_report.pdf
└── outputs/
    └── .gitkeep
```

## Dataset

The dataset is included under `data/raw/credit_risk.csv`. It contains borrower, loan, credit-history, loan-intent, and outcome fields used for PD modeling.

Important target detail:

- `Status`: final loan outcome target used for modeling
- `Default`: prior default history used as an input feature

## Models Tested

- Logistic Regression
- Random Forest
- Hist Gradient Boosting
- XGBoost baseline
- Tuned XGBoost final model

## How to Run

```bash
git clone https://github.com/muradhajiyev7/credit-risk-pd-modeling.git
cd credit-risk-pd-modeling
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/credit_risk_pd_modeling_final.ipynb
```

The notebook includes visible outputs, charts, and final metrics. To rerun the full hyperparameter search, set:

```python
RUN_RANDOM_SEARCH = True
```

For a faster rerun using the stored best parameters, keep:

```python
RUN_RANDOM_SEARCH = False
```

## Business Value

The final model can support credit-risk teams by ranking loan applications, prioritizing manual review, supporting risk-based pricing, and monitoring portfolio default risk. It should be used as decision-support tooling with human oversight, fairness monitoring, and periodic retraining.

## Deliverables

- Final notebook: `notebooks/credit_risk_pd_modeling_final.ipynb`
- Summary report: `reports/credit_risk_pd_modeling_report.pdf`
