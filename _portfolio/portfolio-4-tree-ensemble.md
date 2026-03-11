---
title: "Tree-Based & Ensemble Methods: Bike Sharing and Airline Satisfaction"
excerpt: "Decision trees, random forests, gradient boosting, and nonlinear regression for demand prediction and customer satisfaction classification.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #1a4731 0%, #065f46 50%, #059669 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #6ee7b7; margin-top: 0; font-size: 1.6em;">When One Tree Isn't Enough — Ensembles Take Over</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    From a single decision tree to <strong>random forests</strong> and <strong>gradient boosting</strong> — pushing tree-based methods to their limits on <strong>731 bike-sharing</strong> records and <strong>103K airline satisfaction</strong> surveys.
  </p>
</div>

## Data Source & Cleaning

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #065f46; margin-top: 0;">Bike Sharing Data</h3>
    <p><strong>731 daily observations</strong> (2011–2012) with 11 predictors: season, weather, temperature, humidity, wind speed, and more. Response: daily bike count. 80/20 train-test split.</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fef3c7; border-left: 5px solid #d97706; padding: 20px; border-radius: 8px;">
    <h3 style="color: #92400e; margin-top: 0;">Airline Satisfaction Survey</h3>
    <p><strong>103,594 observations</strong> with 23 predictors: demographics, travel info, 14 service ratings, delay metrics. Binary outcome: satisfied vs. dissatisfied. 80/20 split.</p>
  </div>
</div>

## Exploratory Data Analysis (EDA)

- **Bike Sharing**: Temperature showed strongest positive correlation (r = 0.627). Quadratic temperature effect detected — usage peaks at ~20°C then declines.
- **Airline**: Service ratings had strong discriminative power. Most customers were loyal business travelers. Delays were severely right-skewed.

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Decision Tree</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Pruned via cost-complexity CV</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV-tuned m parameter</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Gradient Boosting</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Grid search: depth, shrinkage, trees</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Linear Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Best subset benchmark</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Nonlinear Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Polynomials + B-splines</p>
  </div>
  <div style="background: #fef3c7; border: 2px solid #d97706; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Noise Injection Test</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Validating importance rankings</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #6ee7b7; margin: 5px 0;">Ensembles Win</p>
      <p style="color: #aaa;">RF & GBM outperform single trees and linear models on bike data</p>
    </div>
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #fbbf24; margin: 5px 0;">103K Surveys</p>
      <p style="color: #aaa;">Airline classification with noise-validated importance</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">Year + Temp</span><br><span style="color: #aaa;">Top bike predictors</span></div>
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">Online Boarding</span><br><span style="color: #aaa;">Top airline predictor</span></div>
  </div>
</div>

- **Year** and **temperature** consistently ranked as top bike-sharing predictors across all methods.
- B-spline regression captured the temperature threshold effect better than polynomial models.
- Online boarding, inflight Wi-Fi, and travel type were the top satisfaction drivers — confirmed by noise variable injection.

<div style="margin-top: 25px;">
  <a href="/files/SL_HW4_Tree_Methods.pdf" style="display: inline-block; background: #065f46; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Full Report (PDF)</a>
</div>
