# Results

## Final Model

The final model is a tuned XGBoost classifier with a validation-selected threshold.

| Metric | Value |
|---|---:|
| ROC-AUC | 0.9477 |
| PR-AUC | 0.8994 |
| Accuracy | 92.70% |
| Precision | 91.06% |
| Recall | 73.77% |
| F1-score | 81.51% |
| KS Statistic | 0.7572 |

## Interpretation

Important predictive factors include home ownership, loan-to-income ratio, interest rate, loan intent, prior default history, income, and percent income used by the loan.

## Calibration

Sigmoid calibration improved probability quality, reducing Brier score from about `0.0704` to about `0.0597`.

## Business Use

The model can support manual review prioritization, risk-based pricing, credit policy design, and portfolio risk monitoring. It should be deployed with human oversight and periodic monitoring.
