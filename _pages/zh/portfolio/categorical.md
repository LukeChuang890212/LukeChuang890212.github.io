---
title: "類別資料分析：GLMs、Logistic 迴歸、Poisson 模型與對應分析"
layout: single
author_profile: true
permalink: /zh/portfolio/categorical/
---


<div style="background: linear-gradient(135deg, #134e4a 0%, #0d9488 50%, #2dd4bf 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #99f6e4; margin-top: 0; font-size: 1.6em;">計數、類別與列聯表</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    全面涵蓋<strong>類別資料方法</strong>——從疾病風險的 Logistic 迴歸、計數資料的 Poisson 模型，到列聯表的對應分析，以及社會流動模式的對稱性檢定。橫跨 5 份報告，分析 <strong>9 個真實資料集</strong>。
  </p>
</div>

## 資料來源與處理

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Motor Trend Cars</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">32 輛汽車，mpg + 10 個預測變數</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">心導管檢查</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">含 RCS 的 Logistic 迴歸</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">棉塵肺職業病</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">64 個共變數組合，二元結果</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">非洲軍事政變</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">計數資料，政治相關預測變數</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">沙門氏菌劑量反應</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">多項式 Poisson + 過度離散</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">丹麥婚姻狀態</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">多項式對比 Poisson</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">食道癌</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">病例對照研究，酒精 + 菸草</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">瑞士教育</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">Correspondence Analysis (chi2 = 5260)</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">英國社會流動</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">6x6 對稱性/準對稱性</p>
  </div>
</div>

## 分析方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Linear Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">完整診斷：槓桿值、Cook's D、VIF</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Logistic Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">RCS、ROC、校正曲線、交互作用</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Poisson Regression</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">過度離散、Quasi-Poisson</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Correspondence Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Pearson 殘差的 SVD 分解</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Log-Linear Models</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">列聯表建模</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">Symmetry Tests</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">社會流動模式檢定</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #2dd4bf; margin: 0;">9 個資料集，6 大方法類別</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">完整的類別資料分析工具箱</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">~40%</span><br><span style="color: #aaa;">吸菸勝算比增幅</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Cubic</span><br><span style="color: #aaa;">最佳劑量反應擬合</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">拒絕</span><br><span style="color: #aaa;">流動對稱性</span></div>
  </div>
</div>

- 對 mpg 取對數的模型有效解決了汽車資料的異質變異數問題。
- **粉塵暴露**與就業年資是棉塵肺最強的預測因子；吸菸使勝算比增加約 40%。
- 政治自由化降低了政變發生頻率；Correspondence Analysis 揭示了不同教育程度與社區類型之間的對應關係。
- 社會流動的**對稱性被拒絕**——向上與向下的階層流動並不對等。

<div style="margin-top: 25px;">
  <a href="/files/CDA_HW1_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">報告 1</a>
  <a href="/files/CDA_HW2_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">報告 2</a>
  <a href="/files/CDA_HW3_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">報告 3</a>
  <a href="/files/CDA_HW4_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">報告 4</a>
  <a href="/files/CDA_HW5_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">報告 5</a>
</div>
