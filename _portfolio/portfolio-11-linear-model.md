---
title: "Linear Models: Time Series Trend Analysis, Correlated Errors, and Spline Regression"
excerpt: "GLS with AR(1) errors, polynomial and spline regression, changepoint models, and mixed-effects modeling for temperature trends and infant mortality.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Two datasets were analyzed:

- **Ann Arbor Temperature Data** (US Historical Climatology Network): ~150 years of annual mean temperatures (degrees F). Data was checked for temporal gaps, with a subset of evenly-spaced years used for autocorrelation modeling.
- **Indian Infant Mortality Data**: Infant Mortality Rates (IMR) and Physical Quality of Life Index (PQLI) for selected Indian states, with rural/urban and male/female distinctions requiring dummy variable construction.

## Exploratory Data Analysis (EDA)

- Time series plots revealed an apparent upward trend in temperature over 150 years.
- Residual analysis from simple linear regression showed temporal autocorrelation patterns.
- Lag-1, lag-2, and lag-3 autocorrelation plots (using `pairs.panels`) quantified the correlation structure, identifying AR(1) as the dominant pattern.
- Pairwise scatter plots for the infant mortality data explored gender and urban/rural differences.

## Methods

- **Simple Linear Regression**: Baseline trend model for temperature over time.
- **Generalized Least Squares (GLS)** with AR(1) correlation structure: Accounted for temporal autocorrelation in successive annual observations. Estimated correlation coefficient with confidence interval.
- **Polynomial Regression**: Degree-10 polynomial with backward elimination, reduced to degree 5. Used for prediction (with discussion of extrapolation dangers).
- **Changepoint Model**: Piecewise linear regression with a structural break at 1930, testing the hypothesis that temperature was constant before 1930.
- **Cubic B-Spline Regression**: 6 basis functions with evenly spaced knots, compared against all previous models via RMSE.
- **Dummy Variable Regression**: Male/female and rural/urban indicators for infant mortality modeling.

## Results & Interpretation

- A significant positive temperature trend was confirmed even after accounting for AR(1) autocorrelation (rho = 0.23, 95% CI: [0.029, 0.414]).
- The changepoint model (break at 1930) achieved the lowest RMSE among simple models, supporting the hypothesis of a post-1930 warming trend.
- Cubic spline fit provided the best overall RMSE, capturing nonlinear temperature fluctuations without the extrapolation instability of high-degree polynomials.
- Prediction for 2020 using the degree-5 polynomial produced an unreasonably high value, illustrating the well-known danger of polynomial extrapolation.

[Download Full Report (PDF)](/files/LM_HW7_Linear_Model.pdf)
