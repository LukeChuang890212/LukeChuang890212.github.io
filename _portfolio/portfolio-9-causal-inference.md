---
title: "Causal Inference and Biological Data Analysis: DAGs, GLMs, Mixed-Effects Models, and Treatment Effect Estimation"
excerpt: "DAG-based causal reasoning, Poisson GLM with offset, logistic regression with ROC/calibration, linear mixed-effects models, GEE, meta-analysis, IPTW, standardization, and doubly robust estimation.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Multiple biostatistical datasets were analyzed:

- **Pregnancy Rate Data**: 1154 observations with count outcome (number of pregnancies), years of sexual activity as offset, and demographic predictors including age, race, marital status, and contraceptive behavior.
- **Cardiac Catheterization Data** (`acath`): Case-control study with significant coronary disease as binary outcome, predictors including sex, age, and serum cholesterol. Split into training (acath_A) and validation (acath_B) sets.
- **DAG Causal Data**: Directed acyclic graphs with unmeasured confounders for reasoning about causal effects, collider bias, and instrumental variables.
- **Orthodontic Growth Data**: Longitudinal measurements of dental distance trajectories for children aged 8–14, with gender and income covariates, requiring mixed-effects modeling.
- **BCG Vaccine Meta-Analysis Data**: 7 clinical studies comparing BCG vaccine vs. placebo for tuberculosis prevention, requiring meta-analytic methods.
- **Salary and Job Training Data**: Observational data on program participation and salary outcomes for causal effect estimation using propensity score methods.

## Exploratory Data Analysis (EDA)

- Pearson residual analysis revealed overdispersion in the Poisson pregnancy model (dispersion ratio ≈ 2.93).
- Nonlinear cholesterol-disease relationships explored via polynomial and restricted cubic spline fits, with likelihood ratio tests confirming significance.
- DAG analysis identified confounders, colliders, and instrumental variables for causal reasoning.
- Spaghetti plots of longitudinal distance trajectories revealed gender-specific growth patterns and subject-level variability.
- Propensity score distributions examined via boxplots; positivity violations addressed by truncation.

## Methods

- **Poisson GLM with Offset**: Rate modeling for pregnancy counts with log(years) offset; overdispersion correction via quasi-Poisson.
- **Logistic Regression with Diagnostics**: Polynomial and RCS nonlinearity modeling; ROC curves (AUC = 0.809), calibration plots, and Hosmer-Lemeshow tests on validation data.
- **DAG-Based Causal Reasoning**: Identifying valid adjustment sets, instrumental variables, and collider bias in complex causal structures.
- **Linear Mixed-Effects Models** (`lme4`): Random intercept and slope models for longitudinal orthodontic data; age centering for convergence; Kenward-Roger tests for fixed effects; parametric bootstrap for RLRT.
- **GEE**: Marginal models with exchangeable and AR(1) working correlation; QIC/CIC for model selection.
- **Meta-Analysis**: Common-effect and random-effects models for BCG vaccine efficacy; GLMM via `glmer`.
- **IPTW and Standardization**: Propensity score logistic regression with RCS; Horvitz-Thompson estimator; covariate balance verification via SMD.
- **Doubly Robust Estimation**: Combined IPTW and outcome regression with bootstrap inference (B = 500).

## Results & Interpretation

- Age was the strongest predictor of pregnancy rate; overdispersion required variance inflation adjustment.
- Old and young participants showed significantly different nonlinear cholesterol-disease relationships (interaction p < 0.05).
- Boys and girls had significantly different dental growth slopes (p < 0.05 by Kenward-Roger test).
- BCG vaccine significantly lowered tuberculosis risk (OR ≈ 0.62, p < 0.001) in both fixed and random effects meta-analysis.
- IPTW estimated a significant positive causal effect of job training on salary, confirmed by standardization and doubly robust estimators.

[Download GLM Analysis (PDF)](/files/BDA_HW1_GLM.pdf) | [Download Causal DAGs (PDF)](/files/BDA_HW2_Causal.pdf) | [Download Mixed-Effects & GEE (PDF)](/files/BDA_Midterm_Mixed_Effects.pdf) | [Download Causal Inference (PDF)](/files/BDA_Term_Causal_Inference.pdf)
