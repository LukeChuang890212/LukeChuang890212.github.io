---
title: "線性模型：迴歸理論、診斷、加權最小平方法與時間序列建模"
layout: single
author_profile: true
permalink: /zh/portfolio/linear-model/
---


<div style="background: linear-gradient(135deg, #1e3a5f 0%, #2563eb 50%, #60a5fa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #bfdbfe; margin-top: 0; font-size: 1.6em;">完整的線性模型工具箱 — 深入 7 份報告</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    從 OLS 基礎到 <strong>WLS</strong>、<strong>GLS + AR(1)</strong>、<strong>B-splines</strong> 與<strong>變點模型</strong> — 全面的線性模型理論應用於賭博、製造業、薪資、身高、CEO 薪酬及 150 年溫度資料。
  </p>
</div>

## 資料來源與清理

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">青少年賭博</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">47 筆觀測，性別/地位/收入/語文能力</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">化學製程</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">蒸氣、速度、溫度交互作用</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">美國薪資</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">教育 + 經驗，巢狀 F 檢定</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">廢棄物資料</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">信賴橢圓、聯立推論</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Galton 身高</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">不等組別大小的 WLS</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">CEO 薪酬</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">離群值、變異數穩定化</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Ann Arbor 溫度</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">約 150 年，AR(1)、Splines、變點</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">印度嬰兒死亡率</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">性別 + 城鄉虛擬變數</p>
  </div>
</div>

## 方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">OLS + F-Tests</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">巢狀模型比較</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">完整診斷</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">槓桿值、Cook's D、DFBETAS</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">WLS</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">分組資料的加權</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GLS + AR(1)</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">時間序列中的相關誤差</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Splines</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Cubic B-splines，6 個基底函數</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Changepoint Model</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">1930 年結構斷裂</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #60a5fa; margin: 0;">150 年暖化趨勢 — 已確認</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">1930 年後的溫度趨勢在 AR(1) 校正後仍然顯著</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">rho = 0.23</span><br><span style="color: #aaa;">AR(1) 自相關</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Spline</span><br><span style="color: #aaa;">最佳 RMSE 模型</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">7 份報告</span><br><span style="color: #aaa;">分析 8 個資料集</span></div>
  </div>
</div>

- 診斷分析發現槓桿點、離群值與異質變異數 — 引導模型改進。
- WLS 適當處理了分組身高資料中的不等精確度。
- **1930 年後的暖化趨勢**在 AR(1) 校正（rho = 0.23）後仍獲確認。
- Cubic B-spline 迴歸達到最佳 RMSE，捕捉非線性溫度波動。

<div style="margin-top: 25px;">
  <a href="/files/LM_HW1_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/LM_HW2_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/LM_HW3_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/LM_HW4_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/LM_HW5_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/LM_HW6_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/LM_HW7_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW7</a>
</div>
