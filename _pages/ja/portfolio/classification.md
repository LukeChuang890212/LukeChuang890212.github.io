---
title: "分類手法：乳がん診断"
permalink: /ja/portfolio/classification/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <a href="/zh/portfolio/">中文</a> | <strong>日本語</strong></div>

<div style="background: linear-gradient(135deg, #4a1942 0%, #893168 50%, #c94b8c 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ffb6d9; margin-top: 0; font-size: 1.6em;">アルゴリズムは良性と悪性を区別できるか？</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Wisconsin Breast Cancer データセットにおける <strong>6つの分類手法</strong>の正面対決。ロジスティック回帰から KNN まで、9つの細胞特徴量を持つ 683 腫瘍サンプルで全分類器の限界を検証した。
  </p>
</div>

## データソースとクリーニング

**Wisconsin Breast Cancer Data**（UCI / R `mlbench`）：699 観測値、細胞特徴量を記述する 9 つの順序尺度予測変数と 1 つの二値目的変数（良性 vs. 悪性）。欠損値のある 16 観測値を除外。密度ベースの検証による 90/10 の訓練・テスト分割を適用。

## 探索的データ分析（EDA）

- 全予測変数において強い右歪み分布、二峰性パターンが2クラス構造を反映。
- ペアワイズ散布図で良性・悪性の明確な分布差を確認——全予測変数が識別力を持つ。
- 予測変数間の高い相関が慎重なモデリングの必要性を示唆。

## 手法——6分類器の対決

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">ロジスティック回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ステップワイズ選択 + 交互作用</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">LDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">線形判別分析</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">QDA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">不等分散共分散行列</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">Naive Bayes</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ガウシアン + ノンパラメトリックカーネル</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">KNN</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV最適化 k</p>
  </div>
  <div style="background: #fdf2f8; border: 2px solid #c94b8c; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #893168; font-size: 1.1em;">ROC/AUC</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">総合比較フレームワーク</p>
  </div>
</div>

## 主要な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2.5em; font-weight: bold; color: #ffb6d9; margin: 0;">AUC > 0.98</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">全分類器——データの強い分離可能性を確認</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">95%+</span><br><span style="color: #aaa;">テスト精度</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3</span><br><span style="color: #aaa;">上位予測因子を特定</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">683</span><br><span style="color: #aaa;">腫瘍サンプル</span></div>
  </div>
</div>

- **Cell.size**、**Bare.nuclei**、**Bl.cromatin** が全手法で最も影響力のある予測因子として特定された。
- QDA とノンパラメトリック Naive Bayes は分布の仮定を緩和することでわずかな改善を示した。
- KNN は最適化された k により競合的な性能を達成したが、解釈可能性は低下した。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW2_Classification.pdf" style="display: inline-block; background: #893168; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
