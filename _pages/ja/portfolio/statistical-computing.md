---
title: "統計計算：シミュレーション・Monte Carlo・MCMC・仮説検定・最適化・EMアルゴリズム・ガウス過程"
permalink: /ja/portfolio/statistical-computing/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #3b0764 0%, #7c3aed 50%, #a78bfa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ddd6fe; margin-top: 0; font-size: 1.6em;">統計の心臓部をゼロから組み上げる</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    現代統計学を支える計算手法――<strong>Monte Carlo</strong>、<strong>MCMC</strong>、<strong>EMアルゴリズム</strong>、<strong>Newton-Raphson</strong>、<strong>ガウス過程</strong>、<strong>ベイズ最適化</strong>――を全7回のレポートですべてスクラッチ実装。
  </p>
</div>

## 手法 ── 統計計算のロードマップ

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">シミュレーション & Monte Carlo</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">逆CDF法、棄却法、対照変量法、重点サンプリング、制御変量法</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート 1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">MCMC サンプリング</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Metropolis-Hastings、Gibbs サンプラー、収束診断、トレースプロット、ESS</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート 1-2</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Bootstrap & 検定</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Jarque-Bera 正規性検定、検出力分析、Bootstrap、順列検定</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート 3</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">Newton-Raphson MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">解析的勾配・Hessian の導出、直線探索、不等分散モデル</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート 4</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">EM アルゴリズム</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ガウス混合モデル、E-step/M-step、対数尤度の単調収束</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート 5</span>
  </div>
  <div style="background: #faf5ff; border: 2px solid #7c3aed; padding: 18px; border-radius: 10px;">
    <strong style="color: #3b0764; font-size: 1.1em;">GP & ベイズ最適化</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Matern 共分散の MLE、クリギング、Expected Improvement 獲得関数</p>
    <span style="font-size: 0.8em; color: #7c3aed; font-weight: bold;">レポート 6 & 中間試験</span>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #a78bfa; margin: 0;">全アルゴリズムをスクラッチ実装</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">ライブラリを呼ぶだけではなく、すべて自分の手でコーディング・検証・分析</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">2次収束</span><br><span style="color: #aaa;">Newton-Raphson の収束次数</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">EM</span><br><span style="color: #aaa;">真のパラメータを復元</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">GP</span><br><span style="color: #aaa;">較正された不確実性</span></div>
  </div>
</div>

- 適切な提案分布を用いた重点サンプリングにより、素朴な Monte Carlo と比べて**大幅な分散削減**を達成。
- Jarque-Bera 検定は裾の重い対立仮説に対して高い検出力を示す一方、対称的な非正規分布に対しては検出力が低い。
- EM アルゴリズムは対数尤度の単調収束のもとで真の混合パラメータを復元。
- Newton-Raphson は**2次収束**を達成し、Rの `optim` 関数の出力と一致することを確認。
- Matern 共分散を用いた GP 回帰は、較正された不確実性バンドとともに正確な空間予測を実現。

<div style="margin-top: 25px;">
  <a href="/files/SC_HW1_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/SC_HW2_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/SC_HW3_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/SC_HW4_Optimization.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/SC_HW5_EM_Algorithm.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/SC_HW6_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/SC_Midterm_Computing.pdf" style="display: inline-block; background: #7c3aed; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">中間試験</a>
</div>
