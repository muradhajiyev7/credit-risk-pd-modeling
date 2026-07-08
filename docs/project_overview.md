# Project Overview

## Problem

Lenders need to estimate the probability that a borrower will default on a loan. A reliable PD model can help rank credit applications, flag risky borrowers, and support portfolio monitoring.

## Objective

Build a binary classification model that estimates default risk using borrower, loan, credit-history, and loan-intent information.

## Dataset

The dataset is included under `data/raw/credit_risk.csv`. It contains borrower, loan, credit-history, loan-intent, and outcome fields for binary credit-risk classification.

The final notebook predicts `Status`, the loan outcome target. The `Default` column is treated as historical default information and used as a feature.

## Deliverables

- Leakage-safe consolidated notebook
- PDF report
- Clean GitHub repository structure
