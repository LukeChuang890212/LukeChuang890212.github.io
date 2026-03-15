---
title: "SVM と教師なし学習：高次元画像分類"
permalink: /ja/portfolio/svm-unsupervised/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #4c1d95 0%, #6d28d9 50%, #8b5cf6 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #c4b5fd; margin-top: 0; font-size: 1.6em;">10,000次元空間で欠陥を見つけ出す</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    生画像を大規模な特徴ベクトルに展開し、<strong>PCA</strong> で次元を圧縮、<strong>t-SNE</strong> で可視化、<strong>SVM</strong> で分類する――鋳造品の欠陥検出に向けた、ピクセルから予測までの一貫パイプライン。
  </p>
</div>

## データと前処理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f5f3ff; border-left: 5px solid #8b5cf6; padding: 20px; border-radius: 8px;">
    <h3 style="color: #4c1d95; margin-top: 0;">大規模画像分類</h3>
    <p>高次元データセットを単位分散に標準化。次元削減のため <strong>PCA</strong> を適用し、標準化済みデータ行列に対して固有値分解を実施。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fdf4ff; border-left: 5px solid #a855f7; padding: 20px; border-radius: 8px;">
    <h3 style="color: #701a75; margin-top: 0;">鋳造品欠陥検出</h3>
    <p><strong>100x100 ピクセル</strong>のグレースケール鋳造品画像。各画像を10,000次元の特徴ベクトルに展開し、欠陥あり・欠陥なしの二値分類を行う。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- **スクリープロット**と累積寄与率プロットにより、適切な主成分数を決定。
- **t-SNE 埋め込み**（perplexity 3 および 7）が高次元空間に潜む自然なクラスター構造を可視化。
- 画像データの**ヒートマップ**が、欠陥品と良品を区別する空間的パターンを示した。

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">PCA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">次元削減の前処理</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">SVM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV でカーネル・コストを調整</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ベンチマーク分類器</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">主成分ロジスティック回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">BIC による変数選択</p>
  </div>
  <div style="background: #f5f3ff; border: 2px solid #8b5cf6; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #4c1d95; font-size: 1.1em;">t-SNE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">非線形可視化</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #c4b5fd; margin: 0;">ピクセルから予測へ</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">完全パイプライン：生画像 → PCA → SVM → 欠陥分類</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">10,000→k</span><br><span style="color: #aaa;">次元削減</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">SVM</span><br><span style="color: #aaa;">最良の分類器</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">t-SNE</span><br><span style="color: #aaa;">明瞭なクラスター分離</span></div>
  </div>
</div>

- PCA は識別力を維持しつつ、効果的に次元を削減した。
- チューニング済みカーネルを用いた **SVM** が優れた欠陥検出性能を達成。
- t-SNE により明瞭に分離されたクラスターが確認され、自動欠陥検出の実現可能性が裏付けられた。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW5_SVM_Unsupervised.pdf" style="display: inline-block; background: #6d28d9; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
