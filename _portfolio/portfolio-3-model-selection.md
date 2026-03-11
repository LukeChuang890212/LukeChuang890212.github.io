---
title: "Model Selection & Regularization: Chemical Manufacturing Yield Prediction"
excerpt: "Systematic comparison of variable selection methods including subset selection, PCR, Lasso, and Ridge regression on high-dimensional manufacturing data.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Two analysis tasks were carried out:

- **Chemical Manufacturing Process Data** (from R `AppliedPredictiveModeling` package): 177 samples with 57 predictors (12 biological material measurements + 45 manufacturing process measurements) and 1 response variable (product yield). Observations with missing values were removed, and predictors were renamed (B1–B12, P1–P45) for convenience. A 90/10 train-test split was used.
- **Outlier-Robust Estimation Problem**: A contaminated dataset used to compare standard vs. robust estimators of population standard deviation via nonparametric bootstrap.

## Exploratory Data Analysis (EDA)

- Summary statistics revealed large scale differences among predictors, necessitating standardization for fair comparison.
- Correlation plot showed high correlations among many predictors, supporting dimensionality reduction.
- Few predictors showed strong marginal association with Yield, consistent with the sparsity principle.
- Skewed distributions were identified in predictors P12, P28, P40, P41, and P43; outliers detected in P25–P31.

## Methods

Six variable selection procedures were systematically compared, all evaluated via **5-fold cross-validation**:

1. **Forward Selection** — identified 5 optimal predictors (P2, P9, P17, P33, P34)
2. **Backward Selection** — identified 3 optimal predictors (P13, P15, P33)
3. **Best Subset Selection** — identified 5 optimal predictors (B3, P13, P15, P33, P34)
4. **Principal Component Regression (PCR)** — 6 PCs selected; composition analyzed via loadings
5. **Lasso Regression** — 12 predictors initially selected, refined to 7 after removing non-significant terms
6. **Ridge Regression** — coefficient magnitude-based selection, refined to 3 predictors (P34, P36, P37)

Additionally, **nonparametric bootstrap** (B = 10,000) was used to compare the sampling distributions of the standard estimator vs. the MAD-based robust estimator of standard deviation.

## Results & Interpretation

- The revised Lasso model (Model 5) achieved the best cross-validation performance with the smallest and most stable test MSE, while PCR (Model 4) had the lowest test-set RMSE.
- **P33 and P34** were consistently identified as the most important predictors across multiple methods, both positively associated with Yield.
- The bootstrap analysis demonstrated that the robust MAD estimator had substantially lower variance than the standard deviation estimator in the presence of outliers, confirming its robustness.
- Key insight: different selection methods may yield different "best" models, and domain expertise should guide final model choice beyond pure prediction metrics.

[Download Full Report (PDF)](/files/SL_HW3_Resampling_Regularization.pdf)
