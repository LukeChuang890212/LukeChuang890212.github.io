---
title: "ノンパラメトリック曲線推定：密度推定、カーネル回帰、スプライン、局所手法"
permalink: /ja/portfolio/nonparametric/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #064e3b 0%, #047857 50%, #34d399 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a7f3d0; margin-top: 0; font-size: 1.6em;">仮定なし？問題なし。</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    パラメトリックモデルが硬直的すぎる場合、<strong>ノンパラメトリック手法</strong>がデータに語らせます。カーネル密度推定から<strong>GAMs</strong>まで、<strong>9つのレポート</strong>にわたって仮定なしの曲線推定の全領域を探求。
  </p>
</div>

## 手法 ── ノンパラメトリック推定の二本柱

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 300px; background: #ecfdf5; border-left: 5px solid #34d399; padding: 20px; border-radius: 8px;">
    <h3 style="color: #064e3b; margin-top: 0;">密度推定（レポート1, 3-6）</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">ヒストグラム</strong><br><span style="color: #666;">ビン原点の効果</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">カーネル密度推定</strong><br><span style="color: #666;">Gaussian、Epanechnikov</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">バンド幅</strong><br><span style="color: #666;">LSCV、プラグイン、ROT</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">多変量</strong><br><span style="color: #666;">積カーネル</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">境界</strong><br><span style="color: #666;">反射法</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">パラメトリックMLE</strong><br><span style="color: #666;">Betaベンチマーク</span>
      </div>
    </div>
  </div>
  <div style="flex: 1; min-width: 300px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #14532d; margin-top: 0;">ノンパラメトリック回帰（レポート7-10）</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">局所多項式</strong><br><span style="color: #666;">線形 & 2次</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Nadaraya-Watson</strong><br><span style="color: #666;">カーネル回帰</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">平滑化スプライン</strong><br><span style="color: #666;">GCVパラメータ選択</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">ペナルティ付きスプライン</strong><br><span style="color: #666;">B-スプライン + 粗さ</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">GAMs</strong><br><span style="color: #666;">mgcvによる加法モデル</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">混合モデル</strong><br><span style="color: #666;">スプラインとランダム効果の接続</span>
      </div>
    </div>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #34d399; margin: 0;">バンド幅 > カーネル選択</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">根本的な洞察：どれだけ平滑化するかが、どのように平滑化するかより重要</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">LSCV</span><br><span style="color: #aaa;">最良のバンド幅選択法</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">局所線形</span><br><span style="color: #aaa;">境界バイアスなし</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">9レポート</span><br><span style="color: #aaa;">包括的なカバレッジ</span></div>
  </div>
</div>

- データ駆動型バンド幅選択は、固定バンド幅アプローチを一貫して上回った。
- カーネルの選択（Gaussian vs. Epanechnikov）はバンド幅よりもはるかに影響が小さい ── **バイアス-バリアンストレードオフ**が最重要。
- 局所線形回帰は、Nadaraya-Watson推定量を悩ませた境界バイアスを回避。
- GCVを用いた平滑化スプラインは、過学習を防ぎつつ優れた適合を提供。
- **GAMs**は複数の予測変数における非線形関係を同時に捉えることに成功。

<div style="margin-top: 25px;">
  <a href="/files/NCE_HW1_Density_Estimation.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW1</a>
  <a href="/files/NCE_HW3_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW3</a>
  <a href="/files/NCE_HW4_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW4</a>
  <a href="/files/NCE_HW5_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW5</a>
  <a href="/files/NCE_HW6_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW6</a>
  <a href="/files/NCE_HW7_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW7</a>
  <a href="/files/NCE_HW8_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW8</a>
  <a href="/files/NCE_HW9_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW9</a>
  <a href="/files/NCE_HW10_Nonparametric.pdf" style="display: inline-block; background: #047857; color: white; padding: 10px 16px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">HW10</a>
</div>
