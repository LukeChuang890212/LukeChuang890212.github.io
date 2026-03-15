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
    大谷翔平の <strong>2025年 MLBシーズンデータ</strong> を使用し、<strong>Random Forest</strong> と <strong>Gradient Boosting Machine</strong> モデルを訓練して、<strong>P(swing | pitch)</strong> と <strong>P(hit | swing, pitch)</strong> を別々に予測した。ここで「pitch」は完全な投球プロファイル（位置、球種、球速、回転数、変化量）を示す。統合指標 <strong>P(hit | pitch) = P(swing | pitch) × P(hit | swing, pitch)</strong> が各投球の総合的な危険度を与える。これらのモデルを鄭浩均の実際の満塁本塁打投球に適用し、その判断を評価した。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">P(swing | pitch) と P(hit | swing, pitch) のノンパラメトリックアンサンブル</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">P(swing | pitch) と P(hit | swing, pitch) の勾配ブースティング</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">特徴量重要度と投球レベルの説明</p>
  </div>
</div>

### 大谷翔平の打撃プロファイル：P(swing | loc)、P(hit | swing, loc)、P(hit | loc)（2025年 MLBシーズン）

<img src="/images/jpn_ohtani_kde_heatmap.png" alt="大谷翔平 KDE ヒートマップ" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">大谷翔平の2025年 MLB打撃データに基づくカーネル平滑化推定値、<em>位置のみ</em>を条件とする。各行は球種カテゴリ（全体、ファストボール、ブレーキング、オフスピード）、各列は確率成分。<strong>左：P(swing | loc)</strong>——大谷翔平がどこでスイングするか。<strong>中：P(hit | swing, loc)</strong>——スイング時にどこが危険か。<strong>右：P(hit | loc)</strong>——各位置の総合危険度。赤い十字は鄭浩均の満塁本塁打カーブの位置（pX=−0.46, pZ=2.16）を示す。</p>

<div style="background: #eff6ff; border: 2px solid #2563eb; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #1e3a5f; margin-top: 0;">KDEから分かること</h4>
  <p style="line-height: 1.7;"><strong>ブレーキングボールの行</strong>（第3行）を見ると、満塁本塁打カーブは <strong>P(swing | loc) が中程度</strong>で <strong>P(hit | swing, loc) が比較的低い</strong>ゾーンに着弾している。この位置の P(hit | loc) はホットゾーンではない——鄭浩均は合理的な位置に投球していた。ブレーキングボールの高危険ゾーンはインコース寄りの中央部と高めに集中しており、鄭浩均のカーブはこれらからやや離れていた。</p>
</div>

### 満塁本塁打投球：モデルの判定

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">上記のKDEヒートマップは位置のみを条件としている。<em>特定の</em>満塁本塁打投球を評価するため、完全な投球プロファイル——位置、球速、回転数、変化量、カウント——をRFとGBMモデルに入力する：</p>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 180px; background: #f0fdf4; border: 2px solid #059669; padding: 18px; border-radius: 10px; text-align: center;">
    <p style="color: #059669; font-weight: bold; font-size: 1.1em; margin: 0;">P(swing | pitch)</p>
    <p style="font-size: 1.8em; font-weight: bold; margin: 8px 0 4px; color: #1a1a2e;">~71%</p>
    <p style="font-size: 0.8em; color: #666; margin: 0;">GBM: 74.8% · RF: 67.5%</p>
  </div>
  <div style="flex: 0 0 30px; display: flex; align-items: center; justify-content: center; font-size: 1.5em; color: #999;">×</div>
  <div style="flex: 1; min-width: 180px; background: #f0fdf4; border: 2px solid #059669; padding: 18px; border-radius: 10px; text-align: center;">
    <p style="color: #059669; font-weight: bold; font-size: 1.1em; margin: 0;">P(hit | swing, pitch)</p>
    <p style="font-size: 1.8em; font-weight: bold; margin: 8px 0 4px; color: #1a1a2e;">~13%</p>
    <p style="font-size: 0.8em; color: #666; margin: 0;">GBM: 12.5% · RF: 14.0%</p>
  </div>
  <div style="flex: 0 0 30px; display: flex; align-items: center; justify-content: center; font-size: 1.5em; color: #999;">=</div>
  <div style="flex: 1; min-width: 180px; background: #ecfdf5; border: 2px solid #047857; padding: 18px; border-radius: 10px; text-align: center;">
    <p style="color: #047857; font-weight: bold; font-size: 1.1em; margin: 0;">P(hit | pitch)</p>
    <p style="font-size: 1.8em; font-weight: bold; margin: 8px 0 4px; color: #047857;">~9%</p>
    <p style="font-size: 0.8em; color: #666; margin: 0;">GBM: 9.4% · RF: 9.5%</p>
  </div>
</div>

<div style="background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px; margin: 20px 0;">
  <h4 style="color: #92400e; margin-top: 0;">投球品質——位置だけでなく——がこれを良い投球にした理由</h4>
  <p style="line-height: 1.7; margin-bottom: 12px;">SHAP分析により、位置以外で P(hit | swing, pitch) を抑制した特徴が明らかになった：</p>
  <ul style="line-height: 2;">
    <li><strong>回転数（2,483 rpm）</strong>——P(hit | swing, pitch) を下げる最大の要因。高回転がより鋭く遅いブレークを生み、クリーンなコンタクトを困難にする。</li>
    <li><strong>縦変化量（pfx_z = −7.09 in.）</strong>——強い落下でバットがボールの軌道の下を通過し、弱い打球や空振りを誘発。</li>
    <li><strong>球速（76.8 mph）</strong>——鄭浩均のファストボールとの20+ mphの速度差が大谷翔平のスイングタイミングを崩す。</li>
    <li><strong>回転軸（45°）</strong>——落下とアームサイドの動きの組み合わせが投球の変化を欺瞞的にする。</li>
  </ul>
  <p style="line-height: 1.7; margin-bottom: 0;">投球がゾーン内にあったこと（P(swing | pitch) を上昇させる）にもかかわらず、これらの品質が P(hit | swing, pitch) をわずか約13%に抑えた——大谷翔平の全体的なスイング時打率を大きく下回る。<strong>これは確かに良い投球であった。</strong></p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit | pitch) ≈ 9%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">スイング確率とコンタクト品質を組み合わせると、このカーブは<strong>約9%のヒット確率</strong>しかなかった。投球の回転、変化、速度差がすべて P(hit | pitch) を抑制した——91%の生存率は妥当な賭けであった。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">鄭浩均は勇気ある選択をした</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">満塁の状況で、鄭浩均は<strong>真っ向勝負を選んだ</strong>——2025年ワールドシリーズで同様の状況で大谷翔平を敬遠したブルージェイズとは対照的であった。モデルはこれが勇敢かつ統計的に合理的な判断であったことを裏付けた。</p>
  </div>
</div>

### 最適配球戦略：鄭浩均はどこを狙うべきだったか？

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">鄭浩均の満塁本塁打カーブは P(hit | pitch) ≈ 9%——既に低い値であった。しかしさらに良くできたか？KDEヒートマップは位置のみを条件とし、モデル判定は<em>1球の特定投球</em>を条件とする。戦略の問いに答えるには、<strong>位置</strong>を変化させつつ鄭浩均の投球プロファイルを固定する必要がある——各球種の平均球速、回転数、変化量を使用する。これにより P(hit | Cheng's profile, loc) の実用的マップが得られる：鄭浩均の4球種それぞれ、どこを狙うべきだったか？</p>

<img src="/images/jpn_ohtani_pitch_strategy_decomp.png" alt="配球戦略分解——鄭浩均 vs 大谷、鄭浩均のプロファイルで条件付け" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">GBMとRFのアンサンブル平均、<strong>鄭浩均の各球種平均投球プロファイル</strong>で条件付け（カウント2-1）。各行は鄭浩均の4球種の1つ（フォーシームファストボール、カーブ、チェンジアップ、スライダー）。<strong>左：P(swing | Cheng's profile, loc)</strong>——鄭浩均の投球に対して大谷翔平がどこでスイングするか。<strong>中：P(hit | swing, Cheng's profile, loc)</strong>——コンタクトがどこで最も危険か。<strong>右：P(hit | Cheng's profile, loc)</strong>——総合危険度指標。赤い十字は鄭浩均が実際に満塁本塁打カーブを投じた位置、青い星は各球種の最適（最低P(hit)）位置を示す。重要な知見：P(hit | swing, Cheng's profile, loc) が高くても P(swing | Cheng's profile, loc) が低いゾーン（例：低め外角）があり、コンタクト危険度が高くても戦略的に安全である。</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">モデルの推奨（青い星 = 最適位置）</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">ファストボール</span><br><span style="color: #aaa;">低め外角 — P(hit | Cheng's FF, loc*) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">チェンジアップ</span><br><span style="color: #aaa;">低め内角 — P(hit | Cheng's CH, loc*) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">カーブ</span><br><span style="color: #aaa;">最適位置 — P(hit | Cheng's CU, loc*) = 4.8%</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">loc* = 青い星（最適位置）。赤い十字 = 鄭浩均が実際に投じた位置（P(hit | pitch) ≈ 9%）。すべての値は鄭浩均の球種別平均投球プロファイルで条件付け。カーブを最適位置に投じても（4.8%）、低め外角ファストボール（3.6%）や低め内角チェンジアップ（4.1%）よりリスクが高い。</p>
</div>

---

## 結論

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>鄭浩均のカウント制御が真の問題</strong>——繰り返し打者にカウントで先行を許し、大谷翔平の打席前に満塁の状況を作った。崩壊は1球ではなく、パターンによって引き起こされた。</li>
    <li><strong>満塁本塁打の投球は悪い球ではなかった</strong>——RF/GBMモデルは P(swing | pitch) ≈ 71%、P(hit | swing, pitch) ≈ 13%、P(hit | pitch) ≈ 9% を示す。カーブの高回転数（2,483 rpm）、強い縦変化（−7.09 in.）、20+ mphの速度差がヒット確率を大谷翔平の平均を大きく下回る水準に抑えた。鄭浩均は敬遠ではなく真っ向勝負を選んだ勇気を示した。</li>
    <li><strong>改善の余地はあった</strong>——鄭浩均自身の投球プロファイルで条件付けすると、最適カーブ位置（青い星）は P(hit | Cheng's CU, loc) を9%から4.8%に低減できた。しかし低め外角ファストボール（3.6%）や低め内角チェンジアップ（4.1%）がさらに安全な選択であった。</li>
    <li><strong>鄭浩均降板後も失点は続いた</strong>——胡と沙は合計5自責点を記録し、これがチーム全体の守備崩壊であり、一人の投手の失敗ではなかったことを証明した。</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  野球は確率のスポーツである。P(hit | pitch) ≈ 9%の投球——高回転、鋭い変化、20 mphの速度差によって抑制された——が満塁本塁打となり、一つの物語が生まれる。しかしデータはより繊細な真実を語る——体系的なカウント管理の問題、勇敢な投球判断、そしてこのスポーツを美しくする残酷なランダム性の物語を。
</div>
