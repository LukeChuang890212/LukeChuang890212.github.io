---
title: "無母數曲線估計：密度估計、Kernel 迴歸、Splines 與局部方法"
layout: single
author_profile: true
permalink: /zh/portfolio/nonparametric/
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <strong>中文</strong> | <a href="/ja/portfolio/">日本語</a></div>

<div style="background: linear-gradient(135deg, #064e3b 0%, #047857 50%, #34d399 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a7f3d0; margin-top: 0; font-size: 1.6em;">沒有假設？沒問題。</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    當參數化模型過於僵化時，<strong>無母數方法</strong>讓資料自己說話。從 Kernel Density Estimation 到 <strong>GAMs</strong> — 在 <strong>9 份報告</strong>中探索完整的無假設曲線估計方法。
  </p>
</div>

## 方法 — 無母數估計的兩大支柱

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 300px; background: #ecfdf5; border-left: 5px solid #34d399; padding: 20px; border-radius: 8px;">
    <h3 style="color: #064e3b; margin-top: 0;">密度估計（報告 1、3-6）</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Histograms</strong><br><span style="color: #666;">Bin 起點效應</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Kernel DE</strong><br><span style="color: #666;">Gaussian、Epanechnikov</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Bandwidth</strong><br><span style="color: #666;">LSCV、Plug-in、ROT</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">多變量</strong><br><span style="color: #666;">乘積核函數</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">邊界校正</strong><br><span style="color: #666;">反射法</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">Parametric MLE</strong><br><span style="color: #666;">Beta 基準</span>
      </div>
    </div>
  </div>
  <div style="flex: 1; min-width: 300px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #14532d; margin-top: 0;">無母數迴歸（報告 7-10）</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Local Polynomial</strong><br><span style="color: #666;">線性與二次</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Nadaraya-Watson</strong><br><span style="color: #666;">Kernel 迴歸</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Smoothing Splines</strong><br><span style="color: #666;">GCV 參數選擇</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Penalized Splines</strong><br><span style="color: #666;">B-spline + 粗糙度懲罰</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">GAMs</strong><br><span style="color: #666;">可加性模型（mgcv）</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Mixed Model</strong><br><span style="color: #666;">Spline 與隨機效果的連結</span>
      </div>
    </div>
  </div>
</div>

## 主要結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #34d399; margin: 0;">Bandwidth > Kernel 選擇</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">核心洞察：平滑程度比平滑方式更重要</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">LSCV</span><br><span style="color: #aaa;">最佳 Bandwidth 選擇器</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Local Linear</span><br><span style="color: #aaa;">無邊界偏誤</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">9 份報告</span><br><span style="color: #aaa;">全面涵蓋</span></div>
  </div>
</div>

- 資料驅動的 Bandwidth 選擇方法一致優於固定 Bandwidth 的做法。
- Kernel 選擇（Gaussian vs. Epanechnikov）的影響遠小於 Bandwidth — **偏差-變異數取捨**才是關鍵。
- Local Linear 迴歸避免了 Nadaraya-Watson 估計量的邊界偏誤問題。
- 搭配 GCV 的 Smoothing Splines 提供優良擬合，同時防止過度擬合。
- **GAMs** 成功捕捉多個預測變數中的非線性關係。

<div style="margin-top: 25px;">
  <a href="/files/NCE_HW1_Density_Estimation.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/NCE_HW3_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/NCE_HW4_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/NCE_HW5_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/NCE_HW6_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/NCE_HW7_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW7</a>
  <a href="/files/NCE_HW8_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW8</a>
  <a href="/files/NCE_HW9_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW9</a>
  <a href="/files/NCE_HW10_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW10</a>
</div>
