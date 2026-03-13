---
title: "樹模型與集成學習：自行車共享與航空滿意度"
permalink: /zh/portfolio/tree-ensemble/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <strong>中文</strong> | <a href="/ja/portfolio/">日本語</a></div>

<div style="background: linear-gradient(135deg, #1a4731 0%, #065f46 50%, #059669 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #6ee7b7; margin-top: 0; font-size: 1.6em;">當一棵樹不夠時——集成方法登場</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    從單一決策樹到 <strong>Random Forest</strong> 和 <strong>Gradient Boosting</strong>——在 <strong>731 筆自行車共享</strong>記錄和 <strong>103K 筆航空滿意度</strong>調查上，將樹模型方法推到極限。
  </p>
</div>

## 資料來源與清理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #065f46; margin-top: 0;">自行車共享資料</h3>
    <p><strong>731 筆每日觀測值</strong>（2011-2012），含 11 個預測因子：季節、天氣、溫度、濕度、風速等。反應變數：每日自行車使用數量。80/20 訓練-測試分割。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fef3c7; border-left: 5px solid #d97706; padding: 20px; border-radius: 8px;">
    <h3 style="color: #92400e; margin-top: 0;">航空滿意度調查</h3>
    <p><strong>103,594 筆觀測值</strong>，含 23 個預測因子：人口統計、旅行資訊、14 項服務評分、延誤指標。二元結果：滿意 vs. 不滿意。80/20 分割。</p>
  </div>
</div>

## 探索性資料分析（EDA）

- **自行車共享**：溫度顯示最強的正相關（r = 0.627）。檢測到二次溫度效應——使用量在約 20°C 達到峰值後下降。
- **航空**：服務評分具有強鑑別力。大多數客戶為忠實商務旅客。延誤呈嚴重右偏分佈。

## 方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Decision Tree</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">透過 cost-complexity CV 進行剪枝</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV 調參 m 參數</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Gradient Boosting</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">網格搜索：深度、學習率、樹數</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Linear Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Best Subset 基準模型</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Nonlinear Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">多項式 + B-splines</p>
  </div>
  <div style="background: #fef3c7; border: 2px solid #d97706; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Noise Injection Test</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">驗證重要性排名</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #6ee7b7; margin: 5px 0;">集成方法勝出</p>
      <p style="color: #aaa;">RF 和 GBM 在自行車資料上優於單一樹和線性模型</p>
    </div>
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #fbbf24; margin: 5px 0;">103K 份調查</p>
      <p style="color: #aaa;">航空分類搭配噪聲驗證的重要性排名</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">Year + Temp</span><br><span style="color: #aaa;">自行車最重要預測因子</span></div>
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">Online Boarding</span><br><span style="color: #aaa;">航空最重要預測因子</span></div>
  </div>
</div>

- **Year** 和**溫度**在所有方法中一致排名為自行車共享的最重要預測因子。
- B-spline 迴歸比多項式模型更好地捕捉了溫度閾值效應。
- 線上登機、機上 Wi-Fi 和旅行類型是滿意度的主要驅動因子——經噪聲變數注入驗證。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW4_Tree_Methods.pdf" style="display: inline-block; background: #065f46; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載完整報告（PDF）</a>
</div>
