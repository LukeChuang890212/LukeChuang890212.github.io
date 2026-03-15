---
title: "野球分析：2026 WBC 台湾対オーストラリア戦 審判のストライクゾーン偏向"
permalink: /ja/portfolio/baseball-aus/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #e94560; margin-top: 0; font-size: 1.6em;">2026 WBC プールC：台湾 @ オーストラリア（2026年3月5日）</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    球審の判定は公平だったのか。投球データと Kernel Density Estimation を用いて、<strong>球審 Omar Peralta のハーフイニングごとの実質的ストライクゾーン</strong>を再構築し、2026 WBC 屈指の名勝負における判定の偏りを定量的に検証した。
  </p>
</div>

## 問題設定

野球におけるルールブック上のストライクゾーンは明確に定義されている。しかし、球審が実際にコールする「ストライクゾーン」は投球ごとに変動しうる。チームが判定の不一致を感じたとき、その答えを示せるのはデータである。2026 WBC プールC、台湾対オーストラリアの劇的な一戦の後、**両チームに対するストライクゾーンの判定は一貫していたのか？**という問いを検証した。

## データと前処理

- **投球レベルデータ**：台豪戦における全判定球（ストライク・ボールのコール。スイングした投球は除外）の着弾位置データ（水平・垂直座標、フィート単位、捕手視点）。
- 計 **142 球の判定球**を分析対象とした：台湾打撃時 75 球、オーストラリア打撃時 67 球。
- 各投球を「判定ストライク」または「判定ボール」に分類し、ルールブック上のストライクゾーン境界と照合した。

## 分析手法

- **2次元 Kernel Density Estimation（KDE）**：判定ストライクの位置に Gaussian KDE を適用し、各チームの打撃時における球審の実質的ストライクゾーン等高線を個別に推定した。
- **判定分類**：各コールを4種類に分類した——正判定ストライク、正判定ボール、拡大ストライク（ゾーン外をストライクとコール）、見逃しボール（ゾーン内をボールとコール）。
- **ストライクゾーン差分マップ**：差分ヒートマップ（台湾打撃時のゾーン確率 − オーストラリア打撃時のゾーン確率）を算出し、空間的な偏りを可視化した。
- **等高線比較**：各チームの 50% 確率等高線をルールブックゾーンに重ね合わせ、形状・サイズの差異を明示した。

## 主要な発見

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #fff3f3; border-left: 5px solid #e94560; padding: 20px; border-radius: 8px;">
    <h3 style="color: #e94560; margin-top: 0;">台湾打撃時</h3>
    <p style="font-size: 2em; font-weight: bold; color: #e94560; margin: 5px 0;">正判定率 77%</p>
    <p>球審のストライクゾーンは<strong>大幅に拡大</strong>され、ほぼ全方向に膨張していた。その形状はあまりに不規則で、まるでオーストラリア大陸の地図のようであった。<strong>全誤判の約3分の2が台湾に不利な方向</strong>に偏っていた。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f0f7ff; border-left: 5px solid #3498db; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3498db; margin-top: 0;">オーストラリア打撃時</h3>
    <p style="font-size: 2em; font-weight: bold; color: #3498db; margin: 5px 0;">正判定率 87%</p>
    <p>ゾーンは<strong>平坦で狭い長方形</strong>に縮小した。低めの投球はほぼ例外なくボール判定となり、台湾の投手は高めに投げざるを得なくなった。その結果、高めのゾーンで痛打を浴びるリスクが増大した。</p>
  </div>
</div>

## 可視化

### 球審の実質的ストライクゾーン vs. ルールブックゾーン

<img src="/images/strike_zone_accuracy.png" alt="ストライクゾーン正判定率比較" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">KDE推定ストライクゾーン（陰影等高線）とルールブックゾーン（破線矩形）の比較。台湾打撃時（左）はゾーンがルールブック境界を大きく超えて拡大している。オーストラリア打撃時（右）はゾーンが縮小しており、特に下端で顕著である。</p>

### ストライクゾーン差分マップ

<img src="/images/strike_zone_diff.png" alt="ストライクゾーン差分マップ" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>赤 = 台湾打撃時にストライク確率が高い領域、青 = オーストラリア打撃時にストライク確率が高い領域。</strong>赤い領域が圧倒的に広く、台湾打撃時の実質的ストライクゾーンがほぼ全域で著しく大きかったことを裏付けている。</p>

## 結果と考察

| 指標 | 台湾打撃時 | オーストラリア打撃時 |
|--------|:-:|:-:|
| 判定球数 | 75 | 67 |
| 正判定率 | **58/75 (77%)** | **58/67 (87%)** |
| 拡大ストライク（ゾーン外をストライクとコール） | 14 | 5 |
| 見逃しボール（ゾーン内をボールとコール） | 3 | 4 |
| 際どい判定 | 5 | 5 |

データは明確な事実を物語っている。台湾の打撃時、球審のゾーンは外側へ膨張し、プレートから明らかに外れた投球までストライクとコールしていた。77% という正判定率はプロの水準として著しく低い。最も重要な点は、誤判が**非対称的**であったことだ。台湾打撃時、拡大ストライク（打者に不利な誤判）と見逃しボールの比率はほぼ 5:1 であった。

オーストラリアの打撃時には、ゾーンは劇的に引き締められた。下端は実質的に消滅し、台湾打者に対してはストライクとコールされていた低めの投球が、ここではほぼすべてボールと判定された。これにより台湾の投手は高めへの投球を強いられ、痛打を浴びるリスクが高まった。

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  忘れられない試合を記念して。数字は嘘をつかない——しかしストライクゾーンは確かに嘘をついた。
</div>
