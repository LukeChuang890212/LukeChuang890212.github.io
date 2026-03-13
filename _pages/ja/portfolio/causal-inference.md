---
title: "因果推論と生物データ分析"
permalink: /ja/portfolio/causal-inference/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1e1b4b 0%, #312e81 50%, #4f46e5 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #a5b4fc; margin-top: 0; font-size: 1.6em;">相関から因果へ ── 適切なツールで</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    <strong>因果推論</strong>と<strong>生物統計モデリング</strong>への深い探求。因果推論のためのDAG、処置効果のための傾向スコア、縦断データのための混合効果モデル、研究間のエビデンス統合のためのメタ分析。
  </p>
</div>

## データソースとクリーニング

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">妊娠率データ</h4>
    <p style="font-size: 0.9em;">1,154件の観測値 ── 性交年数をoffsetとしたカウントアウトカム</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">心臓カテーテル検査</h4>
    <p style="font-size: 0.9em;">ROC分析のための訓練/検証分割を用いた症例対照研究</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">歯科矯正成長データ</h4>
    <p style="font-size: 0.9em;">縦断的な歯科測定（8-14歳）、性別効果あり</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">BCGワクチンメタ分析</h4>
    <p style="font-size: 0.9em;">7つの臨床研究 ── 固定効果・変量効果による統合</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">職業訓練因果データ</h4>
    <p style="font-size: 0.9em;">傾向スコア手法のための観察給与データ</p>
  </div>
  <div style="background: #eef2ff; border-left: 5px solid #4f46e5; padding: 15px; border-radius: 8px;">
    <h4 style="color: #312e81; margin-top: 0;">因果DAG構造</h4>
    <p style="font-size: 0.9em;">未測定交絡因子、合流点、操作変数</p>
  </div>
</div>

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">Poisson GLM</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">offsetを用いた率モデリング + 準Poisson</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">ロジスティック + ROC</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">AUC = 0.809、キャリブレーションプロット</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">DAG推論</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">調整セット、合流点バイアス、操作変数</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">混合効果モデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">lme4によるランダム切片 + 傾き</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">GEE</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">周辺モデル、QIC/CIC選択</p>
  </div>
  <div style="background: #eef2ff; border: 2px solid #4f46e5; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #312e81; font-size: 1.05em;">IPTW + DR</strong>
    <p style="margin: 8px 0 0; font-size: 0.85em; color: #666;">傾向スコア、二重ロバスト推定</p>
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
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">IPTW</span><br><span style="color: #aaa;">有意な訓練効果</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">p < 0.05</span><br><span style="color: #aaa;">性別による成長差</span></div>
    <div style="text-align: center;"><span style="font-size: 1.4em; font-weight: bold; color: #7fecb3;">B = 500</span><br><span style="color: #aaa;">DR推論のためのBootstrap</span></div>
  </div>
</div>

- 年齢が妊娠率の最も強い予測因子であり、過分散には分散膨張が必要であった。
- 男女で歯科成長の傾きに有意差あり（Kenward-Roger検定）。
- **BCGワクチン**は固定効果・変量効果メタ分析の両方で結核リスクを有意に低下させた。
- **IPTW**、標準化、二重ロバスト推定量のすべてが、職業訓練の給与に対する正の因果効果を確認した。

<div style="margin-top: 25px;">
  <a href="/files/BDA_HW1_GLM.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">GLM分析</a>
  <a href="/files/BDA_HW2_Causal.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">因果DAG</a>
  <a href="/files/BDA_Midterm_Mixed_Effects.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">混合効果 & GEE</a>
  <a href="/files/BDA_Term_Causal_Inference.pdf" style="display: inline-block; background: #4f46e5; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold; margin: 4px;">因果推論</a>
</div>
