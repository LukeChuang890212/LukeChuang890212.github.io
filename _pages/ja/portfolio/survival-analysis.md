---
title: "生存時間分析：ノンパラメトリック推定と打ち切りデータのモデリング"
permalink: /ja/portfolio/survival-analysis/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #7f1d1d 0%, #b91c1c 50%, #ef4444 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fecaca; margin-top: 0; font-size: 1.6em;">不完全な観測からイベント発生時間を推定する</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    右側打ち切りを含む生存データには専用の手法が求められる。<strong>Kaplan-Meier 曲線</strong>から<strong>パラメトリックハザードモデル</strong>まで、臨床データおよび信頼性データを用いて生存時間分析の基礎を築く。
  </p>
</div>

## データと前処理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #fef2f2; border-left: 5px solid #ef4444; padding: 20px; border-radius: 8px;">
    <h3 style="color: #7f1d1d; margin-top: 0;">シミュレーション信頼性データ</h3>
    <p><strong>指数分布</strong>および<strong>Weibull 分布</strong>に従う寿命データ。生存関数・ハザード関数の理論的性質を導出するために使用。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fff7ed; border-left: 5px solid #f97316; padding: 20px; border-radius: 8px;">
    <h3 style="color: #9a3412; margin-top: 0;">臨床生存データ</h3>
    <p>右側打ち切りを含む<strong>43件の生存時間</strong>。すべての推定手順において、不完全な観測を適切に取り扱う必要がある。</p>
  </div>
</div>

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Kaplan-Meier</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ノンパラメトリック生存曲線 + Greenwood 分散</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">指数分布 MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">閉形式の Fisher 情報量</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Weibull モデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">増加・減少ハザードに柔軟に対応</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Log-Rank 検定</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">2群の生存曲線の比較</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Nelson-Aalen</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">累積ハザードの推定</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fca5a5; margin: 0;">打ち切りデータに挑む</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">不完全なイベント発生時間データに対するノンパラメトリック・パラメトリック手法</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">O(1/n)</span><br><span style="color: #aaa;">MLE 分散のスケーリング</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">KM</span><br><span style="color: #aaa;">打ち切りに対応</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Weibull</span><br><span style="color: #aaa;">柔軟なハザード形状</span></div>
  </div>
</div>

- Kaplan-Meier 推定量は右側打ち切りデータを適切に処理し、一致性のある生存関数推定を提供した。
- 指数分布 MLE の分散は **O(1/n)** のオーダーでスケーリングし、明示的な閉形式の表現を導出。
- Weibull モデルは形状パラメータを通じて、増加・減少いずれのハザードパターンも柔軟に捉えた。

---

## 最終プロジェクト：肝硬変の生存モデリング

<div style="background: linear-gradient(135deg, #4a1942 0%, #7b2d5f 50%, #c2185b 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #f8bbd0; margin-top: 0; font-size: 1.3em;">疾患ステージ層別 Cox PH モデルと前方変数選択</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    <strong>Mayo Clinic 原発性胆汁性肝硬変</strong>データセットを対象とした包括的な生存時間分析。疾患ステージ（1&2, 3, 4）による患者層別化を行い、<strong>自作実装</strong>の Cox 偏尤度最適化・前方変数選択・交差検証を適用。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Cox PH モデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">偏尤度のスクラッチ実装 + L-BFGS-B 最適化</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">前方変数選択</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">逸脱度ベース、3分割 CV</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">ステージ層別化</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">疾患重症度ごとの個別ベースラインハザード</p>
  </div>
</div>

<div style="background: #1a1a2e; padding: 20px; border-radius: 10px; margin: 20px 0; text-align: center;">
  <p style="color: #f8bbd0; font-size: 1.3em; font-weight: bold; margin: 0;">最も重要な知見</p>
  <p style="color: #ccc; margin-top: 8px; font-size: 1.05em;"><strong style="color: #f48fb1;">ビリルビン</strong>は、すべての疾患ステージにおいて CV シードの<strong style="color: #7fecb3;">100%</strong>で選択された。肝硬変患者の生存予測における最も安定した因子である。</p>
</div>

<div style="margin-top: 25px;">
  <a href="/files/SA_HW1_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">HW1 をダウンロード（PDF）</a>
  <a href="/files/SA_HW2_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">HW2 をダウンロード（PDF）</a>
  <a href="/files/SA_Final_Survival.pdf" style="display: inline-block; background: #880e4f; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">最終プロジェクトをダウンロード（PDF）</a>
</div>
