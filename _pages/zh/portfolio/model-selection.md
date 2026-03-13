---
title: "模型選擇與正則化：化學製程良率預測"
permalink: /zh/portfolio/model-selection/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #0a2463 0%, #1e3a8a 50%, #3b82f6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #93c5fd; margin-top: 0; font-size: 1.6em;">6 種方法、57 個預測因子——哪些真正重要？</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    在高維化學製造資料集上，系統性地比較 <strong>6 種變數選擇與正則化方法</strong>——從 Forward/Backward Selection 到 Lasso 和 Ridge——揭示持續驅動產品良率的關鍵預測因子。
  </p>
</div>

## 資料來源與清理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #3b82f6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #1e3a8a; margin-top: 0;">化學製造資料</h3>
    <p><strong>177 個樣本</strong>，57 個預測因子（12 個生物學 + 45 個製程測量值）及產品良率作為反應變數。移除缺失值，預測因子標準化。90/10 訓練-測試分割。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #15803d; margin-top: 0;">Bootstrap 穩健性研究</h3>
    <p>含污染的資料集，比較標準估計量與 <strong>MAD 穩健估計量</strong>在母體標準差估計上的表現，透過無母數 Bootstrap（B = 10,000）進行。</p>
  </div>
</div>

## 探索性資料分析（EDA）

- 預測因子間的尺度差異大，需要標準化以進行公平比較。
- 許多預測因子間具有高相關性，支持降維方法的使用。
- 少數預測因子與 Yield 具有強邊際關聯——符合**稀疏性原則**。
- P12、P28、P40-P43 呈偏態分佈；P25-P31 檢測到離群值。

## 方法——6 種選擇程序比較

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">1</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Forward Selection</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">選出 5 個預測因子</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">2</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Backward Selection</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">選出 3 個預測因子</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">3</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Best Subset</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">選出 5 個預測因子</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">4</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">PCR</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">保留 6 個主成分</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">5</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Lasso</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">7 個預測因子（精煉後）</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">6</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Ridge</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 個預測因子（最大係數）</p>
  </div>
</div>

所有方法均透過 **5-fold 交叉驗證**進行公平比較。

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #93c5fd; margin: 0;">Lasso 在 CV 穩定性上勝出</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">修正後的 Lasso（模型 5）達成最小且最穩定的測試 MSE</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">P33 & P34</span><br><span style="color: #aaa;">一致的最重要預測因子</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">57 → 3-7</span><br><span style="color: #aaa;">維度縮減</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">B=10,000</span><br><span style="color: #aaa;">Bootstrap 重複次數</span></div>
  </div>
</div>

- **P33** 和 **P34** 在多種方法中被一致識別為最重要的預測因子，兩者均與 Yield 呈正相關。
- PCR 達到最低的測試集 RMSE，而 Lasso 提供最佳的 CV 穩定性。
- 穩健 MAD 估計量在存在離群值時，變異數顯著低於標準估計量。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW3_Resampling_Regularization.pdf" style="display: inline-block; background: #1e3a8a; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載完整報告（PDF）</a>
</div>
