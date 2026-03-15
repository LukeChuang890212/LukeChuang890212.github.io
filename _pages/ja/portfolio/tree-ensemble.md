---
title: "決定木とアンサンブル学習：自転車シェアリング需要予測と航空顧客満足度分析"
permalink: /ja/portfolio/tree-ensemble/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1a4731 0%, #065f46 50%, #059669 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #6ee7b7; margin-top: 0; font-size: 1.6em;">1本の木では足りない――アンサンブルの出番</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    単一の決定木から <strong>Random Forest</strong>、<strong>Gradient Boosting</strong> へ――<strong>731日分の自転車シェアリング</strong>記録と<strong>10万件超の航空満足度</strong>調査データで、木ベース手法の限界を押し広げる。
  </p>
</div>

## データと前処理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #065f46; margin-top: 0;">自転車シェアリングデータ</h3>
    <p><strong>731日分の観測値</strong>（2011〜2012年）、予測変数11個：季節、天候、気温、湿度、風速など。応答変数は日次利用台数。80/20の訓練・テスト分割。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fef3c7; border-left: 5px solid #d97706; padding: 20px; border-radius: 8px;">
    <h3 style="color: #92400e; margin-top: 0;">航空満足度調査</h3>
    <p><strong>103,594件</strong>の回答、予測変数23個：デモグラフィクス、旅行情報、14項目のサービス評価、遅延指標。二値応答：満足 vs. 不満足。80/20分割。</p>
  </div>
</div>

## 探索的データ分析（EDA）

- **自転車シェアリング**：気温が最も強い正の相関を示す（r = 0.627）。2次の気温効果を検出――利用台数は約20度Cでピークに達した後、減少に転じる。
- **航空**：サービス評価項目が高い識別力を持つ。大多数の顧客はリピーターのビジネス旅行者。遅延時間は強い右歪みを示す。

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">決定木</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">コスト複雑度 CV による剪定</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">CV で m パラメータを調整</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">Gradient Boosting</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">グリッドサーチ：深さ・縮小率・木の数</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">線形回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Best Subset によるベンチマーク</p>
  </div>
  <div style="background: #ecfdf5; border: 2px solid #059669; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #065f46; font-size: 1.1em;">非線形回帰</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">多項式 + B-spline</p>
  </div>
  <div style="background: #fef3c7; border: 2px solid #d97706; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #92400e; font-size: 1.1em;">ノイズ変数注入テスト</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">変数重要度ランキングの検証</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #6ee7b7; margin: 5px 0;">アンサンブルが勝利</p>
      <p style="color: #aaa;">RF と GBM が単一木・線形モデルを自転車データで上回る</p>
    </div>
    <div style="flex: 1; min-width: 220px; text-align: center;">
      <p style="font-size: 2.2em; font-weight: bold; color: #fbbf24; margin: 5px 0;">10万件超の調査</p>
      <p style="color: #aaa;">ノイズ検証済みの重要度に基づく航空分類</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">年 + 気温</span><br><span style="color: #aaa;">自転車の上位予測因子</span></div>
    <div style="text-align: center;"><span style="font-size: 1.5em; font-weight: bold; color: #93c5fd;">Online Boarding</span><br><span style="color: #aaa;">航空の上位予測因子</span></div>
  </div>
</div>

- **年**と**気温**が全手法を通じて自転車シェアリングの上位予測因子に一貫してランクインした。
- B-spline 回帰は多項式モデルよりも気温の閾値効果を的確に捉えた。
- Online Boarding、機内Wi-Fi、旅行タイプが満足度の主要ドライバーであることを、ノイズ変数注入テストで確認。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW4_Tree_Methods.pdf" style="display: inline-block; background: #065f46; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">レポート全文をダウンロード（PDF）</a>
</div>
