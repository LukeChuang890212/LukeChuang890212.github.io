---
title: "SVM 與非監督式學習：高維影像分類"
permalink: /zh/portfolio/svm-unsupervised/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #4c1d95 0%, #6d28d9 50%, #8b5cf6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #c4b5fd; margin-top: 0; font-size: 1.6em;">在萬維空間中檢測缺陷</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    將原始影像展平為龐大的特徵向量，再用 <strong>PCA</strong> 降維、<strong>t-SNE</strong> 視覺化、<strong>SVM</strong> 分類——一條從像素到預測的完整流水線，用於鑄造缺陷檢測。
  </p>
</div>

## 資料來源與清理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f5f3ff; border-left: 5px solid #8b5cf6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #4c1d95; margin-top: 0;">大規模影像分類</h3>
    <p>高維資料集標準化至單位變異數。使用 <strong>PCA</strong> 進行降維，在縮放後的資料矩陣上做特徵值分解。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fdf4ff; border-left: 5px solid #a855f7; padding: 20px; border-radius: 8px;">
    <h3 style="color: #701a75; margin-top: 0;">鑄造缺陷檢測</h3>
    <p><strong>100x100 像素</strong>的灰階鑄造產品影像。每張影像展平為 10,000 維特徵向量。目標：缺陷品 vs. 合格品分類。</p>
  </div>
</div>

## 探索性資料分析（EDA）

- **碎石圖**與累積變異數解釋圖用於指導主成分數量的選擇。
- **t-SNE 嵌入**（perplexity 為 3 和 7）揭示了高維空間中天然的群聚結構。
- 影像資料的**熱力圖**展現出區分缺陷品與合格品的空間模式。

## 方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">PCA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">降維預處理</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">SVM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">交叉驗證調校核函數與代價參數</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">基準分類器</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">Logistic on PCs</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">基於 BIC 的模型選擇</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">t-SNE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">非線性視覺化</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #c4b5fd; margin: 0;">從像素到預測</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">完整流水線：原始影像 → PCA → SVM → 缺陷分類</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">10,000→k</span><br><span style="color: #aaa;">維度大幅縮減</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">SVM</span><br><span style="color: #aaa;">最佳分類器</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">t-SNE</span><br><span style="color: #aaa;">清晰的群聚分離</span></div>
  </div>
</div>

- PCA 在保留判別資訊的同時有效降低了維度。
- 調校後的 **SVM** 在缺陷檢測中取得了優異表現。
- t-SNE 證實了各類別之間良好的分離度——驗證了自動化缺陷檢測的可行性。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW5_SVM_Unsupervised.pdf" style="display: inline-block; background: #6d28d9; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載完整報告（PDF）</a>
</div>
