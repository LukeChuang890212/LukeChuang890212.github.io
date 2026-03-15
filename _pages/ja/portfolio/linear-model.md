---
title: "線形モデル：回帰理論、診断、重み付き最小二乗法、時系列モデリング"
permalink: /ja/portfolio/linear-model/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1e3a5f 0%, #2563eb 50%, #60a5fa 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #bfdbfe; margin-top: 0; font-size: 1.6em;">線形モデルの総合ツールキット——7本のレポートで網羅</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    OLSの基礎から<strong>WLS</strong>、<strong>GLS + AR(1)</strong>、<strong>B-spline</strong>、<strong>変化点モデル</strong>まで。ギャンブル行動、製造プロセス、賃金、身長、CEO報酬、150年分の気温データに線形モデル理論を包括的に適用した。
  </p>
</div>

## データと前処理

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">10代のギャンブル</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">47件の観測値、性別・社会的地位・収入・言語能力</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">化学プロセス</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">蒸気圧、速度、温度の交互作用</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">米国賃金</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">教育 + 経験年数、ネストF検定</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">廃棄物データ</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">信頼楕円、同時推論</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Galton身長データ</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">グループサイズ不均等に対するWLS</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">CEO報酬</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">外れ値処理、分散安定化変換</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">Ann Arborの気温</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">約150年間、AR(1)、スプライン、変化点</p>
  </div>
  <div style="background: #eff6ff; border-left: 4px solid #2563eb; padding: 12px; border-radius: 6px;">
    <strong style="color: #1e3a5f;">インド乳児死亡率</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">性別 + 都市部/農村部ダミー</p>
  </div>
</div>

## 分析手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">OLS + F検定</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">ネストモデルの比較</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">網羅的な診断</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">てこ比、Cook's D、DFBETAS</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">WLS</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">グループデータへの重み付け</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GLS + AR(1)</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">時系列における誤差の自己相関</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">スプライン回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">3次B-spline、6基底関数</p>
  </div>
  <div style="background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">変化点モデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">1930年における構造変化</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #60a5fa; margin: 0;">150年にわたる温暖化——統計的に確認</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">1930年以降の気温上昇トレンドはAR(1)補正後も有意</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">rho = 0.23</span><br><span style="color: #aaa;">AR(1)自己相関</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">スプライン</span><br><span style="color: #aaa;">最良RMSEのモデル</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">7レポート</span><br><span style="color: #aaa;">8データセットを分析</span></div>
  </div>
</div>

- 回帰診断により、てこ点、外れ値、不均一分散が検出され、モデルの改善につながった。
- WLSにより、グループ化された身長データの精度の不均一性を適切に考慮した。
- **1930年以降の温暖化トレンド**は AR(1) 補正（rho = 0.23）を行った後でも有意に残った。
- 3次B-spline回帰が最良のRMSEを達成し、気温の非線形な変動パターンを捉えた。

<div style="margin-top: 25px;">
  <a href="/files/LM_HW1_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/LM_HW2_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW2</a>
  <a href="/files/LM_HW3_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/LM_HW4_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/LM_HW5_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/LM_HW6_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/LM_HW7_Linear_Model.pdf" style="display: inline-block; background: #2563eb; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW7</a>
</div>
