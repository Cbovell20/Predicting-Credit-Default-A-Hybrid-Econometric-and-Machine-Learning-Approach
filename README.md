# Predicting-Credit-Default-A-Hybrid-Econometric-and-Machine-Learning-Approach
Built a hybrid credit default prediction model combining Logit, Probit,  and XGBoost on 30,000 observations. Engineered features to address  multicollinearity and constructed a weighted ensemble achieving AUC 0.757.  Marginal effects show payment delinquency increases default probability by 5.3 percentage points.

## Overview
This project examines credit card default prediction using a hybrid approach that combines traditional econometric models with machine learning methods. Using 30,000 individual-level observations from the UCI Taiwan Credit Card dataset, the paper estimates and compares a Linear Probability Model (LPM), Logit, Probit, Random Forest, and XGBoost on a common feature set. A weighted ensemble model is then constructed via constrained optimization to maximize predictive performance.

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
