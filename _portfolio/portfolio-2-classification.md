---
title: "Classification Methods: Breast Cancer Diagnosis"
excerpt: "Comprehensive comparison of classification methods including logistic regression, discriminant analysis, and KNN for tumor diagnosis.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #4a1942 0%, #893168 50%, #c94b8c 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ffb6d9; margin-top: 0; font-size: 1.6em;">Can an Algorithm Distinguish Benign from Malignant?</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    A head-to-head comparison of <strong>6 classification methods</strong> on the Wisconsin Breast Cancer dataset. From logistic regression to KNN — every classifier was pushed to its limits on 683 tumor samples with 9 cell characteristics.
  </p>
</div>

## Data Source & Cleaning

**Wisconsin Breast Cancer Data** (UCI / R `mlbench`): 699 observations with 9 ordinal predictors describing cell characteristics and 1 binary target (benign vs. malignant). 16 observations with missing values removed. A 90/10 train-test split was applied with density-based verification.

## Exploratory Data Analysis (EDA)

- Strongly right-skewed distributions across all predictors, with bimodal patterns reflecting the two-class structure.
- Pairwise scatter plots showed distinct distributions for benign and malignant cases — all predictors carry discriminative power.
- High correlations among predictors warranted careful modeling consideration.

## Methods — 6-Way Classifier Showdown

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">Logistic Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Stepwise selection + interactions</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">LDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Linear discriminant analysis</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">QDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Unequal covariance matrices</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">Naive Bayes</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Gaussian + nonparametric kernel</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">KNN</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV-optimized k</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">ROC/AUC</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Full comparison framework</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2.5em; font-weight: bold; color: #ffb6d9; margin: 0;">AUC > 0.98</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">All classifiers — confirming the data's strong separability</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">95%+</span><br><span style="color: #aaa;">Test accuracy</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3</span><br><span style="color: #aaa;">Top predictors identified</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">683</span><br><span style="color: #aaa;">Tumor samples</span></div>
  </div>
</div>

- **Cell.size**, **Bare.nuclei**, and **Bl.cromatin** identified as the most influential predictors across methods.
- QDA and nonparametric Naive Bayes showed slight improvements by relaxing distributional assumptions.
- KNN performed competitively with an optimally tuned k, though with reduced interpretability.

<div style="margin-top: 25px;">
  <a href="/files/SL_HW2_Classification.pdf" style="display: inline-block; background: #893168; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Full Report (PDF)</a>
</div>
