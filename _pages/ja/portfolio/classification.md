---
title: "分類手法の比較：乳がん診断への適用"
permalink: /ja/portfolio/classification/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #4a1942 0%, #893168 50%, #c94b8c 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ffb6d9; margin-top: 0; font-size: 1.6em;">アルゴリズムは良性と悪性を見分けられるか？</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Wisconsin Breast Cancer データセットを用いた<strong>6つの分類手法</strong>の正面対決。ロジスティック回帰から KNN まで、9つの細胞特徴量を持つ683件の腫瘍サンプルで各分類器の性能を徹底比較した。
  </p>
</div>

## データと前処理

**Wisconsin Breast Cancer Data**（UCI / R `mlbench`）：699件の観測値。9つの順序尺度予測変数（細胞の形態学的特徴）と1つの二値目的変数（良性 vs. 悪性）。欠損値を含む16件を除外し、密度ベースの検証を行ったうえで 90/10 の訓練・テスト分割を適用した。

## 探索的データ分析（EDA）

- 全予測変数で強い右裾分布が見られ、二峰性のパターンが良性・悪性の2クラス構造を反映していた。
- ペアワイズ散布図により、良性・悪性で明確な分布の違いが確認され、全予測変数が識別力を持つことが示された。
- 予測変数間に高い相関があり、モデリングにおいて多重共線性への配慮が必要であった。

## 分析手法——6つの分類器を比較

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">ロジスティック回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ステップワイズ変数選択 + 交互作用</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">LDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">線形判別分析</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">QDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">クラス別の分散共分散行列</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">Naive Bayes</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ガウシアン + ノンパラメトリックカーネル</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">KNN</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">交差検証で最適化した k</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">ROC/AUC</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">統一的な比較フレームワーク</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2.5em; font-weight: bold; color: #ffb6d9; margin: 0;">AUC > 0.98</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">全分類器で達成——データの高い分離可能性を確認</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">95%超</span><br><span style="color: #aaa;">テスト正解率</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3</span><br><span style="color: #aaa;">主要予測因子を特定</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">683</span><br><span style="color: #aaa;">腫瘍サンプル</span></div>
  </div>
</div>

- **Cell.size**、**Bare.nuclei**、**Bl.cromatin** が全手法を通じて最も影響力の大きい予測因子として特定された。
- QDA とノンパラメトリック Naive Bayes は、分布の仮定を緩和することでわずかな性能向上を達成した。
- KNN は最適な k の選択により競争力のある性能を示したが、解釈可能性の面では劣る結果となった。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW2_Classification.pdf" style="display: inline-block; background: #893168; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
