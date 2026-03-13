---
title: "生存時間分析：ノンパラメトリック推定と打ち切りデータモデリング"
permalink: /ja/portfolio/survival-analysis/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #7f1d1d 0%, #b91c1c 50%, #ef4444 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #fecaca; margin-top: 0; font-size: 1.6em;">不完全な観測によるイベント発生時間のモデリング</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    右側打ち切りの生存データには特殊な手法が必要です。<strong>Kaplan-Meier曲線</strong>から<strong>パラメトリックハザードモデル</strong>まで、臨床データおよび信頼性データに基づく生存時間分析の基礎を構築します。
  </p>
</div>

## データソースとクリーニング

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #fef2f2; border-left: 5px solid #ef4444; padding: 20px; border-radius: 8px;">
    <h3 style="color: #7f1d1d; margin-top: 0;">シミュレーション信頼性データ</h3>
    <p>生存関数とハザード関数の理論的性質を導出するための、<strong>指数分布</strong>および<strong>Weibull分布</strong>に従う寿命データ。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #fff7ed; border-left: 5px solid #f97316; padding: 20px; border-radius: 8px;">
    <h3 style="color: #9a3412; margin-top: 0;">臨床生存データ</h3>
    <p>右側打ち切りを含む<strong>43の生存時間</strong>。すべての推定手順で不完全な観測の慎重な取り扱いが必要。</p>
  </div>
</div>

## 手法

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 20px 0;">
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Kaplan-Meier</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ノンパラメトリック生存曲線 + Greenwood分散</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">指数分布MLE</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">閉形式のFisher情報量</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Weibullモデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">増加/減少ハザードに柔軟に対応</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Log-Rank検定</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">2群の生存曲線比較</p>
  </div>
  <div style="background: #fef2f2; border: 2px solid #ef4444; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #7f1d1d; font-size: 1.1em;">Nelson-Aalen</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">累積ハザード推定</p>
  </div>
</div>

## 主な結果

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0; text-align: center;">
  <p style="font-size: 2em; font-weight: bold; color: #fca5a5; margin: 0;">打ち切りデータへの対処</p>
  <p style="color: #aaa; font-size: 1.1em; margin-top: 5px;">不完全なイベント発生時間データに対するノンパラメトリック・パラメトリック手法</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">O(1/n)</span><br><span style="color: #aaa;">MLE分散のスケーリング</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">KM</span><br><span style="color: #aaa;">打ち切りに対応</span></div>
    <div><span style="font-size: 1.8em; font-weight: bold; color: #7fecb3;">Weibull</span><br><span style="color: #aaa;">柔軟なハザード形状</span></div>
  </div>
</div>

- Kaplan-Meier推定量は右側打ち切りデータを適切に処理し、一致性のある生存関数推定値を提供。
- 指数分布MLEの分散は**O(1/n)**でスケーリングし、明示的な閉形式の表現を導出。
- Weibullモデルは形状パラメータにより、増加・減少の両方のハザードパターンを捉えた。

---

## 最終プロジェクト：肝硬変の生存モデリング

<div style="background: linear-gradient(135deg, #4a1942 0%, #7b2d5f 50%, #c2185b 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #f8bbd0; margin-top: 0; font-size: 1.3em;">ステージ層別Cox PHモデルと前方変数選択</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    <strong>Mayo Clinic原発性胆汁性肝硬変</strong>データセットの包括的な生存時間分析。疾患ステージ（1&2, 3, 4）で患者を層別化し、<strong>自作実装</strong>のCox偏尤度最適化、前方変数選択、交差検証を適用。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">Cox PHモデル</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">手書き偏尤度 + L-BFGS-B最適化</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">前方選択</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">逸脱度ベースの3-fold CV</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #fce4ec; border: 2px solid #c2185b; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #880e4f; font-size: 1.05em;">ステージ層別化</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">疾患重症度ごとの個別モデル</p>
  </div>
</div>

<div style="background: #1a1a2e; padding: 20px; border-radius: 10px; margin: 20px 0; text-align: center;">
  <p style="color: #f8bbd0; font-size: 1.3em; font-weight: bold; margin: 0;">主要な知見</p>
  <p style="color: #ccc; margin-top: 8px; font-size: 1.05em;"><strong style="color: #f48fb1;">ビリルビン</strong>はすべての疾患ステージにおいてCVシードの<strong style="color: #7fecb3;">100%</strong>で選択され、肝硬変患者の生存における最も一貫した予測因子であった。</p>
</div>

<div style="margin-top: 25px;">
  <a href="/files/SA_HW1_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">HW1をダウンロード（PDF）</a>
  <a href="/files/SA_HW2_Survival.pdf" style="display: inline-block; background: #b91c1c; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold; margin-right: 10px;">HW2をダウンロード（PDF）</a>
  <a href="/files/SA_Final_Survival.pdf" style="display: inline-block; background: #880e4f; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">最終プロジェクトをダウンロード（PDF）</a>
</div>
