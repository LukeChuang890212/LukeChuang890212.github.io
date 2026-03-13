---
title: "野球分析：2026 WBC 台湾対オーストラリア戦 審判ストライクゾーン偏向"
permalink: /ja/portfolio/baseball-aus/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <a href="/zh/portfolio/">中文</a> | <strong>日本語</strong></div>

<div style="background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #e94560; margin-top: 0; font-size: 1.6em;">2026 WBC プールC：台湾 @ オーストラリア（2026年3月5日）</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    球審のストライクゾーンは公平だったのか？投球データと Kernel Density Estimation を用いて、<strong>Omar Peralta の各半イニングにおける実質的ストライクゾーン</strong>を再構築し、2026 WBC の印象深い一戦における審判の偏向を定量化した。
  </p>
</div>

## 研究課題

野球において、ルールブック上のストライクゾーンは明確に定義されている。しかし、球審が実際にコールする*ストライクゾーン*は投球ごとに変動し得る。チームが判定の不一致を疑うとき、データがその答えを示す。2026 WBC プールCにおける台湾対オーストラリアの劇的な一戦の後、**両チームに対するストライクゾーンの判定は一貫していたのか？**を検証した。

## データソースとクリーニング

- **投球レベルデータ**：台豪戦における全判定球（ストライクとボール、スイングを除く）の球位座標データ（水平・垂直座標、フィート単位、捕手視点）。
- 計 **142 球の判定球**を分析：台湾打撃時 75 球、オーストラリア打撃時 67 球。
- 各投球を判定ストライクまたは判定ボールとしてラベル付けし、ルールブック上のストライクゾーン境界と照合した。

## 手法

- **2次元 Kernel Density Estimation（KDE）**：判定ストライクの位置に Gaussian KDE を適用し、各チーム打撃時における球審の実質的ストライクゾーン等高線を個別に推定。
- **精度分類**：各判定球を4種類に分類——正確ストライク、正確ボール、寛大ストライク（ゾーン外をストライク判定）、誤判ボール（ゾーン内をボール判定）。
- **ストライクゾーン差分マップ**：差分ヒートマップ（台湾ゾーン確率 − オーストラリアゾーン確率）を算出し、空間的偏向を可視化。
- **等高線比較**：各チームの 50% 確率等高線をルールブックゾーンに重ね合わせ、形状とサイズの差異を明示。

## 主要な発見

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #fff3f3; border-left: 5px solid #e94560; padding: 20px; border-radius: 8px;">
    <h3 style="color: #e94560; margin-top: 0;">台湾打撃時</h3>
    <p style="font-size: 2em; font-weight: bold; color: #e94560; margin: 5px 0;">77% 精度</p>
    <p>球審のストライクゾーンは<strong>大幅に拡大</strong>され、ほぼ全方向に膨張していた。ゾーンの形状はあまりに不規則で、オーストラリアの地図のようであった。<strong>全誤判の約3分の2が台湾に不利</strong>であった。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f0f7ff; border-left: 5px solid #3498db; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3498db; margin-top: 0;">オーストラリア打撃時</h3>
    <p style="font-size: 2em; font-weight: bold; color: #3498db; margin: 5px 0;">87% 精度</p>
    <p>ゾーンは<strong>平坦で狭い長方形</strong>に縮小した。低めの投球はほぼ全てボール判定となり、台湾の投手は高めに投げざるを得なくなった——結果として高めゾーンで強い打球を浴びるリスクが増大した。</p>
  </div>
</div>

## 可視化分析

### 球審の実質的ストライクゾーン vs. ルールブックゾーン

<img src="/images/strike_zone_accuracy.png" alt="ストライクゾーン精度比較" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">KDE推定ストライクゾーン（陰影等高線）とルールブックゾーン（破線矩形）の比較。台湾打撃時（左）、ゾーンはルールブック境界を大きく超えて拡大。オーストラリア打撃時（右）、ゾーンは縮小——特に下端で顕著。</p>

### ストライクゾーン差分マップ

<img src="/images/strike_zone_diff.png" alt="ストライクゾーン差分マップ" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>赤 = 台湾打撃時のストライク確率が高い；青 = オーストラリア打撃時のストライク確率が高い。</strong>赤い領域が圧倒的に優勢であり、台湾打撃時の実質的ストライクゾーンがほぼ全ての位置で著しく大きかったことを裏付けている。</p>

## 結果と考察

| 指標 | 台湾打撃 | オーストラリア打撃 |
|--------|:-:|:-:|
| 判定球数 | 75 | 67 |
| 精度 | **58/75 (77%)** | **58/67 (87%)** |
| 寛大ストライク（ゾーン外をストライク判定） | 14 | 5 |
| 誤判ボール（ゾーン内をボール判定） | 3 | 4 |
| 際どい判定 | 5 | 5 |

データは明確な事実を示している。台湾打撃時、球審のゾーンは外側に膨張し、明らかにプレート外の投球をストライクと判定していた。77% の精度はプロ水準として著しく低い。最も重要なのは、誤判が**非対称的**であったことだ：台湾打撃時、寛大ストライク（打者に不利な誤判）と誤判ボールの比率はほぼ 5:1 であった。

オーストラリア打撃時、ゾーンは劇的に引き締められた。下端は実質的に消失し、台湾打者に対してはストライクと判定されていた低めの投球が、ここではほぼ全てボールと判定された。これにより台湾の投手は高めに投げざるを得なくなり、強打を浴びるリスクが増大した。

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  忘れられない試合を記念して。数字は嘘をつかない——しかしストライクゾーンは確かに嘘をついた。
</div>
