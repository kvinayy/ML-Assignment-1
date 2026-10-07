# Machine Learning Assignment 1 — Polynomial Regression

**Student:** Vinay Kusumanchi  
**Roll No:** IMT2023608  
**Course:** Machine Learning

## Overview

This repository contains the implementation and results for Assignment 1 on Polynomial Regression.

Two personalized regression problems were provided:

- **VAR1:** 6 input features (`x1`–`x6`), maximum polynomial degree 10
- **VAR2:** 3 input features (`x1`–`x3`), maximum polynomial degree 20

The objective was to build polynomial regression models, study the effect of polynomial degree, analyze overfitting, evaluate feature subsets, and improve generalization using Ridge and Lasso regularization.

## Methodology

The following workflow was used for both problems:

1. Data loading and integrity checks
2. Exploratory data analysis
3. Linear regression baseline
4. Polynomial degree search using 5-fold cross-validation
5. Feature-subset search
6. Overfitting analysis
7. Ridge and Lasso regularization
8. Final model selection using cross-validation
9. Training diagnostics
10. Test-set prediction and submission validation

All model-selection decisions were based only on the training data because the test labels are hidden.

## Final Models

| Problem | Model | Degree | Features | Alpha | CV MSE | CV R² |
|---|---|---:|---|---:|---:|---:|
| VAR1 | Lasso | 5 | x1–x6 | 0.01 | 0.3600 | 0.9683 |
| VAR2 | Ridge | 11 | x1–x3 | 1.0 | 0.2643 | 0.9942 |

### VAR1

The best unregularized polynomial was degree 4 with a CV MSE of approximately 0.8214.  
After regularization, a degree-5 Lasso model with `alpha = 0.01` achieved a substantially lower CV MSE of approximately 0.3600.

### VAR2

The best unregularized polynomial was degree 8 with a CV MSE of approximately 0.2888.  
A degree-11 Ridge model with `alpha = 1.0` further improved the CV MSE to approximately 0.2643.

## Results

The experiments showed that increasing polynomial degree initially improves performance, but high-degree unregularized polynomials can overfit severely.

For VAR1, the unregularized model became unstable beyond degree 5, while Lasso regularization improved generalization.

For VAR2, the unregularized model performed best around degree 8, while Ridge regularization allowed a higher-degree model to be used without the same level of overfitting.

## Repository Structure

```text
ML-Assignment-1/
│
├── ML_Assignment_Polynomial_Regression.ipynb
├── ML_Assignment_report.pdf
│
├── IMT2023608_train_var1.csv
├── IMT2023608_test_var1.csv
├── IMT2023608_train_var2.csv
├── IMT2023608_test_var2.csv
│
├── figures/
│   ├── ...
│
└── outputs/
    ├── IMT2023608_pred_var1.csv
    ├── IMT2023608_pred_var2.csv
    └── ...
