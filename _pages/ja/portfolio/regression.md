---
title: "回帰モデリング：オゾン濃度予測と前立腺がんデータ分析"
permalink: /ja/portfolio/regression/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #0d4f4f 0%, #1a7a5a 50%, #2d8f4e 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #7fecb3; margin-top: 0; font-size: 1.6em;">観測データから予測モデルへ</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    <strong>環境科学</strong>と<strong>がん生物学</strong>という2つの異なる領域を、回帰分析の枠組みで横断的に分析。風速がオゾン濃度に及ぼす閾値効果の発見から、前立腺がん進行における最重要予測因子の特定まで。
  </p>
</div>

## データと前処理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f0faf5; border-left: 5px solid #2d8f4e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2d8f4e; margin-top: 0;">オゾンデータ</h3>
    <p><strong>111日分</strong>のオゾン、放射量、気温、風速の日次測定値。欠損値なし。正規性の仮定を満たすため Box-Cox 変換（5乗根）を適用。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0f5fa; border-left: 5px solid #3a7bd5; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3a7bd5; margin-top: 0;">前立腺がんデータ</h3>
    <p><strong>97症例</strong>、臨床予測変数8個、応答変数は log-PSA。70/27の訓練・検証分割。Dunn の多重比較検定に基づき Gleason スコア7〜9を「高」に統合。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- **オゾン**：放射量・気温との間に強い正の関連、風速との間に負の関連を確認。条件付き散布図から**風速の閾値効果**が浮かび上がった。
- **前立腺がん**：Kendall の順位相関により lcavol、lweight、lcp、pgg45 が lpsa と有意に関連。Kruskal-Wallis 検定および Wilcoxon 検定で離散変数の有意な効果を確認。

## 手法

| 手法 | 目的 |
|--------|---------|
| 線形回帰 | 多項式項・交互作用項の導入 |
| AIC/BIC ステップワイズ選択 | 簡潔なモデルの探索 |
| モデル診断 | 残差分析、VIF、てこ比、影響度 |
| Box-Cox 変換 | 応答変数の正規性確保 |
| ノンパラメトリック検定 | 離散的予測変数の効果評価 |
| 予測区間 | 検証データでのモデル評価 |

## 主な結果

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #2d8f4e; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #2d8f4e; margin: 5px 0;">RMSE ≈ 19</p>
    <p style="color: #666;">オゾン予測――オゾンの変動範囲に対して十分に小さく、高い予測精度を示す</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #3a7bd5; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #3a7bd5; margin: 5px 0;">lcavol + svi</p>
    <p style="color: #666;">前立腺がん進行（log-PSA）における最重要予測因子</p>
  </div>
</div>

- **風速の閾値効果**を発見――閾値以下では風速が強い負の影響を持つが、閾値を超えるとその効果はほぼ消失する。
- 最終的な前立腺がんモデルは、検証データにおいて良好に較正された予測区間を達成した。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW1_Regression.pdf" style="display: inline-block; background: #2d8f4e; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
