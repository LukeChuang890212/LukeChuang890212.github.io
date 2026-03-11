---
title: "Statistical Computing: EM Algorithm, Newton-Raphson, and Numerical Optimization"
excerpt: "Implementation of EM algorithm for Gaussian mixtures, Newton-Raphson for heteroscedastic regression MLE, and Bayesian optimization from scratch.<br/>"
collection: portfolio
---

## Data Source & Cleaning

- **Gaussian Mixture Data**: Simulated 2D data from a two-component Gaussian mixture model, used to develop and validate the EM algorithm implementation.
- **Heteroscedastic Regression Data**: Data with non-constant variance modeled as an exponential function of covariates, requiring joint MLE of mean and variance parameters.

## Exploratory Data Analysis (EDA)

- Scatter plots of the 2D mixture data revealed two overlapping clusters, motivating the mixture model approach.
- Residual plots from ordinary regression showed clear heteroscedasticity patterns, justifying the variance modeling approach.

## Methods

### EM Algorithm for Gaussian Mixtures
- **Data Augmentation**: Introduced latent class indicators as missing data, enabling the complete-data likelihood decomposition.
- **E-step**: Computed posterior class membership probabilities using Bayes' theorem with current parameter estimates.
- **M-step**: Derived closed-form updates for mixture weight, component means, and covariance matrices.
- Full derivation of both steps from the complete log-likelihood, with convergence monitoring via log-likelihood values.

### Newton-Raphson for Heteroscedastic MLE
- **Model**: Mean mu = beta_0 + beta_1*x with variance sigma² = exp(alpha_0 + alpha_1*x).
- **Implementation**: Derived the gradient vector and Hessian matrix of the log-likelihood analytically. Implemented the Newton-Raphson iterative scheme with line search for step-size control.
- **Comparison**: Validated results against R's `optim` function.

### Bayesian Optimization
- Implemented acquisition function (Expected Improvement) for black-box function optimization using Gaussian process surrogates.

## Results & Interpretation

- The EM algorithm successfully recovered the true mixture parameters (means, covariances, mixing proportion) from simulated data, demonstrating monotone convergence of the log-likelihood.
- Newton-Raphson achieved quadratic convergence to the MLE, with results matching numerical optimization output. The heteroscedastic model captured the increasing variance pattern effectively.
- These implementations demonstrate proficiency in translating statistical theory into efficient computational algorithms.

[Download EM Algorithm Report (PDF)](/files/SC_HW5_EM_Algorithm.pdf) | [Download Optimization Report (PDF)](/files/SC_HW4_Optimization.pdf)
