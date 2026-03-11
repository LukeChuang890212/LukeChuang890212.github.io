---
title: "Model Selection & Regularization: Chemical Manufacturing Yield Prediction"
excerpt: "Systematic comparison of variable selection methods including subset selection, PCR, Lasso, and Ridge regression on high-dimensional manufacturing data.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #0a2463 0%, #1e3a8a 50%, #3b82f6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #93c5fd; margin-top: 0; font-size: 1.6em;">6 Methods. 57 Predictors. Which Ones Actually Matter?</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    A systematic head-to-head comparison of <strong>6 variable selection and regularization methods</strong> on a high-dimensional chemical manufacturing dataset — from forward/backward selection to Lasso and Ridge — revealing the predictors that consistently drive product yield.
  </p>
</div>

## Data Source & Cleaning

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #3b82f6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #1e3a8a; margin-top: 0;">Chemical Manufacturing Data</h3>
    <p><strong>177 samples</strong> with 57 predictors (12 biological + 45 process measurements) and product yield as the response. Missing values removed, predictors standardized. 90/10 train-test split.</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #15803d; margin-top: 0;">Bootstrap Robustness Study</h3>
    <p>Contaminated dataset comparing standard vs. <strong>MAD-based robust estimators</strong> of population standard deviation via nonparametric bootstrap (B = 10,000).</p>
  </div>
</div>

## Exploratory Data Analysis (EDA)

- Large scale differences among predictors necessitated standardization for fair comparison.
- High correlations among many predictors supported dimensionality reduction approaches.
- Few predictors showed strong marginal association with Yield — consistent with the **sparsity principle**.
- Skewed distributions in P12, P28, P40–P43; outliers detected in P25–P31.

## Methods — 6 Selection Procedures Compared

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">1</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Forward Selection</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5 predictors selected</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">2</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Backward Selection</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 predictors selected</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">3</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Best Subset</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5 predictors selected</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">4</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">PCR</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">6 PCs retained</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">5</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Lasso</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">7 predictors (refined)</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">6</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Ridge</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 predictors (top coefs)</p>
  </div>
</div>

All methods evaluated via **5-fold cross-validation** for fair comparison.

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #93c5fd; margin: 0;">Lasso Wins on CV Stability</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">Revised Lasso (Model 5) achieved the smallest and most stable test MSE</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">P33 & P34</span><br><span style="color: #aaa;">Consistent top predictors</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">57 → 3–7</span><br><span style="color: #aaa;">Dimension reduction</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">B=10,000</span><br><span style="color: #aaa;">Bootstrap replicates</span></div>
  </div>
</div>

- **P33** and **P34** were consistently identified as the most important predictors across multiple methods, both positively associated with Yield.
- PCR achieved the lowest test-set RMSE, while Lasso provided the best CV stability.
- The robust MAD estimator had substantially lower variance than the standard estimator in the presence of outliers.

<div style="margin-top: 25px;">
  <a href="/files/SL_HW3_Resampling_Regularization.pdf" style="display: inline-block; background: #1e3a8a; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Full Report (PDF)</a>
</div>
