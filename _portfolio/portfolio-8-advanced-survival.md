---
title: "Advanced Survival Analysis: Interval Censoring and Self-Consistency"
excerpt: "Nonparametric MLE for interval-censored data using self-consistency equations, Turnbull estimator, and EM-type algorithms.<br/>"
collection: portfolio
---

## Data Source & Cleaning

- **Interval-Censored Data**: Observations subject to left-censoring, right-censoring, and interval-censoring simultaneously. Each observation provides a censoring indicator (left/exact/right) alongside the observed time, requiring specialized nonparametric methods.
- Data preprocessing involved sorting observations and identifying distinct failure times to construct the self-consistency equations.

## Exploratory Data Analysis (EDA)

- Censoring patterns analyzed to determine the proportion of left-censored, right-censored, and exactly observed failure times.
- Distinct failure times identified as the support points for the nonparametric MLE.

## Methods

- **Self-Consistency Equations**: Derived from first principles by conditioning on the censoring type. The survival probabilities at distinct failure times satisfy a system of fixed-point equations.
- **Iterative Algorithm**: Custom EM-type algorithm implemented to solve the self-consistency equations via fixed-point iteration until convergence (tolerance = 10^-6).
- **Conditional Probability Derivations**: Rigorous derivation of P(T > t | X, delta) for left-censored, right-censored, and exactly observed cases.
- **Turnbull Estimator**: Connection to the generalized Kaplan-Meier approach for mixed censoring types.

## Results & Interpretation

- The iterative algorithm converged to the NPMLE of the survival function, properly accounting for all censoring types.
- Results demonstrated that ignoring interval censoring (e.g., treating left-censored observations as exact) leads to biased survival estimates.
- The self-consistency approach provided a principled framework for handling complex censoring structures commonly encountered in clinical trials and epidemiological studies.

[Download Full Report (PDF)](/files/ASA_HW2_Advanced_Survival.pdf)
