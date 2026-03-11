---
title: "Categorical Data Analysis: GLMs, Logistic Regression, Poisson Models, and Correspondence Analysis"
excerpt: "Comprehensive categorical data modeling including linear regression diagnostics, logistic regression for disease risk, Poisson regression for count data with overdispersion, log-linear models, correspondence analysis, and symmetry testing.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #134e4a 0%, #0d9488 50%, #2dd4bf 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #99f6e4; margin-top: 0; font-size: 1.6em;">Counts, Categories, and Contingency Tables</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    A comprehensive tour of <strong>categorical data methods</strong> — from logistic regression for disease risk to Poisson models for count data, correspondence analysis for contingency tables, and symmetry tests for social mobility patterns. <strong>9 real-world datasets</strong> analyzed across 5 reports.
  </p>
</div>

## Data Source & Cleaning

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Motor Trend Cars</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">32 automobiles, mpg + 10 predictors</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Cardiac Catheterization</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Logistic regression with RCS</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Byssinosis Occupational</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">64 covariate classes, binary outcome</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">African Military Coups</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Count data, political predictors</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Salmonella Dose-Response</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Polynomial Poisson + overdispersion</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Danish Marital Status</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Polynomial contrast Poisson</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Esophageal Cancer</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Case-control, alcohol + tobacco</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Swiss Education</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Correspondence analysis (chi2 = 5260)</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">British Social Mobility</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">6x6 symmetry/quasi-symmetry</p>
  </div>
</div>

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Linear Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Full diagnostics: leverage, Cook's D, VIF</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Logistic Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">RCS, ROC, calibration, interactions</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Poisson Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Overdispersion, quasi-Poisson</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Correspondence Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">SVD of Pearson residuals</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Log-Linear Models</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Contingency table modeling</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Symmetry Tests</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Social mobility patterns</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #2dd4bf; margin: 0;">9 Datasets. 6 Method Families.</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">A comprehensive categorical data analysis toolkit</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">~40%</span><br><span style="color: #aaa;">Smoking odds increase</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Cubic</span><br><span style="color: #aaa;">Best dose-response fit</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Rejected</span><br><span style="color: #aaa;">Mobility symmetry</span></div>
  </div>
</div>

- Log-transformed mpg model resolved non-constant variance issues in car data.
- **Dust exposure** and employment duration were the strongest byssinosis predictors; smoking increased odds by ~40%.
- Political liberalization decreased coup frequency; correspondence analysis revealed distinct education-community profiles.
- Social mobility **symmetry was rejected** — unequal upward vs. downward class transitions.

<div style="margin-top: 25px;">
  <a href="/files/CDA_HW1_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Report 1</a>
  <a href="/files/CDA_HW2_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Report 2</a>
  <a href="/files/CDA_HW3_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Report 3</a>
  <a href="/files/CDA_HW4_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Report 4</a>
  <a href="/files/CDA_HW5_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Report 5</a>
</div>
