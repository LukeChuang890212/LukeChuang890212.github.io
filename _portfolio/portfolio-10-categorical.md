---
title: "Categorical Data Analysis: Log-Linear Models, Correspondence Analysis, and Social Mobility"
excerpt: "Chi-square tests, logistic regression for cancer risk factors, correspondence analysis for community-education patterns, and symmetry models for social mobility tables.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Multiple categorical datasets were analyzed:

- **Esophageal Cancer Data** (R `esoph` dataset): Case-control study with age group, alcohol consumption, and tobacco use as risk factors. Response: number of cancer cases vs. controls.
- **Swiss Community-Education Data**: Contingency table of 8 schooling levels x 12 communities, examining the association between education and residential location.
- **British Social Mobility Data**: 6x6 mobility table comparing father's social class (1971) with son's social class (1981), testing for symmetry and quasi-symmetry in intergenerational mobility.

## Exploratory Data Analysis (EDA)

- Contingency tables and mosaic plots used to visualize categorical associations.
- Chi-square tests for independence with large test statistics (X² = 5260 for community-education) confirmed strong associations.
- Marginal distributions examined for potential sparsity issues.

## Methods

- **Logistic Regression**: Saturated model with all interactions, simplified via backward elimination (AIC-based). Factors converted between categorical and numerical representations to find the most parsimonious model.
- **Correspondence Analysis**: SVD of Pearson residuals from the independence model, producing 2D biplots for simultaneous visualization of row and column categories.
- **Log-Linear Models**: Poisson regression framework for modeling contingency table frequencies.
- **Symmetry and Quasi-Symmetry Models**: Testing whether social mobility patterns are symmetric (equal upward and downward mobility) using specialized log-linear models with symmetric pair factors.
- **Goodness-of-Fit**: Deviance and Pearson residual analysis for model adequacy.

## Results & Interpretation

- **Cancer Study**: Age and alcohol consumption were the strongest risk factors; tobacco showed a weaker but significant main effect. No significant interactions were retained after model selection.
- **Correspondence Analysis**: Identified distinct education-community profiles. University-level education was strongly associated with specific communities (e.g., Pully, Lausanne) while vocational training showed opposite patterns.
- **Social Mobility**: The symmetry hypothesis was rejected, indicating that upward and downward social mobility are not equally likely in Britain, with specific class transitions showing significant asymmetry.

[Download Report 1 (PDF)](/files/CDA_HW3_Categorical.pdf) | [Download Report 2 (PDF)](/files/CDA_HW5_Categorical.pdf)
