---
title: "生活費分析：多変量手法による世界都市比較"
permalink: /ja/portfolio/final-project/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <a href="/zh/portfolio/">中文</a> | <strong>日本語</strong></div>

<div style="background: linear-gradient(135deg, #78350f 0%, #b45309 50%, #f59e0b 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fef3c7; margin-top: 0; font-size: 1.6em;">都市の物価を決めるものは何か？データに基づく回答</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    世界各都市にわたる<strong>55の支出変数</strong>を、PCA、因子分析、クラスタリングで分析し、世界の生活費格差の背後にある隠れた構造を明らかにしました。
  </p>
</div>

## データソースとクリーニング

8つの支出領域を網羅する包括的な生活費データセット：

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; margin: 20px 0;">
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">食事・外食</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">27変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">交通</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">8変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">施設・設備</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">娯楽</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">3変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">教育</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">2変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">衣料品</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">5変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">住居</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">6変数</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 12px; border-radius: 8px; text-align: center;">
    <strong style="color: #92400e;">その他</strong>
    <p style="margin: 5px 0 0; font-size: 0.85em; color: #666;">2変数</p>
  </div>
</div>

欠損データは**多重代入法**で処理。多変量分析の前にデータを標準化。

## 探索的データ分析（EDA）

- 都市間で住居費と教育費に大きなばらつき。
- 強い**領域内相関**（食品項目同士の相関）と中程度の領域間相関。
- 分布分析が標準化の判断を導いた。

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">PCA</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">変動の主要次元</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">因子分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">潜在的な支出パターン</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">クラスター分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">コストプロファイルによる都市分類</p>
  </div>
  <div style="background: #fffbeb; border: 2px solid #f59e0b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">多重代入法</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">欠損データの処理</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fbbf24; margin: 0;">55変数から解釈可能な構造へ</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">PCA、因子分析、クラスタリングが世界の生活費の構造を解明</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">PC1</span><br><span style="color: #aaa;">全体的なコスト水準</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">3階層</span><br><span style="color: #aaa;">都市コストクラスター</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">8領域</span><br><span style="color: #aaa;">因子分析で検証済み</span></div>
  </div>
</div>

- **PC1**は全体的なコスト水準を捉え、後続のPCは特定のパターン（例：住居費が高いが食費は中程度）を区別した。
- 因子分析は事前定義された8つの領域カテゴリと一致し、ドメイン知識を検証した。
- クラスター分析は**高コスト**、**中コスト**、**低コスト**の都市グループを、きめ細かなサブクラスターとともに特定した。

<div style="margin-top: 25px;">
  <a href="/files/SL_Final_Cost_of_Living.pdf" style="display: inline-block; background: #b45309; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
