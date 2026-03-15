---
title: "因果推論と生物統計データ分析"
permalink: /ja/portfolio/causal-inference/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1e1b4b 0%, #312e81 50%, #4f46e5 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a5b4fc; margin-top: 0; font-size: 1.6em;">相関から因果へ——適切な手法とともに</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    <strong>因果推論</strong>と<strong>生物統計モデリング</strong>を深く掘り下げる。因果構造を捉えるためのDAG、処置効果推定のための傾向スコア、縦断データのための混合効果モデル、複数研究のエビデンスを統合するためのメタ分析を網羅的に扱った。
  </p>
</div>

## データと前処理

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">妊娠率データ</h4>
    <p style="font-size: 0.9em;">1,154件の観測値——性交年数をoffsetとしたカウントアウトカム</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">心臓カテーテル検査</h4>
    <p style="font-size: 0.9em;">症例対照研究。ROC分析のため訓練・検証に分割</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">歯科矯正成長データ</h4>
    <p style="font-size: 0.9em;">8～14歳の縦断的な歯科測定値。性別効果あり</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">BCGワクチン メタ分析</h4>
    <p style="font-size: 0.9em;">7つの臨床研究——固定効果・変量効果モデルで統合</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">職業訓練の因果データ</h4>
    <p style="font-size: 0.9em;">傾向スコア手法のための観察的賃金データ</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">因果DAG構造</h4>
    <p style="font-size: 0.9em;">未測定交絡、合流点バイアス、操作変数</p>
  </div>
</div>

## 分析手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Poisson GLM</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">offsetを用いた発生率モデリング + 準Poisson</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">ロジスティック回帰 + ROC</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">AUC = 0.809、キャリブレーションプロット</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">DAG推論</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">調整変数セット、合流点バイアス、操作変数</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">混合効果モデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">lme4によるランダム切片 + ランダム傾き</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">GEE</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">周辺モデル、QIC/CICによるモデル選択</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">IPTW + DR</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">傾向スコア、二重頑健推定</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <div style="flex: 1; min-width: 200px; text-align: center;">
      <p style="font-size: 2em; font-weight: bold; color: #a5b4fc; margin: 5px 0;">AUC 0.809</p>
      <p style="color: #aaa;">心疾患ロジスティックモデル</p>
    </div>
    <div style="flex: 1; min-width: 200px; text-align: center;">
      <p style="font-size: 2em; font-weight: bold; color: #a5b4fc; margin: 5px 0;">OR 0.62</p>
      <p style="color: #aaa;">BCGワクチン効果（p < 0.001）</p>
    </div>
  </div>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">IPTW</span><br><span style="color: #aaa;">有意な訓練効果を確認</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">p < 0.05</span><br><span style="color: #aaa;">男女間の成長速度の差</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">B = 500</span><br><span style="color: #aaa;">DR推定のためのBootstrap</span></div>
  </div>
</div>

- 年齢が妊娠率の最も強い予測因子であり、過分散に対して分散膨張による補正が必要であった。
- 男女間で歯科成長の傾きに有意差が認められた（Kenward-Roger検定）。
- **BCGワクチン**は固定効果・変量効果メタ分析の双方で結核リスクを有意に低下させた。
- **IPTW**、標準化、二重頑健推定量のいずれも、職業訓練が賃金に正の因果効果をもたらすことを確認した。

<div style="margin-top: 25px;">
  <a href="/files/BDA_HW1_GLM.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">GLM分析</a>
  <a href="/files/BDA_HW2_Causal.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">因果DAG</a>
  <a href="/files/BDA_Midterm_Mixed_Effects.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">混合効果 & GEE</a>
  <a href="/files/BDA_Term_Causal_Inference.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">因果推論</a>
</div>
