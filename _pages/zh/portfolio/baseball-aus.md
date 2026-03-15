---
title: "棒球分析：2026 WBC 台澳戰主審好球帶偏差"
permalink: /zh/portfolio/baseball-aus/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #e94560; margin-top: 0; font-size: 1.6em;">2026 WBC C組：台灣 @ 澳洲（2026年3月5日）</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    主審的好球帶真的公平嗎？我透過逐球數據與 Kernel Density Estimation，重建了主審 <strong>Omar Peralta 每半局的實際好球帶</strong>，量化這場 2026 年世界棒球經典賽中令人難忘比賽的判決偏差。
  </p>
</div>

## 研究問題

棒球規則對好球帶有明確定義，但主審實際判定的*好球帶*每顆球都可能不同。當某支球隊懷疑判決標準不一致時，數據最能說明問題。2026 WBC C組台灣對澳洲那場精彩的比賽結束後，我決定用數據回答一個問題：**兩隊面對的好球帶判定標準是否一致？**

## 資料來源與處理

- **逐球數據**：台澳戰中所有判定球（好球與壞球，不含揮棒球）的落點座標（水平與垂直座標，以英尺為單位，從捕手視角）。
- 共分析 **142 顆判定球**：台灣打擊時 75 顆，澳洲打擊時 67 顆。
- 每顆球標記為判定好球或判定壞球，並與規則好球帶邊界進行交叉比對。

## 分析方法

- **二維 Kernel Density Estimation（KDE）**：對判定好球的落點位置套用 Gaussian KDE，分別估計兩隊打擊時主審的實際好球帶輪廓。
- **判決準確度分類**：將每顆判定球歸為四類——正確好球、正確壞球、寬鬆好球（好球帶外被判好球）、錯誤壞球（好球帶內被判壞球）。
- **好球帶差異圖**：計算差異熱力圖（台灣打擊時的好球帶機率減去澳洲打擊時的機率），以視覺化呈現空間偏差。
- **等高線疊合比較**：將兩隊的 50% 機率等高線疊加在規則好球帶上，凸顯形狀與大小的差異。

## 主要發現

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #fff3f3; border-left: 5px solid #e94560; padding: 20px; border-radius: 8px;">
    <h3 style="color: #e94560; margin-top: 0;">台灣打擊時</h3>
    <p style="font-size: 2em; font-weight: bold; color: #e94560; margin: 5px 0;">77% 準確率</p>
    <p>主審的好球帶<strong>大幅膨脹</strong>，幾乎向每個方向擴張，形狀不規則到幾乎像一幅澳洲地圖。<strong>將近三分之二的誤判對台灣不利</strong>。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f0f7ff; border-left: 5px solid #3498db; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3498db; margin-top: 0;">澳洲打擊時</h3>
    <p style="font-size: 2em; font-weight: bold; color: #3498db; margin: 5px 0;">87% 準確率</p>
    <p>好球帶縮成一個<strong>扁平、狹窄的矩形</strong>。低球幾乎一律被判壞球，迫使台灣投手把球路拉高，反而讓自己在高位好球帶更容易被擊中。</p>
  </div>
</div>

## 視覺化分析

### 主審實際好球帶 vs. 規則好球帶

<img src="/images/strike_zone_accuracy.png" alt="好球帶準確度比較" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">KDE 估計的好球帶（陰影等高線）與規則好球帶（虛線矩形）的比較。台灣打擊時（左圖），好球帶明顯超出規則範圍。澳洲打擊時（右圖），好球帶縮小，底部邊緣尤為明顯。</p>

### 好球帶差異圖

<img src="/images/strike_zone_diff.png" alt="好球帶差異圖" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>紅色 = 台灣打擊時好球機率較高；藍色 = 澳洲打擊時好球機率較高。</strong>紅色區域佔絕大多數，印證了台灣打擊時的實際好球帶在幾乎所有位置都明顯更大。</p>

## 結果與解讀

| 指標 | 台灣打擊 | 澳洲打擊 |
|--------|:-:|:-:|
| 判定球數 | 75 | 67 |
| 準確率 | **58/75 (77%)** | **58/67 (87%)** |
| 寬鬆好球（帶外判好球） | 14 | 5 |
| 錯誤壞球（帶內判壞球） | 3 | 4 |
| 邊角球 | 5 | 5 |

數據清楚呈現了事實。台灣打擊時，主審的好球帶向外膨脹，將明顯偏離好球帶的球也判定為好球。77% 的準確率以職業標準來看明顯偏低。最關鍵的是，誤判是**不對稱的**：台灣打擊時，寬鬆好球（對打者不利的誤判）與錯誤壞球的比例接近 5:1。

澳洲打擊時，好球帶急劇收緊。底部邊緣幾乎消失——對台灣打者會被判好球的低球，這時幾乎都被放成壞球。這很可能迫使台灣投手把球路拉高，增加了被強勁擊球的風險。

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  紀念一場難以忘懷的比賽。數字不會說謊——但好球帶確實會。
</div>
