---
title: "Statistical Computing: Simulation, Monte Carlo, MCMC, Hypothesis Testing, Optimization, EM Algorithm, and Gaussian Processes"
excerpt: "Random variate generation, Monte Carlo integration, MCMC sampling, bootstrap and permutation tests, power analysis, Newton-Raphson optimization, EM algorithm for mixtures, Gaussian process regression, and Bayesian optimization.<br/>"
collection: portfolio
---

## Data Source & Cleaning

A range of simulated and real datasets were used:

- **Simulated Distributions**: Weibull, Beta, Gamma, and custom distributions generated via inverse CDF, acceptance-rejection, and MCMC methods.
- **Monte Carlo Data**: Simulated samples for estimating kurtosis, skewness, and complex integrals with importance sampling and control variates.
- **Normality Testing Data**: Simulated samples from normal and alternative distributions (t, chi-squared, exponential) for Jarque-Bera test power analysis.
- **Gaussian Mixture Data**: Simulated 2D data from two-component Gaussian mixture for EM algorithm development.
- **Heteroscedastic Regression Data**: Data with non-constant variance modeled as exponential function of covariates.
- **Spatial Data**: Georeferenced observations for Gaussian process regression with Matern covariance estimation.

## Exploratory Data Analysis (EDA)

- Empirical vs. theoretical density comparisons validated random variate generation methods.
- Trace plots and autocorrelation diagnostics assessed MCMC chain mixing and convergence.
- Residual plots from ordinary regression revealed heteroscedasticity patterns justifying variance modeling.
- Scatter plots of 2D mixture data visualized overlapping clusters motivating mixture model approach.

## Methods

### Simulation and Monte Carlo (Reports 1-2)
- **Random Variate Generation**: Inverse CDF method for Weibull; acceptance-rejection sampling for complex densities.
- **Monte Carlo Integration**: Crude, antithetic variates, importance sampling, and control variate methods with variance reduction comparisons.
- **MCMC**: Metropolis-Hastings and Gibbs sampling with convergence diagnostics (trace plots, effective sample size).

### Hypothesis Testing and Bootstrap (Report 3)
- **Jarque-Bera Normality Test**: Implemented and evaluated power via Monte Carlo simulation under multiple alternative distributions.
- **Bootstrap and Permutation Tests**: Nonparametric inference for comparing group means and testing hypotheses.

### Optimization and EM Algorithm (Reports 4-5)
- **Newton-Raphson**: Analytical gradient and Hessian for heteroscedastic MLE; line search for step-size control.
- **EM Algorithm**: E-step posterior class probabilities; M-step closed-form updates for mixture weights, means, and covariances; convergence via log-likelihood monitoring.

### Gaussian Process and Bayesian Optimization (Reports 6 & Midterm)
- **Gaussian Process Regression**: Matern covariance with MLE for spatial data; kriging predictions with uncertainty.
- **Bayesian Optimization**: Expected Improvement acquisition function with GP surrogates for black-box optimization.
- **Numerical Integration**: Adaptive quadrature for multivariate integrals; hemisphere density verification.

## Results & Interpretation

- Inverse CDF and acceptance-rejection methods accurately reproduced target distributions.
- Importance sampling with well-chosen proposal distributions achieved significant variance reduction over crude Monte Carlo.
- Jarque-Bera test showed high power against heavy-tailed alternatives but low power against symmetric non-normal distributions.
- EM algorithm recovered true mixture parameters with monotone log-likelihood convergence.
- Newton-Raphson achieved quadratic convergence to MLE, matching R's `optim` output.
- GP regression with Matern covariance provided accurate spatial predictions with calibrated uncertainty bands.

[Download Report 1 (PDF)](/files/SC_HW1_Computing.pdf) | [Download Report 2 (PDF)](/files/SC_HW2_Computing.pdf) | [Download Report 3 (PDF)](/files/SC_HW3_Computing.pdf) | [Download Report 4 (PDF)](/files/SC_HW4_Optimization.pdf) | [Download Report 5 (PDF)](/files/SC_HW5_EM_Algorithm.pdf) | [Download Report 6 (PDF)](/files/SC_HW6_Computing.pdf) | [Download Midterm (PDF)](/files/SC_Midterm_Computing.pdf)
