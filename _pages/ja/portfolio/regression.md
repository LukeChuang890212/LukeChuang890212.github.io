---
title: "回帰モデリング：オゾン予測と前立腺がん分析"
permalink: /ja/portfolio/regression/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <a href="/zh/portfolio/">中文</a> | <strong>日本語</strong></div>

<div style="background: linear-gradient(135deg, #0d4f4f 0%, #1a7a5a 50%, #2d8f4e 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #7fecb3; margin-top: 0; font-size: 1.6em;">生データから予測モデルへ</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    <strong>環境科学</strong>と<strong>がん生物学</strong>という2つの異なる領域を、回帰理論のレンズを通して分析。風速の閾値効果がオゾン濃度に与える影響の発見から、前立腺がん進行の最も重要な予測因子の特定まで。
  </p>
</div>

## データソースとクリーニング

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f0faf5; border-left: 5px solid #2d8f4e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2d8f4e; margin-top: 0;">オゾンデータ</h3>
    <p><strong>111日分の測定値</strong>：オゾン、放射量、気温、風速。欠損値なし。正規性の仮定を満たすために Box-Cox 変換（5乗根）を適用。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0f5fa; border-left: 5px solid #3a7bd5; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3a7bd5; margin-top: 0;">前立腺がんデータ</h3>
    <p><strong>97 観測値</strong>、8つの臨床予測変数と log-PSA を応答変数とする。70/27 の訓練・検証分割。Dunn の多重比較検定に基づき、Gleason スコア 7〜9 を「高」レベルに統合。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- **オゾン**：オゾンと放射量・気温の間に強い正の関連性、風速との間に負の関連性。条件付き散布図により**風速の閾値効果**が明らかになった。
- **前立腺がん**：Kendall の順位相関により lcavol、lweight、lcp、pgg45 が lpsa と有意に関連。Kruskal-Wallis 検定と Wilcoxon 検定により離散変数の有意な効果を確認。

## 手法

| 手法 | 目的 |
|--------|---------|
| 線形回帰 | 多項式項と交互作用効果 |
| AIC/BIC ステップワイズ選択 | 簡潔なモデルの同定 |
| モデル診断 | 残差、VIF、てこ比、影響度 |
| Box-Cox 変換 | 応答変数の正規性 |
| ノンパラメトリック検定 | 離散予測変数の評価 |
| 予測区間 | 検証データでの評価 |

## 主要な結果

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #2d8f4e; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #2d8f4e; margin: 5px 0;">RMSE ≈ 19</p>
    <p style="color: #666;">オゾン予測——オゾンの範囲に対して小さく、強い予測性能を示す</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #3a7bd5; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #3a7bd5; margin: 5px 0;">lcavol + svi</p>
    <p style="color: #666;">前立腺がん進行（log-PSA）の最も重要な予測因子</p>
  </div>
</div>

- **風速の閾値効果**が発見された——閾値以下では風が強い負の影響を持つが、閾値以上ではその効果は無視できる程度であった。
- 最終的な前立腺がんモデルは、検証データにおいて良好に較正された予測区間を達成した。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW1_Regression.pdf" style="display: inline-block; background: #2d8f4e; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
