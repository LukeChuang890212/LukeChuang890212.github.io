---
title: "SVM & Unsupervised Learning: High-Dimensional Image Classification"
excerpt: "Support vector machines with PCA-based dimensionality reduction, t-SNE visualization, and clustering for casting defect detection.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #4c1d95 0%, #6d28d9 50%, #8b5cf6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #c4b5fd; margin-top: 0; font-size: 1.6em;">Detecting Defects in 10,000-Dimensional Space</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Raw images flattened into massive feature vectors, then tamed with <strong>PCA</strong>, visualized with <strong>t-SNE</strong>, and classified with <strong>SVM</strong> — a complete pipeline from pixels to predictions for casting defect detection.
  </p>
</div>

## Data Source & Cleaning

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f5f3ff; border-left: 5px solid #8b5cf6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #4c1d95; margin-top: 0;">Large-Scale Image Classification</h3>
    <p>High-dimensional dataset standardized to unit variance. <strong>PCA</strong> applied for dimensionality reduction. Eigen decomposition computed on the scaled data matrix.</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fdf4ff; border-left: 5px solid #a855f7; padding: 20px; border-radius: 8px;">
    <h3 style="color: #701a75; margin-top: 0;">Casting Defect Detection</h3>
    <p><strong>100x100 pixel</strong> grayscale images of casting products. Each image flattened into a 10,000-dimensional feature vector. Goal: defective vs. non-defective classification.</p>
  </div>
</div>

## Exploratory Data Analysis (EDA)

- **Scree plots** and cumulative variance plots guided principal component selection.
- **t-SNE embeddings** (perplexity 3 and 7) revealed natural cluster structures in high-dimensional space.
- **Heatmaps** of image data showed spatial patterns distinguishing defective from non-defective castings.

## Methods

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">PCA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Dimensionality reduction preprocessing</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">SVM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV-tuned kernel & cost</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Benchmark classifier</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">Logistic on PCs</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">BIC-based selection</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">t-SNE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Nonlinear visualization</p>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #c4b5fd; margin: 0;">Pixels to Predictions</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">Complete pipeline: raw images → PCA → SVM → defect classification</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">10,000→k</span><br><span style="color: #aaa;">Dimensions reduced</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">SVM</span><br><span style="color: #aaa;">Best classifier</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">t-SNE</span><br><span style="color: #aaa;">Clear cluster separation</span></div>
  </div>
</div>

- PCA effectively reduced dimensionality while retaining discriminative power.
- **SVM** with tuned kernel achieved excellent defect detection performance.
- t-SNE confirmed well-separated clusters — validating automated defect detection feasibility.

<div style="margin-top: 25px;">
  <a href="/files/SL_HW5_SVM_Unsupervised.pdf" style="display: inline-block; background: #6d28d9; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">Download Full Report (PDF)</a>
</div>
