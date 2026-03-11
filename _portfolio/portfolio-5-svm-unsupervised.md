---
title: "SVM & Unsupervised Learning: High-Dimensional Image Classification"
excerpt: "Support vector machines with PCA-based dimensionality reduction, t-SNE visualization, and clustering for casting defect detection.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Two problems involving high-dimensional image data were analyzed:

- **Problem 1 — Large-Scale Image Classification**: A high-dimensional dataset requiring substantial preprocessing. Data was standardized to unit variance. PCA was applied for dimensionality reduction before classification. Eigen decomposition was computed on the scaled data matrix.
- **Problem 2 — Casting Defect Detection**: 100x100 pixel grayscale images of casting products, with the goal of classifying defective vs. non-defective items. Images were flattened into feature vectors for analysis.

## Exploratory Data Analysis (EDA)

- **PCA Visualization**: Eigenvalue decomposition revealed the effective dimensionality of the data. Scree plots and cumulative variance plots guided the selection of principal components.
- **t-SNE Embedding**: t-SNE with different perplexity settings (3 and 7) was used to produce 2D visualizations, revealing natural cluster structures in the high-dimensional data.
- **Heatmap Analysis**: Heatmaps of the image data and correlation structures provided insight into spatial patterns distinguishing defective from non-defective castings.

## Methods

- **Principal Component Analysis (PCA)**: Used as a preprocessing step for dimensionality reduction before classification, retaining components that explained sufficient variance.
- **Support Vector Machine (SVM)**: Tuned via cross-validation with different kernel functions; applied on both the original and PCA-reduced feature spaces.
- **Random Forest**: Used as a benchmark classifier alongside SVM.
- **Logistic Regression**: Applied on the PCA-reduced features with BIC-based model selection.
- **t-SNE**: Nonlinear dimensionality reduction for visualization and exploratory analysis.
- **Cross-Validation**: Systematic hyperparameter tuning for SVM (cost parameter, kernel choice) and random forest.

## Results & Interpretation

- PCA effectively reduced dimensionality while retaining discriminative power, enabling efficient SVM training on very high-dimensional image data.
- SVM achieved strong classification performance, with the tuned model demonstrating excellent ability to distinguish defective from non-defective castings.
- Comparison across classifiers (SVM, random forest, logistic regression on PCs) showed that SVM performed competitively, particularly on the PCA-reduced features.
- t-SNE visualizations confirmed the presence of well-separated clusters, validating the feasibility of automated defect detection.
- The project demonstrated a complete pipeline from raw image data to classification: preprocessing, dimensionality reduction, model training, and evaluation.

[Download Full Report (PDF)](/files/SL_HW5_SVM_Unsupervised.pdf)
