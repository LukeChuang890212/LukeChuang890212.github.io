---
title: "モデル選択と正則化：化学製造プロセスにおける収率予測"
permalink: /ja/portfolio/model-selection/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #0a2463 0%, #1e3a8a 50%, #3b82f6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #93c5fd; margin-top: 0; font-size: 1.6em;">57個の予測変数から、本当に効くものを見極める</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    高次元の化学製造データに対し、Forward/Backward Selection から Lasso、Ridge まで<strong>6種類の変数選択・正則化手法</strong>を正面から比較。製品収率を安定的に左右する予測変数を特定する。
  </p>
</div>

## データと前処理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #3b82f6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #1e3a8a; margin-top: 0;">化学製造データ</h3>
    <p><strong>177サンプル</strong>、57個の予測変数（生物学的変数12個＋プロセス測定値45個）、応答変数は製品収率。欠損値を除去し、予測変数を標準化した上で、90/10の訓練・テスト分割を適用。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #15803d; margin-top: 0;">Bootstrap によるロバスト性検証</h3>
    <p>汚染データを用いて、標準推定量と<strong>MADベースのロバスト推定量</strong>による母標準偏差の推定精度をノンパラメトリック Bootstrap（B = 10,000）で比較。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- 予測変数間のスケール差が大きく、公平な比較には標準化が不可欠。
- 多くの予測変数間に高い相関が見られ、次元削減の有効性を示唆。
- Yield と強い周辺的関連を持つ予測変数はごくわずか――**スパース性の原理**と合致する結果。
- P12、P28、P40〜P43に歪んだ分布、P25〜P31に外れ値を確認。

## 手法 ── 6つの選択手法の比較

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">1</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Forward Selection</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5変数を選択</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">2</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Backward Selection</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3変数を選択</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">3</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Best Subset</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5変数を選択</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">4</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">PCR</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">6主成分を保持</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">5</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Lasso</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">7変数（精緻化後）</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">6</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Ridge</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3変数（上位係数）</p>
  </div>
</div>

すべての手法を**5分割交差検証**で統一的に評価。

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #93c5fd; margin: 0;">Lasso が CV 安定性で優勝</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">改良版 Lasso（モデル5）が最小かつ最も安定したテスト MSE を達成</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">P33 & P34</span><br><span style="color: #aaa;">手法横断で一貫した上位予測変数</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">57 → 3–7</span><br><span style="color: #aaa;">次元削減</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">B=10,000</span><br><span style="color: #aaa;">Bootstrap 反復回数</span></div>
  </div>
</div>

- **P33** と **P34** が複数の手法で一貫して最重要予測変数として選出され、いずれも Yield と正の関連を示した。
- PCR がテストセット RMSE で最小値を記録した一方、Lasso は交差検証における安定性で最も優れた。
- 外れ値が存在する状況では、ロバスト MAD 推定量が標準推定量に比べて分散を大幅に抑えた。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW3_Resampling_Regularization.pdf" style="display: inline-block; background: #1e3a8a; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
