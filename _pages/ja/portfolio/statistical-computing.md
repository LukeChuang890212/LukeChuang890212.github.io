---
title: "統計計算：シミュレーション、Monte Carlo、MCMC、仮説検定、最適化、EMアルゴリズム、ガウス過程"
permalink: /ja/portfolio/statistical-computing/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #3b0764 0%, #7c3aed 50%, #a78bfa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ddd6fe; margin-top: 0; font-size: 1.6em;">統計のエンジンルーム ── ゼロから構築</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    現代統計の計算基盤を実装：<strong>Monte Carlo</strong>、<strong>MCMC</strong>、<strong>EMアルゴリズム</strong>、<strong>Newton-Raphson</strong>、<strong>ガウス過程</strong>、<strong>ベイズ最適化</strong> ── すべてを7つのレポートにわたってゼロからコーディング。
  </p>
</div>

## 手法 ── 統計計算のロードマップ

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">シミュレーション & Monte Carlo</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">逆CDF法、棄却法、対照変量法、重点サンプリング、制御変量法</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">MCMCサンプリング</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Metropolis-Hastings、Gibbsサンプラー、収束診断、トレースプロット、ESS</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Bootstrap & 検定</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Jarque-Bera正規性検定、検出力分析、bootstrap、順列検定</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート3</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Newton-Raphson MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">解析的勾配 & Hessian、直線探索、不等分散モデル</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート4</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">EMアルゴリズム</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ガウス混合モデル、E-step/M-step、単調対数尤度収束</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート5</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">GP & ベイズ最適化</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Matern共分散MLE、クリギング、Expected Improvement獲得関数</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート6 & 中間試験</span>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #a78bfa; margin: 0;">すべてのアルゴリズムをゼロから実装</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">すべての手法をコーディング、検証、分析 ── ライブラリを呼び出すだけではない</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">2次</span><br><span style="color: #aaa;">Newton-Raphsonの収束</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">EM</span><br><span style="color: #aaa;">真のパラメータを復元</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">GP</span><br><span style="color: #aaa;">校正された不確実性</span></div>
  </div>
</div>

- 適切な提案分布を用いた重点サンプリングにより、粗Monte Carloに対して**大幅な分散削減**を達成。
- Jarque-Bera検定は裾の重い対立仮説に対して高い検出力を示すが、対称非正規分布に対しては低い検出力。
- EMアルゴリズムは単調対数尤度収束で真の混合パラメータを復元。
- Newton-Raphsonは**2次収束**を達成し、Rの`optim`出力と一致。
- Matern共分散を用いたGP回帰は、校正された不確実性バンドとともに正確な空間予測を提供。

<div style="margin-top: 25px;">
  <a href="/files/SC_HW1_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/SC_HW2_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/SC_HW3_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/SC_HW4_Optimization.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/SC_HW5_EM_Algorithm.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/SC_HW6_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/SC_Midterm_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">中間試験</a>
</div>
