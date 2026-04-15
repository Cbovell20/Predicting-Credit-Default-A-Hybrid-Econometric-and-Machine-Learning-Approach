# Predicting-Credit-Default-A-Hybrid-Econometric-and-Machine-Learning-Approach
Built a hybrid credit default prediction model combining Logit, Probit,  and XGBoost on 30,000 observations. Engineered features to address  multicollinearity and constructed a weighted ensemble achieving AUC 0.757.  Marginal effects show payment delinquency increases default probability by 5.3 percentage points.

## Overview
This project examines credit card default prediction using a hybrid approach that combines traditional econometric models with machine learning methods. Using 30,000 individual-level observations from the UCI Taiwan Credit Card dataset, the paper estimates and compares a Linear Probability Model (LPM), Logit, Probit, Random Forest, and XGBoost on a common feature set. A weighted ensemble model is then constructed via constrained optimization to maximize predictive performance.

## Key Results

| Model | AUC | Accuracy |
|---|---|---|
| LPM | — | 79.0% |
| Logit | 0.7393 | 79.5% |
| Probit | 0.7397 | 79.6% |
| Random Forest | 0.7482 | 80.7% |
| XGBoost | 0.7534 | 81.2% |
| **Ensemble** | **0.7572** | **81.3%** |

- TOTAL_DELAY and PAY_DIFF_1 are the dominant predictors of default, a one-unit deterioration in recent payment status increases default probability by 5.3 percentage points
- Logit and Probit produce near-identical results, confirming the choice of link function is largely immaterial
- An equal-weighted ensemble of Logit, Probit, and XGBoost outperforms all individual models, suggesting both approaches capture distinct components of default risk


## Methodology
Feature Engineering

- First-differenced payment status: reduces serial correlation across monthly payment variables
- Utilization ratio: BILL_AMT1 / LIMIT_BAL captures credit usage intensity
- TOTAL_DELAY: cumulative sum of positive payment delays across the 6-month window

## Models

- LPM: OLS baseline with HC3 robust standard errors
- Logit / Probit: MLE estimation with average marginal effects
- Random Forest: 100 estimators, sklearn
- XGBoost: gradient boosting with built-in regularization
- Ensemble: constrained weighted average of Logit, Probit, XGBoost; weights optimized via SLSQP to maximize AUC

## Evaluation

- AUC-ROC (primary metric)
- Confusion matrix at 0.30 classification threshold
- AIC / BIC for econometric models
- McFadden Pseudo R²

## Data

Dataset: UCI Default of Credit Card Clients

30,000 observations, 23 features
Binary outcome: default payment next month (1 = default, 0 = no default)
Source: Yeh, I-C., & Lien, C. (2009). Expert Systems with Applications, 36(2), 2473–2480.


## References
- Altman, E. I. (1968). Financial Ratios, Discriminant Analysis and the Prediction of Corporate Bankruptcy. Journal of Finance, 23(4), 589–609.
- Wiginton, J. C. (1980). A Note on the Comparison of Logit and Discriminant Models of Consumer Credit Behavior. Journal of Financial and Quantitative Analysis, 15(3), 757–770.
- Yeh, I-C., & Lien, C. (2009). The Comparisons of Data Mining Techniques for the Predictive Accuracy of Probability of Default of Credit Card Clients. Expert Systems with Applications, 36(2), 2473–2480.
- Breiman, L. (2001). Random Forests. Machine Learning, 45(1), 5–32.
