---
title: "Nonparametric Curve Estimation: Density Estimation, Kernel Regression, Splines, and Local Methods"
excerpt: "Histogram and kernel density estimation, bandwidth selection, multivariate KDE, local polynomial regression, smoothing splines, penalized regression, cross-validation, and generalized additive models.<br/>"
collection: portfolio
---

## Data Source & Cleaning

A variety of simulated and real datasets were used across nine reports:

- **Simulated Univariate Data**: Uniform, Beta, and Gaussian mixture samples for studying density estimation properties.
- **Multivariate Data**: Bivariate and higher-dimensional samples for multivariate kernel density estimation.
- **Regression Data**: Nonlinear functional relationships with noise for evaluating local polynomial and spline smoothers.
- **Real-World Data**: Applied datasets requiring flexible nonparametric modeling approaches.

## Exploratory Data Analysis (EDA)

- Histograms with varying bin origins and bandwidths demonstrated sensitivity to arbitrary choices.
- Rug plots and empirical CDFs visualized raw data distributions before smoothing.
- Scatter plots with overlaid fits compared parametric and nonparametric regression approaches.
- Residual analysis after nonparametric fits assessed goodness-of-fit and remaining structure.

## Methods

### Density Estimation (Reports 1, 3–6)
- **Histogram Density Estimation**: Effects of bin origin and bandwidth on estimation quality.
- **Kernel Density Estimation**: Gaussian and Epanechnikov kernels with varying bandwidths; bias-variance tradeoff demonstration.
- **Parametric MLE Comparison**: Beta distribution MLE via L-BFGS-B optimization as benchmark.
- **Bandwidth Selection**: Rule-of-thumb, least-squares cross-validation (LSCV), and plug-in methods.
- **Multivariate KDE**: Extension to bivariate settings with product kernels and bandwidth matrices.
- **Boundary Correction**: Reflection and other methods for density estimation near boundaries.

### Nonparametric Regression (Reports 7–10)
- **Local Polynomial Regression**: Local linear and local quadratic fits with smoother matrix derivation; bandwidth selection via cross-validation.
- **Kernel Regression**: Nadaraya-Watson estimator and its properties.
- **Smoothing Splines**: Cubic smoothing splines with smoothing parameter selection; connection to penalized regression.
- **Penalized Regression Splines**: B-spline basis with roughness penalty; GCV and REML for smoothing parameter estimation.
- **Generalized Additive Models (GAMs)**: Additive models with multiple smooth terms fitted via `mgcv`.
- **Mixed Model Representation**: Connection between penalized splines and random effects models via `lme4`.

## Results & Interpretation

- Kernel density estimation with data-driven bandwidth selection consistently outperformed fixed-bandwidth approaches and histograms.
- Epanechnikov and Gaussian kernels produced similar estimates when bandwidths were properly calibrated; kernel choice was less important than bandwidth choice.
- Local linear regression avoided boundary bias that affected Nadaraya-Watson estimates.
- Smoothing splines with GCV-selected parameters provided excellent fits while avoiding overfitting.
- GAMs successfully captured nonlinear relationships in multiple predictors simultaneously.
- The fundamental bias-variance tradeoff was systematically demonstrated across all estimation methods.

[Download Report 1 (PDF)](/files/NCE_HW1_Density_Estimation.pdf) | [Download Report 3 (PDF)](/files/NCE_HW3_Nonparametric.pdf) | [Download Report 4 (PDF)](/files/NCE_HW4_Nonparametric.pdf) | [Download Report 5 (PDF)](/files/NCE_HW5_Nonparametric.pdf) | [Download Report 6 (PDF)](/files/NCE_HW6_Nonparametric.pdf) | [Download Report 7 (PDF)](/files/NCE_HW7_Nonparametric.pdf) | [Download Report 8 (PDF)](/files/NCE_HW8_Nonparametric.pdf) | [Download Report 9 (PDF)](/files/NCE_HW9_Nonparametric.pdf) | [Download Report 10 (PDF)](/files/NCE_HW10_Nonparametric.pdf)
