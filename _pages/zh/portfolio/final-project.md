---
title: "生活成本分析：全球城市多變量方法比較"
layout: single
author_profile: true
permalink: /zh/portfolio/final-project/
---


<div style="background: linear-gradient(135deg, #78350f 0%, #b45309 50%, #f59e0b 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fef3c7; margin-top: 0; font-size: 1.6em;">是什麼讓一座城市變得昂貴？用數據找答案</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    涵蓋全球各城市的 <strong>55 個支出變數</strong>——透過 PCA、因素分析與集群分析，解構全球生活成本差異背後的隱藏結構。
  </p>
</div>

## 資料來源與處理

一個涵蓋 8 大消費領域的綜合生活成本資料集：

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; margin: 20px 0;">
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">飲食</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">27 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">交通</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">8 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">公共設施</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">娛樂</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">教育</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">2 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">服飾</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">住房</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">6 個變數</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">其他</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">2 個變數</p>
  </div>
</div>

缺失資料透過 **Multiple Imputation** 處理。分析前先對資料進行標準化。

## 探索性資料分析（EDA）

- 各城市間住房與教育成本的差異極大。
- 同一領域內的變數高度相關（如食品項目之間彼此關聯），跨領域相關性則為中等。
- 分布特徵分析為標準化方式的選擇提供了依據。

## 分析方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">PCA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">萃取主要變異方向</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Factor Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">挖掘潛在消費模式</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Cluster Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">依成本特徵為城市分群</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">Multiple Imputation</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">缺失資料處理</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fbbf24; margin: 0;">55 個變數 → 可解讀的結構</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">PCA、因素分析與集群分析揭示全球生活成本的組成面貌</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">PC1</span><br><span style="color: #aaa;">整體成本水準</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3 層級</span><br><span style="color: #aaa;">城市成本分群</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">8 領域</span><br><span style="color: #aaa;">因素分析驗證</span></div>
  </div>
</div>

- **PC1** 捕捉了整體成本水準；後續主成分則區分出特定模式（例如高住房但中等食品成本的城市）。
- 因素分析的結果與預設的 8 大領域分類高度吻合，驗證了領域知識的合理性。
- 集群分析辨識出**高成本**、**中等成本**與**低成本**三個城市群，內部還包含更細緻的子群。

<div style="margin-top: 25px;">
  <a href="/files/SL_Final_Cost_of_Living.pdf" style="display: inline-block; background: #b45309; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載完整報告（PDF）</a>
</div>
