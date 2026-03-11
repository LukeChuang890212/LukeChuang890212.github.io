---
title: "Advanced Survival Analysis: Parametric MLE, Interval Censoring, and Self-Consistency"
excerpt: "Exponential and Weibull MLE with Fisher information, nonparametric MLE for interval-censored data using self-consistency equations and Turnbull estimator.<br/>"
collection: portfolio
---

## Data Source & Cleaning

- **Exponential and Weibull Lifetime Data**: Simulated and theoretical lifetime data used to derive MLE properties, Fisher information, and variance expressions for parametric survival models.
- **Interval-Censored Data**: Observations subject to left-censoring, right-censoring, and interval-censoring simultaneously. Each observation provides a censoring indicator alongside the observed time, requiring specialized nonparametric methods.
- Data preprocessing involved sorting observations and identifying distinct failure times to construct the self-consistency equations.

## Exploratory Data Analysis (EDA)

- Censoring patterns analyzed to determine the proportion of left-censored, right-censored, and exactly observed failure times.
- Distinct failure times identified as the support points for the nonparametric MLE.

## Methods

### Parametric MLE (Report 1)
- **Exponential Model**: Derived MLE of the rate parameter with closed-form variance via inverse Gamma distribution and Fisher information. Showed variance scaling as O(1/n).
- **Weibull Model**: MLE for shape and scale parameters with flexible hazard modeling.

### Interval Censoring and Self-Consistency (Report 2)
- **Self-Consistency Equations**: Derived from first principles by conditioning on the censoring type. The survival probabilities at distinct failure times satisfy a system of fixed-point equations.
- **Iterative Algorithm**: Custom EM-type algorithm implemented to solve the self-consistency equations via fixed-point iteration until convergence.
- **Turnbull Estimator**: Connection to the generalized Kaplan-Meier approach for mixed censoring types.

## Results & Interpretation

- Parametric analysis showed explicit closed-form expressions for the exponential model's MLE variance.
- The iterative algorithm converged to the NPMLE of the survival function, properly accounting for all censoring types.
- Results demonstrated that ignoring interval censoring leads to biased survival estimates.

[Download Report 1 (PDF)](/files/ASA_HW1_Advanced_Survival.pdf) | [Download Report 2 (PDF)](/files/ASA_HW2_Advanced_Survival.pdf)
