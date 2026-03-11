---
title: "Regression Modeling: Ozone Prediction & Prostate Cancer Analysis"
excerpt: "Multiple regression analysis with model diagnostics, variable selection, and scientific interpretation on environmental and biomedical data.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Two datasets were analyzed in this project:

- **Ozone Data**: 111 daily measurements of 4 variables — ozone (response), radiation, temperature, and wind speed. No missing values were present.
- **Prostate Data**: 97 observations with 8 clinical predictors (lcavol, lweight, age, lbph, svi, lcp, gleason, pgg45) and 1 response variable (lpsa). A 70/27 train-validation split was used. Gleason scores 7–9 were combined into a single "high" level based on Dunn's multiple comparison test.

## Exploratory Data Analysis (EDA)

- **Ozone Data**: Correlation analysis revealed strong positive associations between ozone and both radiation and temperature, and a negative association with wind speed. Box-Cox transformation (fifth-root) was applied to ozone to satisfy normality assumptions. Conditional scatter plots revealed potential nonlinear effects and interaction patterns, particularly a wind speed threshold effect.
- **Prostate Data**: Kendall's tau correlation analysis identified lcavol, lweight, lcp, and pgg45 as significantly associated with lpsa. Kruskal-Wallis and Wilcoxon tests confirmed significant effects of discrete variables (svi, gleason) on the response.

## Methods

- **Linear Regression** with polynomial terms and interaction effects
- **Model Selection** via AIC/BIC-based stepwise procedures
- **Model Diagnostics**: residual analysis, VIF for multicollinearity, leverage and influence assessment
- **Box-Cox Transformation** for response normality
- **Nonparametric Tests** (Kruskal-Wallis, Dunn's test) for discrete predictor assessment
- **Prediction Intervals** for validation set evaluation

## Results & Interpretation

- **Ozone**: After Box-Cox transformation, the best model included radiation, temperature, wind speed, and a wind-threshold indicator variable. Higher radiation and temperature were associated with higher ozone, while higher wind speed reduced ozone. A wind speed threshold effect was discovered — wind had strong negative impact below the threshold but negligible effect above it. RMSE of ~19 was small relative to the ozone range, indicating good prediction performance.
- **Prostate**: lcavol and svi were identified as the most important predictors of log-PSA. The final model achieved good predictive coverage on the validation set with well-calibrated prediction intervals.

[Download Full Report (PDF)](/files/SL_HW1_Regression.pdf)
