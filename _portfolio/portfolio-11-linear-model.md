---
title: "Linear Models: Regression Theory, Diagnostics, Weighted Least Squares, and Time Series Modeling"
excerpt: "Comprehensive linear model analysis covering EDA, model fitting and selection, hypothesis testing, diagnostics (leverage, outliers, influence, heteroscedasticity), confidence regions, WLS, GLS with AR(1), polynomial regression, splines, and changepoint models.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Multiple datasets were analyzed across seven reports:

- **Teen Gambling Data** (`teengamb`): 47 observations on gambling expenditure predicted by sex, status, income, and verbal score.
- **Chemical Process Data**: Output predicted by steam input, speed, and inlet temperature with polynomial and interaction terms.
- **US Wage Data** (`uswages`): Wages predicted by education and experience with F-tests for nested model comparison.
- **Waste Data**: 5-predictor linear model with confidence intervals, confidence regions (ellipsoidal), and simultaneous inference.
- **Height Data** (Galton-type): Father-son height regression using weighted least squares (WLS) to account for unequal group sizes.
- **CEO Salary Data**: Percentage salary increase modeled with outlier detection, variance stabilization, and transformation diagnostics.
- **Ann Arbor Temperature Data**: ~150 years of annual mean temperatures with AR(1) autocorrelation, polynomial regression, changepoint models, and cubic B-splines.
- **Indian Infant Mortality Data**: IMR and PQLI with gender and urban/rural dummy variables.

## Exploratory Data Analysis (EDA)

- Pairwise scatter plots, correlation matrices, and conditional distributions to explore variable relationships.
- Residual analysis using raw, studentized, and jackknife residuals for model adequacy assessment.
- Lag-1/2/3 autocorrelation analysis of temperature time series identified AR(1) structure.
- Added-variable plots for detecting nonlinearity in partial relationships.

## Methods

- **Multiple Linear Regression**: OLS estimation with F-tests for overall significance and nested model comparison.
- **Model Diagnostics**: Leverage points (hat matrix), outlier detection (Bonferroni-corrected jackknife residuals), influential observations (Cook's distance, DFBETAS), non-constant variance tests, Q-Q plots.
- **Confidence Regions**: Joint confidence ellipses for pairs of coefficients using the ellipse package.
- **Weighted Least Squares (WLS)**: Regression with weights proportional to group sizes for aggregated data.
- **Generalized Least Squares (GLS)**: AR(1) correlated errors for time series trend estimation.
- **Polynomial and Spline Regression**: Degree-10 polynomial with backward elimination; cubic B-splines with 6 basis functions.
- **Changepoint Model**: Piecewise linear regression with structural break at 1930.
- **Transformations**: Box-Cox power transformation; log-transform for variance stabilization.

## Results & Interpretation

- Backward variable selection identified parsimonious models with significant predictors retained at each stage.
- Diagnostic analyses revealed leverage points, potential outliers, and heteroscedasticity patterns, guiding model refinement.
- WLS properly accounted for unequal precision across grouped observations in height regression.
- Temperature trend analysis confirmed significant post-1930 warming even after AR(1) correction (ρ = 0.23).
- Cubic spline regression achieved the best RMSE, capturing nonlinear temperature fluctuations without polynomial extrapolation instability.

[Download Report 1 (PDF)](/files/LM_HW1_Linear_Model.pdf) | [Download Report 2 (PDF)](/files/LM_HW2_Linear_Model.pdf) | [Download Report 3 (PDF)](/files/LM_HW3_Linear_Model.pdf) | [Download Report 4 (PDF)](/files/LM_HW4_Linear_Model.pdf) | [Download Report 5 (PDF)](/files/LM_HW5_Linear_Model.pdf) | [Download Report 6 (PDF)](/files/LM_HW6_Linear_Model.pdf) | [Download Report 7 (PDF)](/files/LM_HW7_Linear_Model.pdf)
