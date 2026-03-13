---
title: "モデル選択と正則化：化学製造プロセスの収率予測"
permalink: /ja/portfolio/model-selection/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #0a2463 0%, #1e3a8a 50%, #3b82f6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #93c5fd; margin-top: 0; font-size: 1.6em;">6手法、57予測変数。本当に重要なのはどれか？</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    高次元化学製造データセットにおける <strong>6つの変数選択・正則化手法</strong>の体系的な正面比較——前方/後方選択から Lasso、Ridge まで——製品収率を一貫して左右する予測変数を明らかにする。
  </p>
</div>

## データソースとクリーニング

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #3b82f6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #1e3a8a; margin-top: 0;">化学製造データ</h3>
    <p><strong>177 サンプル</strong>、57 予測変数（12 生物学的 + 45 プロセス測定値）、応答変数は製品収率。欠損値を除外し、予測変数を標準化。90/10 の訓練・テスト分割。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #15803d; margin-top: 0;">Bootstrap ロバスト性研究</h3>
    <p>汚染データセットにおいて、標準推定量と <strong>MADベースのロバスト推定量</strong>による母標準偏差の推定をノンパラメトリック Bootstrap（B = 10,000）で比較。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- 予測変数間の大きなスケール差により、公平な比較のための標準化が必要。
- 多くの予測変数間の高い相関が次元削減アプローチを支持。
- Yield との強い周辺関連性を示す予測変数はわずか——**スパース性の原理**と整合。
- P12、P28、P40〜P43 に歪んだ分布；P25〜P31 に外れ値を検出。

## 手法——6つの選択手順の比較

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">1</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">前方選択</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5 予測変数を選択</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">2</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">後方選択</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 予測変数を選択</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">3</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Best Subset</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5 予測変数を選択</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">4</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">PCR</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">6 主成分を保持</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">5</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Lasso</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">7 予測変数（精緻化後）</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #3b82f6; padding: 15px; border-radius: 10px; text-align: center;">
    <span style="font-size: 1.5em; font-weight: bold; color: #1e3a8a;">6</span>
    <p style="margin: 5px 0 0; font-weight: bold; color: #1e3a8a;">Ridge</p>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3 予測変数（上位係数）</p>
  </div>
</div>

全手法を **5分割交差検証**により公平に評価。

## 主要な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #93c5fd; margin: 0;">Lasso が CV 安定性で勝利</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">改良 Lasso（モデル5）が最小かつ最も安定したテスト MSE を達成</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">P33 & P34</span><br><span style="color: #aaa;">一貫した上位予測因子</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">57 → 3–7</span><br><span style="color: #aaa;">次元削減</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">B=10,000</span><br><span style="color: #aaa;">Bootstrap 反復回数</span></div>
  </div>
</div>

- **P33** と **P34** が複数の手法で一貫して最も重要な予測因子として特定され、両者とも Yield と正の関連性を示した。
- PCR が最小のテストセット RMSE を達成した一方、Lasso は最良の CV 安定性を提供した。
- ロバスト MAD 推定量は外れ値存在下で標準推定量より著しく低い分散を示した。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW3_Resampling_Regularization.pdf" style="display: inline-block; background: #1e3a8a; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
