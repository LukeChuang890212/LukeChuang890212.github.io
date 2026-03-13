---
title: "野球分析：2026 WBC 台湾対日本戦 2回の崩壊を検証"
permalink: /ja/portfolio/baseball-jpn/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1a0a0a 0%, #4a1a1a 50%, #8b0000 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ff6b6b; margin-top: 0; font-size: 1.6em;">2026 WBC プールC：台湾 vs. 日本（2026年3月9日）</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    日本は<strong style="color: #ff6b6b;">2回に10失点</strong>を記録——壊滅的な単一イニングの崩壊であった。先発の<strong>鄭浩均（Cheng）</strong>は 1.2回 8自責点で降板し、直ちに批判の矛先が向けられた。しかしそれは妥当だったのか？投球データと機械学習モデルを用いて検証した。
  </p>
</div>

## 2つの問い

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 280px; background: #fff3f3; border-left: 5px solid #dc2626; padding: 20px; border-radius: 8px;">
    <h3 style="color: #dc2626; margin-top: 0;">Q1：本当に鄭浩均の責任だったのか？</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">先発投手が単独で崩壊を引き起こしたのか、それとも同イニングに登板した3投手全員に共通する構造的問題だったのか？</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #2563eb; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2563eb; margin-top: 0;">Q2：鄭浩均は大谷翔平にもっと上手く対処できたか？</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">満塁のカウント2-1という運命の場面で、鄭浩均が投じたカーブを大谷翔平は満塁本塁打に仕留めた。より賢い球種選択はあったのか？</p>
  </div>
</div>

---

## 第1部：崩壊の診断

### 2回の投球推移

<img src="/images/jpn_inning2_progression.png" alt="2回の打席推移" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">各ドットは2回における1球を表す。Y軸はカウントレバレッジ（ボール数 − ストライク数）を追跡：ゼロより上は打者有利を示す。赤い星は得点打を示す。鄭浩均がダメージ投球の<strong>前に</strong>いかに頻繁に打者にカウントで先行されていたかに注目。</p>

### 根本原因：カウント制御

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <p style="color: #ff6b6b; font-size: 1.3em; font-weight: bold; margin: 0 0 15px 0; text-align: center;">失点の原因</p>
  <img src="/images/jpn_damage_analysis.png" alt="カウントと球種選択分析" style="width: 100%; max-width: 1000px; border-radius: 8px; margin: 0 auto; display: block;">
  <p style="color: #ccc; font-size: 0.95em; margin-top: 15px; text-align: center;">左：各ダメージ投球時のカウント——赤い棒（打者有利カウント）が圧倒的。右：イニング全体の球種別得点率。</p>
</div>

<div style="background: #fef2f2; border: 2px solid #dc2626; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #991b1b; margin-top: 0;">重要な知見：鄭浩均の制球問題が大谷翔平に満塁の場面を作った</h4>
  <p style="line-height: 1.7;">鄭浩均は繰り返しカウントで先行を許し、打者有利の状況を作り出した。大谷翔平が打席に入る時点で塁は既に埋まっていた——それは1球の失投によるものではなく、前の打者たちとの<strong>カウント争いに負け続けたパターン</strong>によるものだった。大谷翔平が打席に立つ前に、崩壊の下地は既に整っていた。</p>
</div>

### 3投手全員が被弾

<img src="/images/jpn_damage_pitch_map.png" alt="投手別ダメージ投球位置" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">赤い星は3投手全員の得点投球を示す：鄭浩均（1.2回、8自責点）、胡（0.1回、2自責点）、沙（2.0回、3自責点）。鄭浩均の降板後も失血は続いた——これは一人の投手だけの問題ではなかった。</p>

### 鄭浩均の球種構成

<img src="/images/jpn_cheng_pitch_location.png" alt="鄭浩均の球種別投球位置" style="width: 100%; max-width: 600px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">鄭浩均の54球を球種別に分類：チェンジアップ（11）、カーブ（7）、フォーシームファストボール（29）、スライダー（7）。ファストボールの制球が不安定で、多くの投球がゾーン中央に流れていた。</p>

---

## 第2部：満塁本塁打——鄭浩均にはもっと良い選択肢があったか？

<div style="background: linear-gradient(135deg, #0f172a 0%, #1e3a5f 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #93c5fd; margin-top: 0; font-size: 1.3em;">大谷翔平のヒット確率モデリング</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    大谷翔平の <strong>2025年 MLBシーズンデータ</strong>（1,271スイング、169安打）を使用し、<strong>Random Forest</strong> と <strong>Gradient Boosting Machine</strong> モデルを訓練して、投球位置、球種、球速、回転数、変化量を関数として P(hit) を予測した。これらのモデルを鄭浩均の実際の満塁本塁打投球に適用し、その判断を評価した。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">P(swing) と P(hit|swing) のノンパラメトリックアンサンブル</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">ヒット確率モデリングのための勾配ブースティング</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">特徴量重要度と投球レベルの説明</p>
  </div>
</div>

### 大谷翔平のヒットゾーン（2025年 MLBシーズン）

<img src="/images/jpn_ohtani_hit_heatmap.png" alt="大谷翔平 2025年ヒットヒートマップ" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">大谷翔平の2025年打撃プロファイル：ヒット密度のKDE（左上）、ゾーンビン別ヒット率（右上）、スイング時ヒット率（左下）、単打 vs. 長打の位置（右下）。赤い星は鄭浩均の満塁本塁打カーブの位置を示す。</p>

### 満塁本塁打投球：モデルの判定

<img src="/images/jpn_ohtani_hit_model.png" alt="大谷翔平満塁本塁打モデル分析" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit) = 13.2%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">鄭浩均が投じたカーブ（76.8 mph、2483 rpm、pX=-0.46、pZ=2.16）は、RF/GBMアンサンブルに基づく<strong>予測ヒット確率が約13%</strong>であった。数字上は悪い投球ではなかった。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">鄭浩均は勇気ある選択をした</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">満塁で一塁が空いている状況（敬遠も可能）にもかかわらず、鄭浩均は<strong>真っ向勝負を選んだ</strong>——2025年ワールドシリーズで同様の状況で大谷翔平を敬遠したブルージェイズとは対照的であった。これは勇敢な決断だった。</p>
  </div>
</div>

### 大谷翔平のヒット確率を左右する要因

<img src="/images/jpn_ohtani_shap.png" alt="大谷翔平ヒットモデルのSHAP分析" style="width: 100%; max-width: 800px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">SHAPサマリー（左上）、満塁本塁打投球の個別分解（右上）、垂直位置と球速の依存プロット（下段）。満塁本塁打カーブのSHAP分解は P(hit|swing) = 12.5% を示す——回転数とゾーン内であることがやや押し上げたが、位置と垂直変化量が抑制した。</p>

### 最適配球戦略

<img src="/images/jpn_ohtani_pitch_strategy.png" alt="最適投球位置戦略" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>P(hit) = P(swing) x P(hit|swing)</strong>——GBMとRFのアンサンブル平均、ストライクゾーン内に制約。青い点は各球種で最も低い P(hit) の位置を示し、赤い×は鄭浩均が実際に満塁本塁打カーブを投じた位置。各球種において、より低い予測ヒット確率の位置が存在した。</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">モデルの推奨</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">チェンジアップ</span><br><span style="color: #aaa;">低め内角——P(hit) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">ファストボール</span><br><span style="color: #aaa;">低め外角——P(hit) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #fca5a5;">カーブ</span><br><span style="color: #aaa;">鄭浩均の選択——P(hit) = 4.8%*</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">*最適カーブ位置での値。鄭浩均が実際に投じた位置では 13.2%。低め外角ファストボールまたは低め内角チェンジアップが統計的に最も安全な選択であった。</p>
</div>

---

## 結論

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>鄭浩均のカウント制御が真の問題</strong>——繰り返し打者にカウントで先行を許し、大谷翔平の打席前に満塁の状況を作った。崩壊は1球ではなく、パターンによって引き起こされた。</li>
    <li><strong>満塁本塁打の投球は悪い球ではなかった</strong>——予測ヒット確率 13.2% のカーブは妥当な選択であった。鄭浩均は敬遠ではなく大谷翔平との真っ向勝負を選んだ勇気を示した。</li>
    <li><strong>改善の余地はあった</strong>——モデルは低め外角ファストボール（P(hit) 3.6%）または低め内角チェンジアップ（4.1%）が、鄭浩均が選んだカーブの位置より統計的に安全であったことを示唆している。</li>
    <li><strong>鄭浩均降板後も失点は続いた</strong>——胡と沙は合計5自責点を記録し、これがチーム全体の守備崩壊であり、一人の投手の失敗ではなかったことを証明した。</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  野球は確率のスポーツである。13%のヒットが満塁本塁打となり、一つの物語が生まれる。しかしデータはより繊細な真実を語る——体系的なカウント管理の問題、勇敢な投球判断、そしてこのスポーツを美しくする残酷なランダム性の物語を。
</div>
