---
title: "Nonparametric Curve Estimation: Density Estimation, Kernel Regression, Splines, and Local Methods"
excerpt: "Histogram and kernel density estimation, bandwidth selection, multivariate KDE, local polynomial regression, smoothing splines, penalized regression, cross-validation, and generalized additive models.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #064e3b 0%, #047857 50%, #34d399 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a7f3d0; margin-top: 0; font-size: 1.6em;">No Assumptions? No Problem.</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    When parametric models are too rigid, <strong>nonparametric methods</strong> let the data speak. From kernel density estimation to <strong>GAMs</strong> — exploring the full spectrum of assumption-free curve estimation across <strong>9 reports</strong>.
  </p>
</div>

## Methods — Two Pillars of Nonparametric Estimation

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 300px; background: #ecfdf5; border-left: 5px solid #34d399; padding: 20px; border-radius: 8px;">
    <h3 style="color: #064e3b; margin-top: 0;">Density Estimation (Reports 1, 3-6)</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Histograms</strong><br><span style="color: #666;">Bin origin effects</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Kernel DE</strong><br><span style="color: #666;">Gaussian, Epanechnikov</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Bandwidth</strong><br><span style="color: #666;">LSCV, plug-in, ROT</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Multivariate</strong><br><span style="color: #666;">Product kernels</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Boundary</strong><br><span style="color: #666;">Reflection methods</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Parametric MLE</strong><br><span style="color: #666;">Beta benchmark</span>
      </div>
    </div>
  </div>
  <div style="flex: 1; min-width: 300px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #14532d; margin-top: 0;">Nonparametric Regression (Reports 7-10)</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Local Polynomial</strong><br><span style="color: #666;">Linear & quadratic</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Nadaraya-Watson</strong><br><span style="color: #666;">Kernel regression</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Smoothing Splines</strong><br><span style="color: #666;">GCV parameter selection</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Penalized Splines</strong><br><span style="color: #666;">B-spline + roughness</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">GAMs</strong><br><span style="color: #666;">Additive models via mgcv</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Mixed Model</strong><br><span style="color: #666;">Spline-random effects link</span>
      </div>
    </div>
  </div>
</div>

## Key Results

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #34d399; margin: 0;">Bandwidth > Kernel Choice</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">The fundamental insight: how much you smooth matters more than how you smooth</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">LSCV</span><br><span style="color: #aaa;">Best bandwidth selector</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Local Linear</span><br><span style="color: #aaa;">No boundary bias</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">9 Reports</span><br><span style="color: #aaa;">Comprehensive coverage</span></div>
  </div>
</div>

- Data-driven bandwidth selection consistently outperformed fixed-bandwidth approaches.
- Kernel choice (Gaussian vs. Epanechnikov) mattered far less than bandwidth — the **bias-variance tradeoff** is paramount.
- Local linear regression avoided boundary bias that plagued Nadaraya-Watson estimates.
- Smoothing splines with GCV provided excellent fits while preventing overfitting.
- **GAMs** successfully captured nonlinear relationships in multiple predictors simultaneously.

<div style="margin-top: 25px;">
  <a href="/files/NCE_HW1_Density_Estimation.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/NCE_HW3_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/NCE_HW4_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/NCE_HW5_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/NCE_HW6_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/NCE_HW7_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW7</a>
  <a href="/files/NCE_HW8_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW8</a>
  <a href="/files/NCE_HW9_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW9</a>
  <a href="/files/NCE_HW10_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW10</a>
</div>
