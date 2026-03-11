---
title: "Cost of Living Analysis: Global City Comparison via Multivariate Methods"
excerpt: "PCA, factor analysis, and clustering applied to global cost-of-living data across 55 expenditure categories to identify city groupings and spending patterns.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #78350f 0%, #b45309 50%, #f59e0b 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fef3c7; margin-top: 0; font-size: 1.6em;">What Makes a City Expensive? A Data-Driven Answer</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    <strong>55 expenditure variables</strong> across cities worldwide — dissected with PCA, factor analysis, and clustering to reveal the hidden structure behind global cost-of-living differences.
  </p>
</div>

## Data Source & Cleaning

A comprehensive cost-of-living dataset covering 8 spending domains:

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; margin: 20px 0;">
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Food & Dining</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">27 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Transportation</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">8 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Facilities</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Entertainment</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Education</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">2 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Clothing</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Housing</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">6 variables</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">Others</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">2 variables</p>
  </div>
</div>

Missing data handled through **multiple imputation**. Data standardized prior to multivariate analysis.

## Exploratory Data Analysis (EDA)

- Large variation in housing and education costs across cities.
- Strong **intra-domain correlations** (food items correlated with each other) and moderate cross-domain correlations.
- Distribution analysis guided standardization decisions.

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">PCA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Main dimensions of variation</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Factor Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Latent spending patterns</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Cluster Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">City groupings by cost profile</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Multiple Imputation</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Missing data handling</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fbbf24; margin: 0;">55 Variables → Interpretable Structure</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">PCA, factor analysis, and clustering reveal the anatomy of global living costs</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">PC1</span><br><span style="color: #aaa;">Overall cost level</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3 Tiers</span><br><span style="color: #aaa;">City cost clusters</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">8 Domains</span><br><span style="color: #aaa;">Factor-validated</span></div>
  </div>
</div>

- **PC1** captured overall cost level; subsequent PCs distinguished specific patterns (e.g., high housing but moderate food).
- Factor analysis aligned with the 8 predefined domain categories — validating domain knowledge.
- Cluster analysis identified **high-cost**, **moderate-cost**, and **low-cost** city groups with nuanced sub-clusters.

<div style="margin-top: 25px;">
  <a href="/files/SL_Final_Cost_of_Living.pdf" style="display: inline-block; background: #b45309; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Full Report (PDF)</a>
</div>
