---
title: "カテゴリカルデータ分析：GLMs、ロジスティック回帰、ポアソンモデル、対応分析"
permalink: /ja/portfolio/categorical/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <a href="/zh/portfolio/">中文</a> | <strong>日本語</strong></div>

<div style="background: linear-gradient(135deg, #134e4a 0%, #0d9488 50%, #2dd4bf 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #99f6e4; margin-top: 0; font-size: 1.6em;">カウント、カテゴリ、分割表</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    <strong>カテゴリカルデータ手法</strong>の包括的な探求。疾患リスクのためのロジスティック回帰、カウントデータのためのポアソンモデル、分割表のための対応分析、社会的流動性パターンのための対称性検定。<strong>9つの実データセット</strong>を5つのレポートで分析。
  </p>
</div>

## データソースとクリーニング

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 20px 0;">
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">Motor Trend自動車</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">32台の自動車、mpg + 10予測変数</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">心臓カテーテル検査</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">RCSを用いたロジスティック回帰</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">綿肺症（職業性）</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">64の共変量クラス、二値アウトカム</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">アフリカ軍事クーデター</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">カウントデータ、政治的予測変数</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">サルモネラ用量反応</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">多項式ポアソン + 過分散</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">デンマーク婚姻状況</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">多項式コントラストポアソン</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">食道がん</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">症例対照研究、飲酒 + 喫煙</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">スイス教育</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">対応分析（chi2 = 5260）</p>
  </div>
  <div style="background: #f0fdfa; border-left: 4px solid #0d9488; padding: 12px; border-radius: 6px;">
    <strong style="color: #134e4a;">英国社会的流動性</strong>
    <p style="font-size: 0.85em; margin: 5px 0 0; color: #666;">6x6 対称性/準対称性</p>
  </div>
</div>

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">線形回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">完全診断：てこ比、Cook's D、VIF</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">ロジスティック回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">RCS、ROC、キャリブレーション、交互作用</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">ポアソン回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">過分散、準ポアソン</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">対応分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">Pearson残差のSVD</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">対数線形モデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">分割表モデリング</p>
  </div>
  <div style="background: #f0fdfa; border: 2px solid #0d9488; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #134e4a; font-size: 1.05em;">対称性検定</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">社会的流動性パターン</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #2dd4bf; margin: 0;">9データセット。6つの手法ファミリー。</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">包括的なカテゴリカルデータ分析ツールキット</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">~40%</span><br><span style="color: #aaa;">喫煙によるオッズ増加</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">3次</span><br><span style="color: #aaa;">最良の用量反応適合</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">棄却</span><br><span style="color: #aaa;">流動性の対称性</span></div>
  </div>
</div>

- 対数変換したmpgモデルにより、自動車データの不等分散問題を解決。
- **粉塵曝露**と雇用期間が綿肺症の最も強い予測因子であり、喫煙はオッズを約40%増加させた。
- 政治的自由化がクーデター頻度を減少させ、対応分析により異なる教育-コミュニティプロファイルが明らかに。
- 社会的流動性の**対称性は棄却**された ── 上方移動と下方移動の階層間遷移は不均等。

<div style="margin-top: 25px;">
  <a href="/files/CDA_HW1_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">レポート1</a>
  <a href="/files/CDA_HW2_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">レポート2</a>
  <a href="/files/CDA_HW3_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">レポート3</a>
  <a href="/files/CDA_HW4_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">レポート4</a>
  <a href="/files/CDA_HW5_Categorical.pdf" style="display: inline-block; background: #0d9488; color: white; padding: 10px 18px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">レポート5</a>
</div>
