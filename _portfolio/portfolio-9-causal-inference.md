---
title: "Causal Inference: Average Treatment Effect Estimation via IPTW and Standardization"
excerpt: "Propensity score modeling, inverse probability weighting, outcome regression, and doubly robust estimation for evaluating a job training program's causal effect on salary.<br/>"
collection: portfolio
---

## Data Source & Cleaning

**Salary and Job Training Data**: Observational data on citizens' participation in a government job training program. Variables include demographic information (age, education, gender, race), baseline salary (sal05), program participation indicator (prog), and follow-up salary (sal07). The goal was to estimate the average causal effect of program participation on subsequent salary.

## Exploratory Data Analysis (EDA)

- DAG (directed acyclic graph) analysis to identify confounders between treatment and outcome.
- Propensity score distribution examined via boxplots, revealing near-zero propensities for some individuals, violating the positivity assumption.
- Calibration plots with Hosmer-Lemeshow tests assessed propensity model adequacy.
- Standardized mean differences (SMD) and empirical CDF comparisons used to verify covariate balance after reweighting.

## Methods

- **Propensity Score Modeling**: Logistic regression with restricted cubic splines (RCS) for nonlinear covariate effects, iteratively refined using Hosmer-Lemeshow calibration tests.
- **Identifying Assumptions**: Systematic verification of consistency, conditional exchangeability, and positivity. Positivity violation addressed by truncating the sample to individuals with propensity >= 3%.
- **IPTW (Inverse Probability of Treatment Weighting)**: Horvitz-Thompson estimator with propensity-based weights; covariate balance verified via SMD < 0.1 and eCDF alignment.
- **Standardization (Outcome Regression)**: Separate outcome models fitted for treated and untreated groups using RCS-based linear regression.
- **Doubly Robust Estimation**: Combined IPTW and outcome regression for robustness against model misspecification.
- **Bootstrap Inference**: Nonparametric bootstrap (B = 500) for confidence intervals and hypothesis testing of the causal effect.

## Results & Interpretation

- The positivity assumption was violated for the full population, leading to a refined causal query targeting individuals with >= 3% enrollment probability.
- IPTW estimated a statistically significant positive causal effect of the program on salary, confirmed by the bootstrap 95% CI excluding zero.
- Standardization and doubly robust estimators yielded consistent results, strengthening the causal conclusion.
- The analysis provided actionable evidence that the city administrator could use to justify program expansion, while carefully delineating the population to which the causal conclusion applies.

[Download Full Report (PDF)](/files/BDA_Term_Causal_Inference.pdf)
