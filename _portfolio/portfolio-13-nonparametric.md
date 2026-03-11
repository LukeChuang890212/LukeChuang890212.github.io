---
title: "Nonparametric Curve Estimation: Density Estimation and Kernel Methods"
excerpt: "Histogram construction, parametric MLE fitting, kernel density estimation with bandwidth selection, and comparison of smoothing approaches.<br/>"
collection: portfolio
---

## Data Source & Cleaning

- **Simulated Uniform Data**: 100 random samples from Uniform(0,1), used to study the effect of bin origin and bandwidth on histogram density estimation.
- **Beta Distribution Data**: Samples used for parametric (MLE) and nonparametric (kernel) density estimation comparison.

## Exploratory Data Analysis (EDA)

- Histograms with rug plots visualized the raw data distribution.
- Varying the bin origin (t_0 = 0 vs. t_0 = -0.1) demonstrated sensitivity of histogram shape to this arbitrary choice.
- Bandwidth variation (0.2 vs. 0.1) showed the bias-variance tradeoff: smaller bandwidths produce rougher but more detailed estimates.

## Methods

- **Histogram Density Estimation**: Constructed with different bin origins and bandwidths to illustrate the sensitivity of this simplest nonparametric estimator.
- **Parametric MLE**: Maximum likelihood estimation of Beta(alpha, beta) parameters using `optim` with L-BFGS-B algorithm and positivity constraints. The fitted parametric density served as a benchmark.
- **Kernel Density Estimation**: Gaussian kernel with data-driven bandwidth selection. Compared against the parametric fit to assess the flexibility advantage of nonparametric methods.
- **Bias-Variance Tradeoff**: Systematic exploration of how smoothing parameter choices affect estimation quality.

## Results & Interpretation

- Histograms are highly sensitive to both bin origin and bandwidth, making them unreliable for precise density estimation despite their visual simplicity.
- The Beta MLE provided a smooth, parametric fit that closely matched the true density when the parametric assumption was correct.
- Kernel density estimation offered a flexible alternative that adapts to the data shape without parametric assumptions, at the cost of requiring bandwidth selection.
- The analysis clearly demonstrated the fundamental bias-variance tradeoff in nonparametric estimation: too little smoothing yields high variance (noisy estimates), while too much smoothing introduces bias (over-smoothed estimates).

[Download Full Report (PDF)](/files/NCE_HW1_Density_Estimation.pdf)
