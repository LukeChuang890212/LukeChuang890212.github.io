---
title: "統計計算：模擬、Monte Carlo、MCMC、假設檢定、最佳化、EM 演算法與 Gaussian Process"
layout: single
author_profile: true
permalink: /zh/portfolio/statistical-computing/
---


<div style="background: linear-gradient(135deg, #3b0764 0%, #7c3aed 50%, #a78bfa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ddd6fe; margin-top: 0; font-size: 1.6em;">統計學的引擎室 — 從零開始打造</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    實作現代統計的計算核心：<strong>Monte Carlo</strong>、<strong>MCMC</strong>、<strong>EM Algorithm</strong>、<strong>Newton-Raphson</strong>、<strong>Gaussian Process</strong> 與 <strong>Bayesian Optimization</strong> — 所有演算法皆從頭編寫，涵蓋 7 份報告。
  </p>
</div>

## 方法 — 統計計算路線圖

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">模擬與 Monte Carlo</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Inverse CDF、Acceptance-Rejection、Antithetic Variates、Importance Sampling、Control Variates</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">報告 1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">MCMC 抽樣</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Metropolis-Hastings、Gibbs Sampler、收斂診斷、Trace Plots、ESS</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">報告 1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Bootstrap 與檢定</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Jarque-Bera 常態性檢定、檢定力分析、Bootstrap、排列檢定</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">報告 3</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Newton-Raphson MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">解析梯度與 Hessian、Line Search、異質變異數模型</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">報告 4</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">EM Algorithm</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Gaussian Mixture Models、E-step/M-step、單調 Log-Likelihood 收斂</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">報告 5</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">GP 與 Bayesian Optimization</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Matern 協方差 MLE、Kriging、Expected Improvement 取得函數</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">報告 6 與期中</span>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #a78bfa; margin: 0;">所有演算法從零實作</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">每個方法皆經編寫、驗證與分析 — 而非僅呼叫函式庫</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Quadratic</span><br><span style="color: #aaa;">Newton-Raphson 收斂</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">EM</span><br><span style="color: #aaa;">還原真實參數</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">GP</span><br><span style="color: #aaa;">校準的不確定性</span></div>
  </div>
</div>

- 選擇良好提議分佈的 Importance Sampling 相較粗略 Monte Carlo 達到了**顯著的變異數縮減**。
- Jarque-Bera 檢定對厚尾替代假設有高檢定力，但對對稱非常態分佈的檢定力低。
- EM Algorithm 成功還原真實混合模型參數，並具有單調 Log-Likelihood 收斂性。
- Newton-Raphson 達到**二次收斂**，結果與 R 的 `optim` 輸出一致。
- 使用 Matern 協方差的 GP 迴歸提供準確的空間預測與校準的不確定性區間。

<div style="margin-top: 25px;">
  <a href="/files/SC_HW1_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/SC_HW2_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/SC_HW3_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/SC_HW4_Optimization.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/SC_HW5_EM_Algorithm.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/SC_HW6_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/SC_Midterm_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">期中</a>
</div>
