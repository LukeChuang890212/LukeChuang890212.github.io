---
title: "野球分析：2026 WBC 台湾対日本戦 2回の大量失点を検証する"
permalink: /ja/portfolio/baseball-jpn/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1a0a0a 0%, #4a1a1a 50%, #8b0000 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ff6b6b; margin-top: 0; font-size: 1.6em;">2026 WBC プールC：台湾 vs. 日本（2026年3月9日）</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    日本が<strong style="color: #ff6b6b;">2回に10得点</strong>を挙げた——壊滅的な1イニングでの崩壊であった。先発の<strong>鄭浩均（Cheng）</strong>は 1.2回 8自責点で降板し、批判の矢面に立たされた。しかし、それは妥当な評価だったのか。投球データと機械学習モデルを用いて検証した。
  </p>
</div>

## 2つの問い

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 280px; background: #fff3f3; border-left: 5px solid #dc2626; padding: 20px; border-radius: 8px;">
    <h3 style="color: #dc2626; margin-top: 0;">Q1：本当に鄭浩均の責任だったのか？</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">先発投手が単独で崩壊を招いたのか、それとも同イニングに登板した3投手全員に共通する構造的な問題が原因だったのか。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #2563eb; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2563eb; margin-top: 0;">Q2：大谷翔平への配球に改善の余地はあったか？</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">満塁、カウント2-1という場面で、鄭浩均が投じたカーブを大谷翔平が満塁本塁打にした。より賢い球種選択は存在したのか。</p>
  </div>
</div>

---

## 第1部：崩壊の原因分析

### 2回の投球推移

<img src="/images/jpn_inning2_progression.png" alt="2回の打席推移" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">各ドットは2回の1球を表す。Y軸はカウントレバレッジ（ボール数 − ストライク数）で、ゼロを超えると打者有利を意味する。赤い星は得点に直結した安打を示す。注目すべきは、決定打の<strong>前に</strong>鄭浩均がいかに頻繁にカウントで先行を許していたかという点である。</p>

### 根本原因：カウント管理の失敗

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <p style="color: #ff6b6b; font-size: 1.3em; font-weight: bold; margin: 0 0 15px 0; text-align: center;">なぜ失点が重なったのか</p>
  <img src="/images/jpn_damage_analysis.png" alt="カウントと球種選択の分析" style="width: 100%; max-width: 1000px; border-radius: 8px; margin: 0 auto; display: block;">
  <p style="color: #ccc; font-size: 0.95em; margin-top: 15px; text-align: center;">左：各得点打時のカウント——赤い棒（打者有利カウント）が大半を占める。右：イニング全体での球種別被打率。</p>
</div>

<div style="background: #fef2f2; border: 2px solid #dc2626; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #991b1b; margin-top: 0;">重要な知見：鄭浩均のカウント管理の問題が大谷翔平に満塁の場面を与えた</h4>
  <p style="line-height: 1.7;">鄭浩均は繰り返しカウントで後手に回り、打者有利の状況を自ら作り出していた。大谷翔平が打席に入った時点で、すでに塁はすべて埋まっていた。それは1球の失投が原因ではなく、それ以前の打者たちとの<strong>カウント争いに負け続けたパターン</strong>の結果であった。崩壊の土台は、大谷翔平が打席に立つ前にすでに出来上がっていたのである。</p>
</div>

### 3投手全員が失点

<img src="/images/jpn_damage_pitch_map.png" alt="投手別の得点打位置" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">赤い星は3投手全員の得点打の位置を示す：鄭浩均（1.2回、8自責点）、胡（0.1回、2自責点）、沙（2.0回、3自責点）。鄭浩均が降板した後も失点は止まらなかった——これは一人の投手だけの問題ではなかった。</p>

### 鄭浩均の球種構成

<img src="/images/jpn_cheng_pitch_location.png" alt="鄭浩均の球種別投球位置" style="width: 100%; max-width: 600px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">鄭浩均の全54球の球種内訳：チェンジアップ（11球）、カーブ（7球）、フォーシーム（29球）、スライダー（7球）。フォーシームの制球が不安定で、多くの球がゾーン中央に甘く入っていた。</p>

---

## 第2部：あの満塁本塁打——鄭浩均にもっと良い選択肢はあったか？

<div style="background: linear-gradient(135deg, #0f172a 0%, #1e3a5f 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #93c5fd; margin-top: 0; font-size: 1.3em;">大谷翔平のヒット確率をモデル化する</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    大谷翔平の<strong>2025年 MLBシーズン</strong>の全打撃データを用いて、<strong>Random Forest</strong> と <strong>Gradient Boosting Machine</strong> モデルを構築し、<strong>P(swing | pitch)</strong> と <strong>P(hit | swing, pitch)</strong> を個別に予測した。ここで「pitch」とは投球の完全なプロファイル（位置、球種、球速、回転数、変化量）を意味する。統合指標 <strong>P(hit | pitch) = P(swing | pitch) × P(hit | swing, pitch)</strong> により、各投球の総合的な危険度を定量化した。このモデルを鄭浩均の実際の満塁本塁打の投球に適用し、その配球判断を評価した。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">P(swing | pitch) と P(hit | swing, pitch) を推定するノンパラメトリックアンサンブル</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">P(swing | pitch) と P(hit | swing, pitch) を推定する勾配ブースティング</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">特徴量の重要度と個別投球の解釈</p>
  </div>
</div>

### 大谷翔平の打撃プロファイル：P(swing | loc)、P(hit | swing, loc)、P(hit | loc)（2025年 MLBシーズン）

<img src="/images/jpn_ohtani_kde_heatmap.png" alt="大谷翔平 KDE ヒートマップ" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">大谷翔平の2025年 MLB打撃データに基づくカーネル平滑化による確率推定値。<em>投球位置のみ</em>を条件変数としている。各行は球種カテゴリ（全球種、ファストボール、変化球、緩急系）、各列は確率の構成要素を表す。<strong>左：P(swing | loc)</strong>——大谷翔平がスイングする確率。<strong>中央：P(hit | swing, loc)</strong>——スイングした場合に安打になる確率。<strong>右：P(hit | loc)</strong>——各位置の総合的な危険度。赤い十字は鄭浩均が投じた満塁本塁打のカーブ位置（pX=−0.46, pZ=2.16）を示す。</p>

<div style="background: #eff6ff; border: 2px solid #2563eb; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #1e3a5f; margin-top: 0;">KDEから読み取れる鄭浩均のカーブの位置評価</h4>
  <p style="line-height: 1.7;"><strong>変化球の行</strong>（第3行）を見ると、あの満塁本塁打のカーブは <strong>P(swing | loc) が中程度</strong>、<strong>P(hit | swing, loc) が比較的低い</strong>ゾーンに着弾している。この位置における P(hit | loc) はホットゾーンには該当しない——つまり、鄭浩均は妥当な位置に投げていた。変化球の高危険ゾーンはインコース中央付近と高めに集中しているが、鄭浩均のカーブはそこからやや外れた場所に投じられていた。</p>
</div>

### 満塁本塁打の投球：モデルによる評価

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">上記のKDEヒートマップは投球位置のみを条件としている。あの<em>特定の1球</em>を評価するには、投球の完全なプロファイル——位置、球速、回転数、変化量、カウント——をRFモデルとGBMモデルに入力する必要がある。</p>

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
  <h4 style="color: #92400e; margin-top: 0;">位置だけでなく、投球の質がこの球を「良い球」にした理由</h4>
  <p style="line-height: 1.7; margin-bottom: 12px;">SHAP分析により、投球位置以外で P(hit | swing, pitch) を低く抑えた要因が明らかになった。</p>
  <ul style="line-height: 2;">
    <li><strong>回転数（2,483 rpm）</strong>——P(hit | swing, pitch) を下げる最大の要因。高い回転数がより鋭く遅いタイミングでの変化を生み、芯で捉えることを困難にする。</li>
    <li><strong>縦の変化量（pfx_z = −7.09 in.）</strong>——強い落差によりバットがボールの軌道の下を通り、弱い打球や空振りを誘発する。</li>
    <li><strong>球速（76.8 mph）</strong>——鄭浩均のフォーシームとの20 mph以上の球速差が大谷翔平のタイミングを狂わせる。</li>
    <li><strong>回転軸（45°）</strong>——落下とシュート方向の変化が組み合わさり、軌道に欺瞞性が生まれる。</li>
  </ul>
  <p style="line-height: 1.7; margin-bottom: 0;">この球はゾーン内にあったため P(swing | pitch) は高まったが、上記の投球特性により P(hit | swing, pitch) はわずか約13%に抑えられた——これは大谷翔平のスイング時の全体的な被安打率を大きく下回る。<strong>紛れもなく良い投球であった。</strong></p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit | pitch) ≈ 9%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">スイング確率とコンタクトの質を総合すると、このカーブの<strong>安打確率はわずか約9%</strong>であった。回転、変化、球速差のすべてが P(hit | pitch) を抑制しており、91%の確率で打ち取れる計算になる。十分に合理的な勝負であった。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">鄭浩均は勇気ある勝負を選んだ</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">満塁の場面で、鄭浩均は<strong>真っ向勝負を選択した</strong>。2025年ワールドシリーズで同様の場面で大谷翔平を敬遠したブルージェイズとは対照的である。モデルの分析結果は、この判断が勇敢であると同時に統計的にも合理的であったことを裏付けている。</p>
  </div>
</div>

### 最適配球戦略：鄭浩均はどこを狙うべきだったか？

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">鄭浩均のあのカーブは P(hit | pitch) ≈ 9% と、すでに低い値であった。しかし、さらに低く抑えることは可能だったのか。KDEヒートマップは位置のみを条件としており、モデルの評価は<em>あの1球</em>に限定されている。戦略上の問いに答えるには、鄭浩均の投球プロファイル（各球種の平均球速・回転数・変化量）を固定したまま<strong>投球位置</strong>を変化させる必要がある。これにより、鄭浩均の4球種それぞれについて P(hit | Cheng's profile, loc) の実用的なマップが得られる。</p>

<img src="/images/jpn_ohtani_pitch_strategy_decomp.png" alt="配球戦略の分解——鄭浩均 vs 大谷翔平" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">GBMとRFのアンサンブル平均。<strong>鄭浩均の各球種の平均投球プロファイル</strong>でカウント2-1を条件としている。各行は鄭浩均の4球種（フォーシーム、カーブ、チェンジアップ、スライダー）に対応する。<strong>左：P(swing | Cheng's profile, loc)</strong>——鄭浩均の球に対する大谷翔平のスイング確率。<strong>中央：P(hit | swing, Cheng's profile, loc)</strong>——コンタクトが最も危険な位置。<strong>右：P(hit | Cheng's profile, loc)</strong>——総合危険度。赤い十字は実際にカーブを投じた位置、青い星は各球種の最適位置（P(hit)が最小となる位置）を示す。注目すべき点として、P(hit | swing) が高くても P(swing) が低いゾーン（例：低め外角）は、打たれた場合の危険性は高いものの、そもそもスイングされにくいため戦略的には安全である。</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">モデルの推奨（青い星 = 最適位置）</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">フォーシーム</span><br><span style="color: #aaa;">低め外角 — P(hit | Cheng's FF, loc*) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">チェンジアップ</span><br><span style="color: #aaa;">低め内角 — P(hit | Cheng's CH, loc*) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">カーブ</span><br><span style="color: #aaa;">最適位置 — P(hit | Cheng's CU, loc*) = 4.8%</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">loc* = 青い星（最適位置）。赤い十字 = 実際の投球位置（P(hit | pitch) ≈ 9%）。すべての値は鄭浩均の球種別平均プロファイルで条件付けしている。カーブを最適位置に投げたとしても（4.8%）、低め外角フォーシーム（3.6%）や低め内角チェンジアップ（4.1%）のほうがより安全な選択であった。</p>
</div>

---

## 結論

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>鄭浩均のカウント管理こそが真の問題であった</strong>——繰り返しカウントで後手に回り、大谷翔平の打席前に満塁の状況を招いた。崩壊は1球のミスではなく、パターンの積み重ねによるものであった。</li>
    <li><strong>あの満塁本塁打の球は悪い投球ではなかった</strong>——RF/GBMモデルによれば P(swing | pitch) ≈ 71%、P(hit | swing, pitch) ≈ 13%、P(hit | pitch) ≈ 9% であった。高回転数（2,483 rpm）、大きな縦変化（−7.09 in.）、20 mph以上の球速差がいずれもヒット確率を大谷翔平の平均値より大幅に抑えていた。鄭浩均は敬遠ではなく勝負を選ぶ勇気を見せた。</li>
    <li><strong>改善の余地は存在した</strong>——鄭浩均自身の投球プロファイルで条件付けすると、カーブの最適位置（青い星）であれば P(hit) を9%から4.8%に下げられた。ただし、低め外角フォーシーム（3.6%）や低め内角チェンジアップ（4.1%）のほうがさらに安全な選択肢であった。</li>
    <li><strong>鄭浩均の降板後も失点は続いた</strong>——胡と沙で合計5自責点を記録しており、これがチーム全体の守備崩壊であって一人の投手の失敗ではなかったことを物語っている。</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  野球は確率のスポーツである。P(hit | pitch) ≈ 9%——高回転、鋭い変化、20 mphの球速差によって打たれにくくなっていた投球——が満塁本塁打となり、ひとつの「物語」が生まれた。しかしデータが語るのは、より複雑な真実である。カウント管理という構造的な問題、勇敢な配球判断、そしてこのスポーツを美しくも残酷にするランダム性。それらが交差した結果が、あの2回だったのだ。
</div>
