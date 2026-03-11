---
title: "Causal Inference and Biological Data Analysis: DAGs, GLMs, Mixed-Effects Models, and Treatment Effect Estimation"
excerpt: "DAG-based causal reasoning, Poisson GLM with offset, logistic regression with ROC/calibration, linear mixed-effects models, GEE, meta-analysis, IPTW, standardization, and doubly robust estimation.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #1e1b4b 0%, #312e81 50%, #4f46e5 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a5b4fc; margin-top: 0; font-size: 1.6em;">From Correlation to Causation — With the Right Tools</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    A deep dive into <strong>causal inference</strong> and <strong>biostatistical modeling</strong> — DAGs for causal reasoning, propensity scores for treatment effects, mixed-effects models for longitudinal data, and meta-analysis for synthesizing evidence across studies.
  </p>
</div>

## Data Source & Cleaning

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">Pregnancy Rate Data</h4>
    <p style="font-size: 0.9em;">1,154 observations — count outcome with offset for years of sexual activity</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">Cardiac Catheterization</h4>
    <p style="font-size: 0.9em;">Case-control study with training/validation split for ROC analysis</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">Orthodontic Growth</h4>
    <p style="font-size: 0.9em;">Longitudinal dental measurements (ages 8-14) with gender effects</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">BCG Vaccine Meta-Analysis</h4>
    <p style="font-size: 0.9em;">7 clinical studies — fixed and random effects synthesis</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">Job Training Causal Data</h4>
    <p style="font-size: 0.9em;">Observational salary data for propensity score methods</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">Causal DAG Structures</h4>
    <p style="font-size: 0.9em;">Unmeasured confounders, colliders, instrumental variables</p>
  </div>
</div>

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Poisson GLM</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Rate modeling with offset + quasi-Poisson</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Logistic + ROC</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">AUC = 0.809, calibration plots</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">DAG Reasoning</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Adjustment sets, collider bias, IVs</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Mixed-Effects</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Random intercept + slope via lme4</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">GEE</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Marginal models, QIC/CIC selection</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">IPTW + DR</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Propensity scores, doubly robust</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 200px; text-align: center;">
      <p style="font-size: 2em; font-weight: bold; color: #a5b4fc; margin: 5px 0;">AUC 0.809</p>
      <p style="color: #aaa;">Cardiac disease logistic model</p>
    </div>
    <div style="flex: 1; min-width: 200px; text-align: center;">
      <p style="font-size: 2em; font-weight: bold; color: #a5b4fc; margin: 5px 0;">OR 0.62</p>
      <p style="color: #aaa;">BCG vaccine effect (p < 0.001)</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">IPTW</span><br><span style="color: #aaa;">Significant training effect</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">p < 0.05</span><br><span style="color: #aaa;">Gender growth differences</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">B = 500</span><br><span style="color: #aaa;">Bootstrap for DR inference</span></div>
  </div>
</div>

- Age was the strongest predictor of pregnancy rate; overdispersion required variance inflation.
- Boys and girls had significantly different dental growth slopes (Kenward-Roger test).
- **BCG vaccine** significantly lowered TB risk in both fixed and random effects meta-analysis.
- **IPTW**, standardization, and doubly robust estimators all confirmed a positive causal effect of job training on salary.

<div style="margin-top: 25px;">
  <a href="/files/BDA_HW1_GLM.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">GLM Analysis</a>
  <a href="/files/BDA_HW2_Causal.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Causal DAGs</a>
  <a href="/files/BDA_Midterm_Mixed_Effects.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Mixed-Effects & GEE</a>
  <a href="/files/BDA_Term_Causal_Inference.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Causal Inference</a>
</div>
