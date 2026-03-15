---
title: "分類方法：乳癌診斷"
permalink: /zh/portfolio/classification/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #4a1942 0%, #893168 50%, #c94b8c 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ffb6d9; margin-top: 0; font-size: 1.6em;">演算法能否區分良性與惡性腫瘤？</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    在 Wisconsin Breast Cancer 資料集上進行 <strong>6 種分類方法</strong>的正面對決。從 Logistic Regression 到 KNN，每個分類器都在 683 個腫瘤樣本、9 項細胞特徵上接受嚴格考驗。
  </p>
</div>

## 資料來源與處理

**Wisconsin Breast Cancer Data**（UCI / R `mlbench`）：699 筆觀測值，包含 9 個序數型預測變數（描述細胞特徵）與 1 個二元目標變數（良性 vs. 惡性）。移除 16 筆含缺失值的觀測後，以 90/10 比例進行訓練-測試分割，並透過密度方法進行驗證。

## 探索性資料分析（EDA）

- 所有預測變數均呈現強烈右偏，雙峰模式反映出兩類結構。
- 配對散佈圖顯示良性與惡性病例的分布明顯不同——每個預測變數都具有鑑別力。
- 預測變數之間存在高度相關性，建模時需加以留意。

## 方法——6 種分類器正面對決

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">Logistic Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">逐步選擇 + 交互項</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">LDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">線性判別分析</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">QDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">允許不等共變異數矩陣</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">Naive Bayes</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Gaussian + 無母數核密度</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">KNN</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">交叉驗證最佳化 k</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">ROC/AUC</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">完整比較框架</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2.5em; font-weight: bold; color: #ffb6d9; margin: 0;">AUC > 0.98</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">所有分類器均達此水準——印證資料具有很強的可分離性</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">95%+</span><br><span style="color: #aaa;">測試準確率</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3</span><br><span style="color: #aaa;">個關鍵預測變數</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">683</span><br><span style="color: #aaa;">腫瘤樣本</span></div>
  </div>
</div>

- **Cell.size**、**Bare.nuclei** 和 **Bl.cromatin** 在各方法中一致被識別為最具影響力的預測變數。
- QDA 和無母數 Naive Bayes 放寬了分布假設後略有提升。
- KNN 在最佳 k 值下表現具競爭力，但可解釋性相對較低。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW2_Classification.pdf" style="display: inline-block; background: #893168; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載完整報告（PDF）</a>
</div>
