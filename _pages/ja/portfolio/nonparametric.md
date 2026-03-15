---
title: "ノンパラメトリック曲線推定：密度推定・カーネル回帰・スプライン・局所的手法"
permalink: /ja/portfolio/nonparametric/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #064e3b 0%, #047857 50%, #34d399 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a7f3d0; margin-top: 0; font-size: 1.6em;">仮定を置かずに、データに語らせる</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    パラメトリックモデルでは捉えきれない構造がある。カーネル密度推定から<strong>GAMs</strong>まで、<strong>全9回のレポート</strong>を通じて、分布の仮定に依存しない曲線推定の全体像を体系的に探る。
  </p>
</div>

## 手法 ── ノンパラメトリック推定の二本柱

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 300px; background: #ecfdf5; border-left: 5px solid #34d399; padding: 20px; border-radius: 8px;">
    <h3 style="color: #064e3b; margin-top: 0;">密度推定（レポート 1, 3-6）</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">ヒストグラム</strong><br><span style="color: #666;">ビン原点の影響</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">カーネル密度推定</strong><br><span style="color: #666;">Gaussian、Epanechnikov</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">バンド幅選択</strong><br><span style="color: #666;">LSCV、Plug-in、ROT</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">多変量推定</strong><br><span style="color: #666;">積カーネル</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">境界補正</strong><br><span style="color: #666;">反射法</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #047857;">パラメトリック MLE</strong><br><span style="color: #666;">Beta 分布によるベンチマーク</span>
      </div>
    </div>
  </div>
  <div style="flex: 1; min-width: 300px; background: #f0fdf4; border-left: 5px solid #22c55e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #14532d; margin-top: 0;">ノンパラメトリック回帰（レポート 7-10）</h3>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 10px;">
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">局所多項式回帰</strong><br><span style="color: #666;">線形・2次</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">Nadaraya-Watson</strong><br><span style="color: #666;">カーネル回帰</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">平滑化スプライン</strong><br><span style="color: #666;">GCV によるパラメータ選択</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">ペナルティ付きスプライン</strong><br><span style="color: #666;">B-spline ＋ 粗さペナルティ</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">GAMs</strong><br><span style="color: #666;">mgcv による加法モデル</span>
      </div>
      <div style="background: white; padding: 8px; border-radius: 6px; text-align: center; font-size: 0.9em;">
        <strong style="color: #15803d;">混合モデル</strong><br><span style="color: #666;">スプラインとランダム効果の対応</span>
      </div>
    </div>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #34d399; margin: 0;">バンド幅 ＞ カーネルの選択</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">核心的な知見：「どれだけ平滑化するか」が「どう平滑化するか」より重要</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">LSCV</span><br><span style="color: #aaa;">最良のバンド幅選択法</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">局所線形</span><br><span style="color: #aaa;">境界バイアスなし</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">全9レポート</span><br><span style="color: #aaa;">体系的な網羅</span></div>
  </div>
</div>

- データ駆動型のバンド幅選択は、固定バンド幅の手法を一貫して上回った。
- カーネルの種類（Gaussian vs. Epanechnikov）はバンド幅ほど結果に影響しない――**バイアス-バリアンスのトレードオフ**こそが本質的に重要である。
- 局所線形回帰は、Nadaraya-Watson 推定量に固有の境界バイアスを解消した。
- GCV による平滑化スプラインは、過学習を防ぎつつ優れた当てはまりを実現。
- **GAMs** は複数の予測変数における非線形関係を同時にとらえることに成功した。

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
