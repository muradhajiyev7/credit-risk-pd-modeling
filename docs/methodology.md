# Methodology

## Data Preparation

The workflow starts from `data/raw/credit_risk.csv`. Missing values in employment length and interest rate are handled inside the model pipeline to avoid train/test leakage.

## Feature Engineering

Engineered features include:

- Loan-to-income ratio
- Annual interest estimate
- Employment-to-credit-history ratio
- Amount per credit-history length
- Rate-by-amount interaction

## Modeling

The project compares Logistic Regression, Random Forest, Hist Gradient Boosting, and XGBoost. XGBoost produced the strongest held-out performance after randomized hyperparameter tuning.

## Leakage Controls

The final notebook avoids full-dataset target encodings such as pre-split WoE. Preprocessing, imputation, encoding, scaling, feature creation, and model fitting are wrapped in sklearn pipelines.

## Calibration

Sigmoid calibration is used to improve probability-of-default quality. Calibration performance is assessed with Brier score and predicted-vs-actual default rates by decile.
