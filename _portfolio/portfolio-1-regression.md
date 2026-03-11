---
title: "Regression Modeling: Ozone Prediction & Prostate Cancer Analysis"
excerpt: "Multiple regression analysis with model diagnostics, variable selection, and scientific interpretation on environmental and biomedical data.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #0d4f4f 0%, #1a7a5a 50%, #2d8f4e 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #7fecb3; margin-top: 0; font-size: 1.6em;">From Raw Measurements to Predictive Models</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Two distinct domains — <strong>environmental science</strong> and <strong>cancer biology</strong> — analyzed through the lens of regression theory. From discovering a wind speed threshold effect on ozone levels to identifying the most critical predictors of prostate cancer progression.
  </p>
</div>

## Data Source & Cleaning

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f0faf5; border-left: 5px solid #2d8f4e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2d8f4e; margin-top: 0;">Ozone Data</h3>
    <p><strong>111 daily measurements</strong> of ozone, radiation, temperature, and wind speed. No missing values. Box-Cox transformation (fifth-root) applied to satisfy normality assumptions.</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0f5fa; border-left: 5px solid #3a7bd5; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3a7bd5; margin-top: 0;">Prostate Data</h3>
    <p><strong>97 observations</strong> with 8 clinical predictors and log-PSA response. 70/27 train-validation split. Gleason scores 7–9 combined into "high" level based on Dunn's multiple comparison test.</p>
  </div>
</div>

## Exploratory Data Analysis (EDA)

- **Ozone**: Strong positive associations between ozone and both radiation and temperature; negative association with wind speed. Conditional scatter plots revealed a **wind speed threshold effect**.
- **Prostate**: Kendall's tau identified lcavol, lweight, lcp, and pgg45 as significantly associated with lpsa. Kruskal-Wallis and Wilcoxon tests confirmed significant effects of discrete variables.

## Methods

| Method | Purpose |
|--------|---------|
| Linear Regression | Polynomial terms and interaction effects |
| AIC/BIC Stepwise Selection | Parsimonious model identification |
| Model Diagnostics | Residuals, VIF, leverage, influence |
| Box-Cox Transformation | Response normality |
| Nonparametric Tests | Discrete predictor assessment |
| Prediction Intervals | Validation set evaluation |

## Key Results

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #2d8f4e; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #2d8f4e; margin: 5px 0;">RMSE ≈ 19</p>
    <p style="color: #666;">Ozone prediction — small relative to the ozone range, indicating strong performance</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #3a7bd5; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #3a7bd5; margin: 5px 0;">lcavol + svi</p>
    <p style="color: #666;">Most important predictors of prostate cancer progression (log-PSA)</p>
  </div>
</div>

- A **wind speed threshold effect** was discovered — wind had strong negative impact below the threshold but negligible effect above it.
- The final prostate model achieved well-calibrated prediction intervals on the validation set.

<div style="margin-top: 25px;">
  <a href="/files/SL_HW1_Regression.pdf" style="display: inline-block; background: #2d8f4e; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Full Report (PDF)</a>
</div>
