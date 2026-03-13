---
title: "因果推論與生物資料分析"
layout: single
author_profile: true
permalink: /zh/portfolio/causal-inference/
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <strong>中文</strong> | <a href="/ja/portfolio/">日本語</a></div>

<div style="background: linear-gradient(135deg, #1e1b4b 0%, #312e81 50%, #4f46e5 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a5b4fc; margin-top: 0; font-size: 1.6em;">從相關到因果 — 用正確的工具</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    深入探討<strong>因果推論</strong>與<strong>生物統計建模</strong> — 以 DAGs 進行因果推理、傾向分數估計處理效果、混合效果模型分析縱向資料，以及 Meta-Analysis 綜合跨研究證據。
  </p>
</div>

## 資料來源與清理

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">懷孕率資料</h4>
    <p style="font-size: 0.9em;">1,154 筆觀測 — 以性活動年數為 offset 的計數結果</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">心導管檢查</h4>
    <p style="font-size: 0.9em;">病例對照研究，含訓練/驗證分割進行 ROC 分析</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">齒顎生長資料</h4>
    <p style="font-size: 0.9em;">縱向牙齒測量（8-14 歲）含性別效果</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">BCG 疫苗 Meta-Analysis</h4>
    <p style="font-size: 0.9em;">7 項臨床研究 — 固定效果與隨機效果綜合分析</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">職訓因果資料</h4>
    <p style="font-size: 0.9em;">觀測性薪資資料，用於傾向分數方法</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">因果 DAG 結構</h4>
    <p style="font-size: 0.9em;">未測量干擾因子、碰撞器、工具變數</p>
  </div>
</div>

## 方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Poisson GLM</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">含 offset 的比率建模 + Quasi-Poisson</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Logistic + ROC</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">AUC = 0.809，校正圖</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">DAG 推理</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">調整集合、碰撞器偏誤、工具變數</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Mixed-Effects</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">隨機截距 + 斜率（lme4）</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">GEE</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">邊際模型，QIC/CIC 選擇</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">IPTW + DR</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">傾向分數、雙重穩健估計</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 200px; text-align: center;">
      <p style="font-size: 2em; font-weight: bold; color: #a5b4fc; margin: 5px 0;">AUC 0.809</p>
      <p style="color: #aaa;">心臟疾病 Logistic 模型</p>
    </div>
    <div style="flex: 1; min-width: 200px; text-align: center;">
      <p style="font-size: 2em; font-weight: bold; color: #a5b4fc; margin: 5px 0;">OR 0.62</p>
      <p style="color: #aaa;">BCG 疫苗效果 (p < 0.001)</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">IPTW</span><br><span style="color: #aaa;">顯著的職訓效果</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">p < 0.05</span><br><span style="color: #aaa;">性別生長差異</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">B = 500</span><br><span style="color: #aaa;">Bootstrap DR 推論</span></div>
  </div>
</div>

- 年齡是懷孕率最強的預測因子；過度離散需要變異數膨脹校正。
- 男女生的牙齒生長斜率有顯著差異（Kenward-Roger 檢定）。
- **BCG 疫苗**在固定效果與隨機效果 Meta-Analysis 中均顯著降低結核病風險。
- **IPTW**、標準化與雙重穩健估計量均確認職業訓練對薪資有正向因果效果。

<div style="margin-top: 25px;">
  <a href="/files/BDA_HW1_GLM.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">GLM 分析</a>
  <a href="/files/BDA_HW2_Causal.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">因果 DAGs</a>
  <a href="/files/BDA_Midterm_Mixed_Effects.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">Mixed-Effects & GEE</a>
  <a href="/files/BDA_Term_Causal_Inference.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">因果推論</a>
</div>
