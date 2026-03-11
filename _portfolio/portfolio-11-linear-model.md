---
title: "Linear Models: Regression Theory, Diagnostics, Weighted Least Squares, and Time Series Modeling"
excerpt: "Comprehensive linear model analysis covering EDA, model fitting and selection, hypothesis testing, diagnostics (leverage, outliers, influence, heteroscedasticity), confidence regions, WLS, GLS with AR(1), polynomial regression, splines, and changepoint models.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #1e3a5f 0%, #2563eb 50%, #60a5fa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #bfdbfe; margin-top: 0; font-size: 1.6em;">The Full Linear Models Toolkit — 7 Reports Deep</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    From OLS fundamentals to <strong>WLS</strong>, <strong>GLS with AR(1)</strong>, <strong>B-splines</strong>, and <strong>changepoint models</strong> — a comprehensive treatment of linear model theory applied to gambling, manufacturing, wages, heights, CEO salaries, and 150 years of temperature data.
  </p>
</div>

## Data Source & Cleaning

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Teen Gambling</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">47 observations, sex/status/income/verbal</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Chemical Process</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Steam, speed, temperature interactions</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">US Wages</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Education + experience, nested F-tests</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Waste Data</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Confidence ellipses, simultaneous inference</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Galton Heights</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">WLS for unequal group sizes</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">CEO Salary</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Outliers, variance stabilization</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Ann Arbor Temperature</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">~150 years, AR(1), splines, changepoint</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Indian Infant Mortality</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Gender + urban/rural dummies</p>
  </div>
</div>

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">OLS + F-Tests</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Nested model comparisons</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Full Diagnostics</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Leverage, Cook's D, DFBETAS</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">WLS</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Weights for grouped data</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GLS + AR(1)</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Correlated errors in time series</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Splines</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Cubic B-splines, 6 basis functions</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Changepoint Model</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Structural break at 1930</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #60a5fa; margin: 0;">150 Years of Warming — Confirmed</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">Post-1930 temperature trend remains significant even after AR(1) correction</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">rho = 0.23</span><br><span style="color: #aaa;">AR(1) autocorrelation</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Spline</span><br><span style="color: #aaa;">Best RMSE model</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">7 Reports</span><br><span style="color: #aaa;">8 datasets analyzed</span></div>
  </div>
</div>

- Diagnostic analyses revealed leverage points, outliers, and heteroscedasticity — guiding model refinement.
- WLS properly accounted for unequal precision in grouped height data.
- **Post-1930 warming** confirmed even after AR(1) correction (rho = 0.23).
- Cubic B-spline regression achieved the best RMSE, capturing nonlinear temperature fluctuations.

<div style="margin-top: 25px;">
  <a href="/files/LM_HW1_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/LM_HW2_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/LM_HW3_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/LM_HW4_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/LM_HW5_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/LM_HW6_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/LM_HW7_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW7</a>
</div>
