---
title: "Survival Analysis: Nonparametric Estimation and Censored Data Modeling"
excerpt: "Kaplan-Meier estimation, hazard functions, log-rank tests, and Cox proportional hazards models applied to clinical and reliability data.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #7f1d1d 0%, #b91c1c 50%, #ef4444 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fecaca; margin-top: 0; font-size: 1.6em;">Modeling Time-to-Event with Incomplete Observations</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Right-censored survival data demands specialized methods. From <strong>Kaplan-Meier curves</strong> to <strong>parametric hazard models</strong> — building the foundations of survival analysis on clinical and reliability data.
  </p>
</div>

## Data Source & Cleaning

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #fef2f2; border-left: 5px solid #ef4444; padding: 20px; border-radius: 8px;">
    <h3 style="color: #7f1d1d; margin-top: 0;">Simulated Reliability Data</h3>
    <p>Lifetime data following <strong>exponential</strong> and <strong>Weibull</strong> distributions for deriving theoretical properties of survival and hazard functions.</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fff7ed; border-left: 5px solid #f97316; padding: 20px; border-radius: 8px;">
    <h3 style="color: #9a3412; margin-top: 0;">Clinical Survival Data</h3>
    <p><strong>43 survival times</strong> with right-censoring, requiring careful handling of incomplete observations in all estimation procedures.</p>
  </div>
</div>

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Kaplan-Meier</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Nonparametric survival curves + Greenwood variance</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Exponential MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Closed-form Fisher information</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Weibull Model</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Flexible increasing/decreasing hazards</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Log-Rank Test</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Two-sample survival comparison</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Nelson-Aalen</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Cumulative hazard estimation</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fca5a5; margin: 0;">Surviving Censored Data</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">Nonparametric and parametric methods for incomplete time-to-event data</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">O(1/n)</span><br><span style="color: #aaa;">MLE variance scaling</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">KM</span><br><span style="color: #aaa;">Handles censoring</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Weibull</span><br><span style="color: #aaa;">Flexible hazard shapes</span></div>
  </div>
</div>

- Kaplan-Meier estimator appropriately handles right-censored data with consistent survival function estimates.
- Exponential MLE has variance scaling as **O(1/n)** with explicit closed-form expressions derived.
- Weibull model captured both increasing and decreasing hazard patterns via the shape parameter.

---

## Final Project: Liver Cirrhosis Survival Modeling

<div style="background: linear-gradient(135deg, #4a1942 0%, #7b2d5f 50%, #c2185b 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #f8bbd0; margin-top: 0; font-size: 1.3em;">Stage-Stratified Cox PH with Forward Variable Selection</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    A comprehensive survival analysis of the <strong>Mayo Clinic primary biliary cirrhosis</strong> dataset — stratifying patients by disease stage (1&2, 3, 4) and applying <strong>custom-implemented</strong> Cox partial likelihood optimization with forward variable selection and cross-validation.
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Cox PH Model</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Hand-coded partial likelihood + L-BFGS-B optimization</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Forward Selection</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Deviance-based with 3-fold CV</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Stage Stratification</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Separate models per disease severity</p>
  </div>
</div>

<div style="background: #1a1a2e; padding: 20px; border-radius: 10px; margin: 20px 0; text-align: center;">
  <p style="color: #f8bbd0; font-size: 1.3em; font-weight: bold; margin: 0;">Key Finding</p>
  <p style="color: #ccc; margin-top: 8px; font-size: 1.05em;"><strong style="color: #f48fb1;">Bilirubin</strong> was selected across <strong style="color: #7fecb3;">100%</strong> of CV seeds in all disease stages — the most consistent predictor of survival in cirrhosis patients.</p>
</div>

<div style="margin-top: 25px;">
  <a href="/files/SA_HW1_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">Download HW1 (PDF)</a>
  <a href="/files/SA_HW2_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">Download HW2 (PDF)</a>
  <a href="/files/SA_Final_Survival.pdf" style="display: inline-block; background: #880e4f; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Final Project (PDF)</a>
</div>
