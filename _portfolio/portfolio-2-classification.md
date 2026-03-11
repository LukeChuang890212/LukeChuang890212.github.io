---
title: "Classification Methods: Breast Cancer Diagnosis"
excerpt: "Comprehensive comparison of classification methods including logistic regression, discriminant analysis, and KNN for tumor diagnosis.<br/>"
collection: portfolio
---

## Data Source & Cleaning

**Wisconsin Breast Cancer Data** from the UCI Machine Learning Repository (via R `mlbench` package): 699 observations with 9 ordinal predictors describing cell characteristics (clump thickness, uniformity of cell size/shape, marginal adhesion, epithelial cell size, bare nuclei, bland chromatin, normal nucleoli, mitoses) and 1 binary target (benign vs. malignant). 16 observations with missing values in the Bare.nuclei variable were removed, resulting in 683 complete cases. A 90/10 train-test split was applied with density-based verification to ensure the split preserved the data structure.

## Exploratory Data Analysis (EDA)

- Frequency tables revealed strongly right-skewed distributions across all predictors, with most observations concentrated at lower levels.
- Pairwise scatter plots colored by class showed distinct distributions for benign and malignant cases across all variables, suggesting all predictors carry discriminative power.
- Correlation analysis revealed high correlations among predictors, warranting careful consideration during modeling.
- Bimodal distributions in most predictors reflected the underlying two-class structure.

## Methods

- **Logistic Regression**: Main-effects model with stepwise variable selection; interaction effects explored based on EDA findings.
- **Linear Discriminant Analysis (LDA)**: Applied despite potential violation of multivariate normality.
- **Quadratic Discriminant Analysis (QDA)**: To account for unequal covariance matrices between classes.
- **Naive Bayes Classifier**: Both Gaussian and nonparametric kernel-based versions to handle the non-normal marginal distributions.
- **K-Nearest Neighbors (KNN)**: Optimal k selected via cross-validation.
- All classifiers evaluated using accuracy, false positive rate, false negative rate, and ROC/AUC analysis.

## Results & Interpretation

- All classifiers achieved high accuracy (>95%) on the test set, reflecting the strong discriminative signal in the cell characteristics.
- Logistic regression and LDA provided highly interpretable results, identifying Cell.size, Bare.nuclei, and Bl.cromatin as the most influential predictors.
- QDA and nonparametric Naive Bayes showed slight improvements by relaxing normality and equal-covariance assumptions.
- KNN performed competitively with an optimally tuned k, though with reduced interpretability.
- ROC curve comparison demonstrated that all methods achieved AUC values above 0.98, confirming the data's strong separability.

[Download Full Report (PDF)](/files/SL_HW2_Classification.pdf)
