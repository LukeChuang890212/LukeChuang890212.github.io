---
title: "決定木とアンサンブル学習：自転車シェアリングと航空満足度"
permalink: /ja/portfolio/tree-ensemble/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <a href="/zh/portfolio/">中文</a> | <strong>日本語</strong></div>

<div style="background: linear-gradient(135deg, #1a4731 0%, #065f46 50%, #059669 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #6ee7b7; margin-top: 0; font-size: 1.6em;">1本の木では足りないとき——アンサンブルの出番</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    単一の決定木から <strong>Random Forest</strong>、<strong>Gradient Boosting</strong> まで——<strong>731件の自転車シェアリング</strong>記録と <strong>103K件の航空満足度</strong>調査で、木ベース手法の限界に挑む。
  </p>
</div>

## データソースとクリーニング

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #065f46; margin-top: 0;">自転車シェアリングデータ</h3>
    <p><strong>731日分の観測値</strong>（2011〜2012年）、11予測変数：季節、天候、気温、湿度、風速など。応答変数：日次利用台数。80/20 の訓練・テスト分割。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fef3c7; border-left: 5px solid #d97706; padding: 20px; border-radius: 8px;">
    <h3 style="color: #92400e; margin-top: 0;">航空満足度調査</h3>
    <p><strong>103,594 観測値</strong>、23予測変数：人口統計、旅行情報、14項目のサービス評価、遅延指標。二値結果：満足 vs. 不満足。80/20 分割。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- **自転車シェアリング**：気温が最も強い正の相関を示す（r = 0.627）。二次の気温効果を検出——利用は約20°Cでピークに達し、その後減少。
- **航空**：サービス評価が強い識別力を持つ。大多数の顧客はロイヤルなビジネス旅行者。遅延は強い右歪みを示す。

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">決定木</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">コスト複雑度 CV による剪定</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV チューニングされた m パラメータ</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Gradient Boosting</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">グリッドサーチ：深度、縮小率、木の数</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">線形回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Best Subset ベンチマーク</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">非線形回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">多項式 + B-spline</p>
  </div>
  <div style="background: #fef3c7; border: 2px solid #d97706; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">ノイズ注入テスト</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">重要度ランキングの検証</p>
  </div>
</div>

## 主要な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #6ee7b7; margin: 5px 0;">アンサンブルが勝利</p>
      <p style="color: #aaa;">RF と GBM が単一木・線形モデルを自転車データで上回る</p>
    </div>
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #fbbf24; margin: 5px 0;">103K件の調査</p>
      <p style="color: #aaa;">ノイズ検証済み重要度による航空分類</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">年 + 気温</span><br><span style="color: #aaa;">自転車の上位予測因子</span></div>
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">Online Boarding</span><br><span style="color: #aaa;">航空の上位予測因子</span></div>
  </div>
</div>

- **年**と**気温**が全手法で一貫して自転車シェアリングの上位予測因子にランクされた。
- B-spline 回帰は多項式モデルより気温の閾値効果をうまく捉えた。
- Online Boarding、機内Wi-Fi、旅行タイプが満足度の上位要因——ノイズ変数注入で確認。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW4_Tree_Methods.pdf" style="display: inline-block; background: #065f46; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
