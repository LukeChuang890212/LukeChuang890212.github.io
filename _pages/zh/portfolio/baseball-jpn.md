---
title: "棒球分析：2026 WBC 台日戰第二局崩盤解析"
permalink: /zh/portfolio/baseball-jpn/
layout: single
author_profile: true
---

<div style="text-align: right; margin-bottom: 15px;"><a href="/portfolio/">English</a> | <strong>中文</strong> | <a href="/ja/portfolio/">日本語</a></div>

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
    <h3 style="color: #2563eb; margin-top: 0;">Q2：面對大谷翔平（Ohtani），鄭浩均能做得更好嗎？</h3>
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
    使用大谷翔平 <strong>2025 MLB 完整賽季數據</strong>（1,271 次揮棒，169 支安打），我訓練了 <strong>Random Forest</strong> 與 <strong>Gradient Boosting Machine（GBM）</strong> 模型，預測 P(hit) 作為球位、球種、球速、轉速和球路變化的函數。然後將模型應用於鄭浩均實際投出的滿貫全壘打球，評估這個決策。
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">非參數集成模型，預測 P(swing) 與 P(hit|swing)</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">梯度提升模型，用於安打機率建模</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP 分析</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">特徵重要性與逐球解釋</p>
  </div>
</div>

### 大谷翔平的安打熱區（2025 MLB 賽季）

<img src="/images/jpn_ohtani_hit_heatmap.png" alt="大谷翔平 2025 安打熱力圖" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">大谷翔平 2025 打擊輪廓：安打密度 KDE（左上）、各區間安打率（右上）、揮棒後安打率（左下）、一壘安打 vs. 長打位置（右下）。紅色星號標記鄭浩均滿貫全壘打曲球的位置。</p>

### 滿貫全壘打球：模型判定

<img src="/images/jpn_ohtani_hit_model.png" alt="大谷翔平滿貫全壘打模型分析" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit) = 13.2%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">鄭浩均投出的曲球（76.8 mph，2483 rpm，位於 pX=-0.46, pZ=2.16）根據 RF/GBM 集成模型的<strong>預測安打機率僅約 13%</strong>。從數據角度來看，這並不是一顆壞球。</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">鄭浩均選擇了勇氣</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">在滿壘且一壘有空位（可以保送大谷）的情況下，鄭浩均選擇<strong>正面對決</strong>——不像藍鳥隊在 2025 年世界大賽中類似局面選擇故意四壞保送大谷。這是一個勇敢的決定。</p>
  </div>
</div>

### 什麼因素驅動大谷的安打機率？

<img src="/images/jpn_ohtani_shap.png" alt="大谷安打模型 SHAP 分析" style="width: 100%; max-width: 800px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">SHAP 摘要圖（左上）、滿貫全壘打球的個別分解（右上）、垂直位置與球速的依賴圖（下方）。滿貫全壘打曲球的 SHAP 分解顯示預測 P(hit|swing) 為 12.5%——轉速和進入好球帶略微推高機率，但位置和垂直位移將其壓低。</p>

### 最佳配球策略

<img src="/images/jpn_ohtani_pitch_strategy.png" alt="最佳投球位置策略" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>P(hit) = P(swing) x P(hit|swing)</strong>——GBM 與 RF 的集成平均，限制在好球帶內。藍點標記每種球種的最佳（最低 P(hit)）位置；紅色 X 標記鄭浩均實際投出滿貫全壘打曲球的位置。每種球種都存在預測安打機率更低的位置。</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">模型建議</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">變速球</span><br><span style="color: #aaa;">內角低球 — P(hit) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">速球</span><br><span style="color: #aaa;">外角低球 — P(hit) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #fca5a5;">曲球</span><br><span style="color: #aaa;">鄭浩均的選擇 — P(hit) = 4.8%*</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">*最佳曲球位置，相比鄭浩均實際投出位置的 13.2%。外角低球速球或內角低球變速球是統計上最安全的選擇。</p>
</div>

---

## 結論

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>鄭浩均的球數控制才是真正的問題</strong>——他反覆落後球數，在大谷打席前就已經形成滿壘。崩盤是由一個模式造成的，而非單一一球。</li>
    <li><strong>滿貫全壘打球並不是一顆壞球</strong>——以 13.2% 的預測安打機率而言，曲球是一個合理的選擇。鄭浩均展現了正面對決大谷的勇氣，而非選擇故意四壞保送。</li>
    <li><strong>仍有改善空間</strong>——模型建議外角低球速球（3.6% P(hit)）或內角低球變速球（4.1%）在統計上比鄭浩均選擇的曲球位置更安全。</li>
    <li><strong>鄭浩均退場後失血持續</strong>——胡和沙合計再丟 5 分責失，證明這是全隊的防守崩潰，而非一位投手的失敗。</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  棒球是一場機率的遊戲。13% 的安打機率變成了滿貫全壘打，一個敘事就此誕生。但數據訴說的是一個更細膩的故事——一個關於系統性球數控制問題、一個勇敢的投球決定，以及讓這項運動如此美麗的殘酷隨機性。
</div>
