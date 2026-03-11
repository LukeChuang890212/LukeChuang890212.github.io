---
title: "Categorical Data Analysis: GLMs, Logistic Regression, Poisson Models, and Correspondence Analysis"
excerpt: "Comprehensive categorical data modeling including linear regression diagnostics, logistic regression for disease risk, Poisson regression for count data with overdispersion, log-linear models, correspondence analysis, and symmetry testing.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Multiple categorical and count datasets were analyzed:

- **Motor Trend Car Data** (`mtcars`): 32 automobiles with fuel consumption (mpg) and 10 design/performance variables. Thorough EDA with Box-Cox transformation exploration.
- **Cardiac Catheterization Data**: Logistic regression for coronary disease with nonlinear cholesterol effects via polynomial and restricted cubic splines.
- **Byssinosis Occupational Data**: Binary outcome (respiratory disease) across 64 covariate classes defined by dust level, employment duration, smoking status, sex, and race.
- **African Military Coups Data** (`faraway::africa`): Count of successful coups per country with political and economic predictors.
- **Salmonella Colony Count Data**: Dose-response relationship with polynomial Poisson regression and overdispersion diagnostics.
- **Danish Marital Status Data**: Age-by-marital-status contingency table modeled with Poisson regression using polynomial contrasts.
- **Esophageal Cancer Data**: Case-control study with age, alcohol, and tobacco risk factors.
- **Swiss Community-Education Data**: Large contingency table (X² = 5260) for correspondence analysis.
- **British Social Mobility Data**: 6×6 intergenerational mobility table for symmetry and quasi-symmetry testing.

## Exploratory Data Analysis (EDA)

- Correlation matrices and pairwise scatter plots revealed multicollinearity (e.g., `cyl` vs. `vs` in mtcars).
- Box-Cox transformation analysis suggested log-transform for mpg (λ ≈ 0).
- Balloon plots and bar charts visualized byssinosis proportions across covariate combinations.
- Half-normal plots of Pearson residuals identified outliers in Salmonella data.
- Mosaic plots and chi-square tests quantified associations in contingency tables.

## Methods

- **Linear Regression with Full Diagnostics**: Leverage points, Cook's distance, jackknife residuals (Bonferroni correction), added-variable plots, non-constant variance tests, Q-Q plots for normality.
- **Logistic Regression**: Polynomial and RCS nonlinearity; AIC-based model comparison; ROC/calibration analysis; interaction effects between age groups and cholesterol.
- **Forward Model Selection via Deviance Tests**: Sequential addition of main effects and interactions using differences-in-deviance chi-square tests with hierarchical principle.
- **Poisson Regression**: Count modeling with polynomial dose-response; AIC-based backward elimination; overdispersion detection and quasi-Poisson adjustment.
- **Correspondence Analysis**: SVD decomposition of Pearson residuals producing 2D biplots for simultaneous row/column visualization.
- **Log-Linear and Symmetry Models**: Poisson framework for contingency tables; symmetry and quasi-symmetry testing for social mobility patterns.

## Results & Interpretation

- Log-transformed mpg model (hp + wt) outperformed the untransformed model, resolving non-constant variance issues.
- Dust exposure and employment duration were the strongest predictors of byssinosis; smoking increased odds by ~40%.
- Political liberalization significantly decreased military coup frequency; oligarchy years and number of parties increased it.
- Cubic polynomial provided best dose-response fit for Salmonella colonies after outlier removal and overdispersion adjustment.
- Correspondence analysis revealed distinct education-community profiles in Swiss data.
- Social mobility symmetry hypothesis was rejected, indicating unequal upward/downward class transitions.

[Download Report 1 (PDF)](/files/CDA_HW1_Categorical.pdf) | [Download Report 2 (PDF)](/files/CDA_HW2_Categorical.pdf) | [Download Report 3 (PDF)](/files/CDA_HW3_Categorical.pdf) | [Download Report 4 (PDF)](/files/CDA_HW4_Categorical.pdf) | [Download Report 5 (PDF)](/files/CDA_HW5_Categorical.pdf)
