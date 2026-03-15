---
title: "棒球分析：2026 WBC 台日戰第二局崩盤解析"
permalink: /zh/portfolio/baseball-jpn/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #1a0a0a 0%, #4a1a1a 50%, #8b0000 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ff6b6b; margin-top: 0; font-size: 1.6em;">2026 WBC C組：台灣 vs. 日本（2026年3月9日）</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    日本在第二局攻下 <strong style="color: #ff6b6b;">10 分</strong>——一場毀滅性的單局崩盤。先發投手<strong>鄭浩均（Cheng）</strong>在投 1.2 局後以 8 分責失退場，輿論迅速將責任歸咎於他。但這公平嗎？我利用逐球數據與機器學習模型進行深入分析。
  </p>
</div>

## 兩個問題

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 280px; background: #fff3f3; border-left: 5px solid #dc2626; padding: 20px; border-radius: 8px;">
    <h3 style="color: #dc2626; margin-top: 0;">Q1：真的是鄭浩均的錯嗎？</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">先發投手是否獨力導致了崩盤，還是這場災難源於貫穿該局三位投手的系統性問題？</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #2563eb; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2563eb; margin-top: 0;">Q2：面對大谷翔平，鄭浩均能做得更好嗎？</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">在滿壘、球數 2-1 的關鍵時刻，鄭浩均投出一顆被大谷轟出滿貫全壘打的曲球。是否有更聰明的配球選擇？</p>
  </div>
</div>

---

## 第一部分：崩盤診斷

### 第二局逐球解析

<img src="/images/jpn_inning2_progression.png" alt="第二局打席進程" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">每個點代表第二局的一顆球。Y 軸追蹤球數優勢（壞球數 - 好球數）：大於零表示打者領先球數。紅色星號標記得分安打。注意鄭浩均在關鍵球<strong>之前</strong>多次讓打者取得球數優勢。</p>

### 根本原因：球數控制

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <p style="color: #ff6b6b; font-size: 1.3em; font-weight: bold; margin: 0 0 15px 0; text-align: center;">失分原因分析</p>
  <img src="/images/jpn_damage_analysis.png" alt="球數與配球分析" style="width: 100%; max-width: 1000px; border-radius: 8px; margin: 0 auto; display: block;">
  <p style="color: #ccc; font-size: 0.95em; margin-top: 15px; text-align: center;">左：每顆失分球的球數狀況——紅色（打者有利球數）佔主導。右：整局各球種的失分率。</p>
</div>

<div style="background: #fef2f2; border: 2px solid #dc2626; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #991b1b; margin-top: 0;">關鍵發現：鄭浩均的控球問題為大谷創造了滿壘局面</h4>
  <p style="line-height: 1.7;">鄭浩均反覆落後球數，使自己陷入對打者有利的局面。大谷上場打擊時，壘上已經滿壘——不是因為一顆壞球，而是因為在前面打者的打席中<strong>連續輸掉球數戰</strong>。大谷進入打擊區之前，失分的條件就已經成熟。</p>
</div>

### 三位投手都受創

<img src="/images/jpn_damage_pitch_map.png" alt="各投手失分球位置" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">紅色星號標記三位投手的失分球：鄭浩均（1.2 局，8 分責失）、胡（0.1 局，2 分責失）、沙（2.0 局，3 分責失）。鄭浩均退場後失血仍在持續——這不是一個人的問題。</p>

### 鄭浩均的球種分布

<img src="/images/jpn_cheng_pitch_location.png" alt="鄭浩均各球種位置" style="width: 100%; max-width: 600px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">鄭浩均 54 球的球種分佈：變速球（11）、曲球（7）、四縫線速球（29）、滑球（7）。他的速球控制不穩定，許多球漂向好球帶正中央。</p>

---

## 第二部分：滿貫全壘打——鄭浩均能做得更好嗎？

<div style="background: linear-gradient(135deg, #0f172a 0%, #1e3a5f 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #93c5fd; margin-top: 0; font-size: 1.3em;">大谷翔平安打機率建模</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    使用大谷翔平 <strong>2025 MLB 完整賽季數據</strong>，我訓練了 <strong>Random Forest</strong> 與 <strong>Gradient Boosting Machine（GBM）</strong> 模型，分別預測 <strong>P(swing | pitch)</strong> 與 <strong>P(hit | swing, pitch)</strong>——其中「pitch」代表完整的投球特徵（位置、球種、球速、轉速和球路變化）。合併指標 <strong>P(hit | pitch) = P(swing | pitch) × P(hit | swing, pitch)</strong> 衡量每顆球的整體危險度。模型隨後應用於鄭浩均實際投出的滿貫全壘打球。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">非參數集成模型，分別預測 P(swing | pitch) 與 P(hit | swing, pitch)</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">梯度提升模型，分別預測 P(swing | pitch) 與 P(hit | swing, pitch)</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP 分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">特徵重要性與逐球解釋</p>
  </div>
</div>

### 大谷翔平的打擊輪廓：P(swing | loc)、P(hit | swing, loc)、P(hit | loc)（2025 MLB 賽季）

<img src="/images/jpn_ohtani_kde_heatmap.png" alt="大谷翔平 KDE 熱力圖" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">基於大谷翔平 2025 MLB 打擊數據的 Kernel 平滑估計，僅以<em>位置</em>為條件。每行為一種球種類別（整體、速球、變化球、離速球）；每列為一個機率成分。<strong>左：P(swing | loc)</strong>——大谷在何處揮棒。<strong>中：P(hit | swing, loc)</strong>——揮棒後在何處產生危險。<strong>右：P(hit | loc)</strong>——各位置的綜合危險度。紅色十字標記鄭浩均滿貫全壘打曲球位置（pX=−0.46, pZ=2.16）。</p>

<div style="background: #eff6ff; border: 2px solid #2563eb; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #1e3a5f; margin-top: 0;">KDE 告訴我們什麼</h4>
  <p style="line-height: 1.7;">觀察<strong>變化球列</strong>（第3列），滿貫全壘打曲球落在 <strong>P(swing | loc) 中等</strong>且 <strong>P(hit | swing, loc) 相對較低</strong>的區域。該位置的 P(hit | loc) 並非熱區——鄭浩均將球投在一個合理的位置。變化球的高危險區集中在內角偏中和高位；鄭浩均的曲球略微偏離這些區域。</p>
</div>

### 滿貫全壘打球：模型判定

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">上方 KDE 熱力圖僅以位置為條件。為了評估<em>特定</em>的滿貫全壘打球，我們將其完整投球特徵——位置、球速、轉速、球路變化、球數——輸入 RF 和 GBM 模型：</p>

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
  <h4 style="color: #92400e; margin-top: 0;">為什麼投球品質——不只是位置——讓這是一顆好球</h4>
  <p style="line-height: 1.7; margin-bottom: 12px;">SHAP 分析揭示了在位置之外壓低 P(hit | swing, pitch) 的特徵：</p>
  <ul style="line-height: 2;">
    <li><strong>轉速（2,483 rpm）</strong>——壓低 P(hit | swing, pitch) 的首要因素。高轉速產生更銳利、更晚的變化，更難確實擊中。</li>
    <li><strong>垂直位移（pfx_z = −7.09 in.）</strong>——強烈的下墜使球棒通過球的下方，造成弱擊或揮空。</li>
    <li><strong>球速（76.8 mph）</strong>——與鄭浩均速球相差 20+ mph，打亂大谷的揮棒節奏。</li>
    <li><strong>旋轉軸（45°）</strong>——結合下墜與側向移動，使球路變化具欺騙性。</li>
  </ul>
  <p style="line-height: 1.7; margin-bottom: 0;">儘管球在好球帶內（提高了 P(swing | pitch)），這些品質將 P(hit | swing, pitch) 壓在僅約 13%——遠低於大谷的整體揮棒安打率。<strong>這確實是一顆好球。</strong></p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit | pitch) ≈ 9%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">綜合揮棒可能性與接觸品質，這顆曲球僅有<strong>約 9% 的安打機率</strong>。投球的轉速、變化和速差共同壓低了 P(hit | pitch)——91% 的存活率是一個合理的賭注。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">鄭浩均選擇了勇氣</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">在滿壘的情況下，鄭浩均選擇<strong>正面對決</strong>——不像藍鳥隊在 2025 年世界大賽中類似局面選擇故意四壞保送大谷。模型證實這是一個勇敢且統計上合理的決定。</p>
  </div>
</div>

### 最佳配球策略：鄭浩均該瞄準哪裡？

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">我們已確認鄭浩均的滿貫全壘打曲球 P(hit | pitch) ≈ 9%——已經很低。但能否更好？KDE 熱力圖僅以位置為條件；模型判定以<em>一顆特定球</em>為條件。要回答策略問題，我們需要改變<strong>位置</strong>，同時固定鄭浩均的投球特徵——使用他每種球種的平均球速、轉速和變化量。這給出 P(hit | Cheng's profile, loc) 的可操作地圖：鄭浩均的四種球種各應瞄準哪裡？</p>

<img src="/images/jpn_ohtani_pitch_strategy_decomp.png" alt="配球策略分解——鄭浩均 vs 大谷，以鄭浩均特徵為條件" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">GBM 與 RF 集成平均，以<strong>鄭浩均各球種平均投球特徵</strong>為條件（2-1 球數）。每行為鄭浩均的四種球種之一（四縫線速球、曲球、變速球、滑球）。<strong>左：P(swing | Cheng's profile, loc)</strong>——大谷面對鄭浩均各球種在何處揮棒。<strong>中：P(hit | swing, Cheng's profile, loc)</strong>——揮棒後何處最危險。<strong>右：P(hit | Cheng's profile, loc)</strong>——綜合危險度。紅色十字標記鄭浩均實際投出的滿貫全壘打曲球位置；藍色星號標記各球種的最佳（最低 P(hit)）位置。關鍵發現：某些區域 P(hit | swing, Cheng's profile, loc) 高但 P(swing | Cheng's profile, loc) 低（如外角低球），使其在接觸危險度高的情況下仍然策略性安全。</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">模型建議（藍色星號 = 最佳位置）</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">速球</span><br><span style="color: #aaa;">外角低球 — P(hit | Cheng's FF, loc*) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">變速球</span><br><span style="color: #aaa;">內角低球 — P(hit | Cheng's CH, loc*) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">曲球</span><br><span style="color: #aaa;">最佳位置 — P(hit | Cheng's CU, loc*) = 4.8%</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">loc* = 藍色星號（最佳位置）。紅色十字 = 鄭浩均實際投出位置（P(hit | pitch) ≈ 9%）。所有數值以鄭浩均各球種平均投球特徵為條件。即使曲球投在最佳位置（4.8%），仍比外角低球速球（3.6%）或內角低球變速球（4.1%）風險更高。</p>
</div>

---

## 結論

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>鄭浩均的球數控制才是真正的問題</strong>——他反覆落後球數，在大谷打席前就已經形成滿壘。崩盤是由一個模式造成的，而非單一一球。</li>
    <li><strong>滿貫全壘打球並不是一顆壞球</strong>——RF/GBM 模型給出 P(swing | pitch) ≈ 71%、P(hit | swing, pitch) ≈ 13%、P(hit | pitch) ≈ 9%。曲球的高轉速（2,483 rpm）、強烈垂直位移（−7.09 in.）和 20+ mph 速差有效壓低了安打機率。鄭浩均展現了正面對決大谷的勇氣，而非選擇故意四壞保送。</li>
    <li><strong>仍有改善空間</strong>——以鄭浩均自身的投球特徵為條件，最佳曲球位置（藍色星號）可將 P(hit | Cheng's CU, loc) 從 9% 降至 4.8%。但外角低球速球（3.6%）或內角低球變速球（4.1%）會是更安全的選擇。</li>
    <li><strong>鄭浩均退場後失血持續</strong>——胡和沙合計再丟 5 分責失，證明這是全隊的防守崩潰，而非一位投手的失敗。</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  棒球是一場機率的遊戲。一顆 P(hit | pitch) ≈ 9% 的球——被高轉速、銳利變化和 20 mph 速差所壓制——變成了滿貫全壘打，一個敘事就此誕生。但數據訴說的是一個更細膩的故事——一個關於系統性球數控制問題、一個勇敢的投球決定，以及讓這項運動如此美麗的殘酷隨機性。
</div>
