---
title: "存活分析：無母數估計與設限資料建模"
layout: single
author_profile: true
permalink: /zh/portfolio/survival-analysis/
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <strong>中文</strong> | <a href="/ja/portfolio/">日本語</a></div>

<div style="background: linear-gradient(135deg, #7f1d1d 0%, #b91c1c 50%, #ef4444 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fecaca; margin-top: 0; font-size: 1.6em;">在不完整觀測下建模事件發生時間</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    右設限存活資料需要專門的方法。從 <strong>Kaplan-Meier 曲線</strong>到<strong>參數化危險函數模型</strong> — 在臨床與可靠度資料上建立存活分析的基礎。
  </p>
</div>

## 資料來源與清理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #fef2f2; border-left: 5px solid #ef4444; padding: 20px; border-radius: 8px;">
    <h3 style="color: #7f1d1d; margin-top: 0;">模擬可靠度資料</h3>
    <p>服從 <strong>Exponential</strong> 與 <strong>Weibull</strong> 分配的壽命資料，用於推導存活函數與危險函數的理論性質。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fff7ed; border-left: 5px solid #f97316; padding: 20px; border-radius: 8px;">
    <h3 style="color: #9a3412; margin-top: 0;">臨床存活資料</h3>
    <p><strong>43 筆存活時間</strong>含右設限，所有估計程序均需謹慎處理不完整觀測。</p>
  </div>
</div>

## 方法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Kaplan-Meier</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">無母數存活曲線 + Greenwood 變異數</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Exponential MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">封閉式 Fisher 資訊量</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Weibull Model</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">彈性遞增/遞減危險函數</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Log-Rank Test</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">雙樣本存活比較</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Nelson-Aalen</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">累積危險函數估計</p>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fca5a5; margin: 0;">處理設限資料的存活分析</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">針對不完整事件發生時間資料的無母數與參數化方法</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">O(1/n)</span><br><span style="color: #aaa;">MLE 變異數收斂速率</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">KM</span><br><span style="color: #aaa;">處理設限資料</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Weibull</span><br><span style="color: #aaa;">彈性危險函數形狀</span></div>
  </div>
</div>

- Kaplan-Meier 估計量適當處理右設限資料，提供一致的存活函數估計。
- Exponential MLE 的變異數以 **O(1/n)** 的速率收斂，推導出明確的封閉式表達式。
- Weibull 模型透過形狀參數捕捉遞增與遞減的危險函數模式。

---

## 期末專題：肝硬化存活建模

<div style="background: linear-gradient(135deg, #4a1942 0%, #7b2d5f 50%, #c2185b 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #f8bbd0; margin-top: 0; font-size: 1.3em;">分階段 Cox PH 模型與前向變數選擇</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    對 <strong>Mayo Clinic 原發性膽汁性肝硬化</strong>資料集進行全面的存活分析 — 依疾病分期（1&2、3、4）分層，並應用<strong>自行實作</strong>的 Cox Partial Likelihood 最佳化，搭配前向變數選擇與交叉驗證。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Cox PH Model</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">手動編寫 Partial Likelihood + L-BFGS-B 最佳化</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Forward Selection</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">基於 Deviance 的 3-fold CV</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Stage Stratification</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">依疾病嚴重程度分別建模</p>
  </div>
</div>

<div style="background: #1a1a2e; padding: 20px; border-radius: 10px; margin: 20px 0; text-align: center;">
  <p style="color: #f8bbd0; font-size: 1.3em; font-weight: bold; margin: 0;">關鍵發現</p>
  <p style="color: #ccc; margin-top: 8px; font-size: 1.05em;"><strong style="color: #f48fb1;">Bilirubin</strong> 在所有疾病分期的交叉驗證中被 <strong style="color: #7fecb3;">100%</strong> 選入 — 是肝硬化患者存活最一致的預測因子。</p>
</div>

<div style="margin-top: 25px;">
  <a href="/files/SA_HW1_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">下載 HW1 (PDF)</a>
  <a href="/files/SA_HW2_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">下載 HW2 (PDF)</a>
  <a href="/files/SA_Final_Survival.pdf" style="display: inline-block; background: #880e4f; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載期末專題 (PDF)</a>
</div>
