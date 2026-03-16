---
title: "Baseball Analytics: Dissecting the 2nd Inning Meltdown — Taiwan vs. Japan, WBC 2026"
excerpt: "Was Cheng really to blame for the 10-run disaster? Using pitch-level data, Random Forest, and GBM models trained on Ohtani's 2025 MLB season, we decompose the damage and propose an optimal pitching strategy.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #1a0a0a 0%, #4a1a1a 50%, #8b0000 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ff6b6b; margin-top: 0; font-size: 1.6em;">WBC 2026 Pool C: Taiwan vs. Japan (Mar 9, 2026)</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Japan scored <strong style="color: #ff6b6b;">10 runs in the 2nd inning</strong>, a pivotal half-inning that decided the game. Starter <strong>Hao-Chun Cheng</strong> was pulled after just 1.2 IP with 8 ER, and his performance was widely seen as an area that needed scrutiny. Let's use pitch-level data from that game and machine learning models to objectively examine what happened.
  </p>
</div>

## Two Questions

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 280px; background: #fff3f3; border-left: 5px solid #dc2626; padding: 20px; border-radius: 8px;">
    <h3 style="color: #dc2626; margin-top: 0;">Q1: Did Cheng actually pitch poorly?</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">Was the 2nd-inning meltdown caused by the starter alone? How did the other pitchers perform?</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #2563eb; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2563eb; margin-top: 0;">Q2: Could Cheng have done better when facing Ohtani in the crucial 2nd inning?</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">With bases loaded and a 2-1 count at the critical moment, Cheng threw an outside curveball that Ohtani crushed for a grand slam. Was there a better pitch selection?</p>
  </div>
</div>

---

## Part 1: Diagnosing the Meltdown

### The 2nd Inning, Pitch by Pitch

<img src="/images/jpn_inning2_progression.png" alt="2nd Inning At-Bat Progression" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Each dot is a single pitch in the 2nd inning. The y-axis tracks count leverage (Balls - Strikes): above zero means the hitter is ahead. Red stars mark run-scoring hits. Note how often Cheng let hitters get ahead in the count <strong>before</strong> the damage pitches.</p>

### The Root Cause: Count Control

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 20px 0;">
  <p style="color: #ff6b6b; font-size: 1.3em; font-weight: bold; margin: 0 0 15px 0; text-align: center;">Why the Runs Scored</p>
  <img src="/images/jpn_damage_analysis.png" alt="Count and Pitch Selection Analysis" style="width: 100%; max-width: 1000px; border-radius: 8px; margin: 0 auto; display: block;">
  <p style="color: #ccc; font-size: 0.95em; margin-top: 15px; text-align: center;">Left: The count at each damage pitch — red bars (hitter's count) dominate. Right: Run-scoring rate by pitch type across the entire inning.</p>
</div>

<div style="background: #fef2f2; border: 2px solid #dc2626; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #991b1b; margin-top: 0;">Key Insight: Cheng's control problem loaded the bases for Ohtani</h4>
  <p style="line-height: 1.7;">Cheng repeatedly fell behind in the count, putting himself in hitter-friendly situations over and over. By the time Ohtani stepped up, the bases were already loaded. Unwilling to simply walk Ohtani, the battery chose to challenge him head-on with a curveball near zone 9 in the strike zone — but Ohtani crushed it for a grand slam, resulting in massive damage.</p>
</div>

### All Three Pitchers Suffered

<img src="/images/jpn_damage_pitch_map.png" alt="Damage Pitch Locations by Pitcher" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Red stars mark run-scoring pitches for all three pitchers: Cheng (1.2 IP, 8 ER), Hu (0.1 IP, 2 ER), and Sha (2.0 IP, 3 ER). The bleeding continued long after Cheng was pulled. It appears that aside from the control issues facing the first few batters at the start of the 2nd inning, Cheng's overall pitching quality was not noticeably worse than the relievers who followed him.</p>

### Cheng's Pitch Arsenal

<img src="/images/jpn_cheng_pitch_location.png" alt="Cheng Pitch Locations by Type" style="width: 100%; max-width: 600px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Cheng's 54 pitches broken down by type: Changeup (11), Curveball (7), Four-Seam Fastball (29), Slider (7). He relied heavily on his fastball, but his command was inconsistent, resulting in many balls. Additionally, quite a few pitches drifted toward the center-high area of the zone.</p>

---

## Part 2: The Grand Slam — Could Cheng Have Done Better?

<div style="background: linear-gradient(135deg, #0f172a 0%, #1e3a5f 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #93c5fd; margin-top: 0; font-size: 1.3em;">Modeling Ohtani's Hit Probability</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    Using Ohtani's complete <strong>2025 MLB season data</strong>, I first applied <strong>Kernel Density Estimation (KDE)</strong> to analyze Ohtani's swing patterns against different pitch types, then trained <strong>Random Forest</strong> and <strong>Gradient Boosting Machine (GBM)</strong> models to separately predict <strong>P(swing | pitch)</strong> and <strong>P(hit | swing, pitch)</strong> — where "pitch" denotes the full pitch profile (location, type, speed, spin rate, and movement). Multiplying them gives <strong>P(hit | pitch) = P(swing | pitch) × P(hit | swing, pitch)</strong>, which measures the overall danger of the actual grand slam pitch. Finally, the models are used to propose optimal pitch strategies for that situation.
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Non-parametric ensemble for P(swing | pitch) and P(hit | swing, pitch)</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Gradient boosting for P(swing | pitch) and P(hit | swing, pitch)</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Feature importance & pitch-level explanation</p>
  </div>
</div>

### Ohtani's Hitting Profile: P(swing | loc), P(hit | swing, loc), P(hit | loc) (2025 MLB Season)

<img src="/images/jpn_ohtani_kde_heatmap.png" alt="Ohtani KDE Heatmaps — P(swing), P(hit|swing), P(hit) by Pitch Type" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">KDE-based rate estimates from Ohtani's 2025 MLB batting data — conditioned on <em>location only</em>. Each row is a pitch category, from top to bottom: Overall (all pitch types), Fastball (four-seam, two-seam, cutter, etc.), Breaking (slider, curveball, etc.), Offspeed (changeup, splitter, etc.). Each column is a probability component. <strong>Left: P(swing | loc)</strong> — where Ohtani swings. <strong>Middle: P(hit | swing, loc)</strong> — where contact becomes a hit given a swing. <strong>Right: P(hit | loc)</strong> — the combined danger at each location. The red cross marks Cheng's grand slam curveball (pX=−0.46, pZ=2.16).</p>

<div style="background: #eff6ff; border: 2px solid #2563eb; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #1e3a5f; margin-top: 0;">What the KDE tells us about Cheng's curveball location</h4>
  <p style="line-height: 1.7;">Looking at the <strong>Breaking ball row</strong> (3rd row), the grand slam curveball landed in a zone with <strong>moderate P(swing | loc)</strong> and <strong>relatively low P(hit | swing, loc)</strong>. The combined P(hit | loc) at this location is not in a hot zone — Cheng placed the pitch in a reasonable location. The high-danger zones for breaking balls concentrate in the middle-inside region and up in the zone; Cheng's curveball was slightly away from these.</p>
</div>

### The Grand Slam Pitch: Model Verdict

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">From the KDE analysis, we know that the grand slam pitch — judging by location alone without considering speed, spin rate, or movement — was already a well-placed pitch. Now, to more accurately assess the probability of that grand slam pitch being hit, we feed its full pitch profile — location, speed, spin rate, movement, and count — as predictors into the RF and GBM models:</p>

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
  <h4 style="color: #92400e; margin-top: 0;">Even considering pitch quality, the grand slam pitch was still a very good pitch</h4>
  <p style="line-height: 1.7; margin-bottom: 12px;">SHAP analysis reveals the key factors beyond the outside-low location that suppressed P(hit | swing, pitch):</p>
  <ul style="line-height: 2;">
    <li><strong>Spin rate (2,483 rpm)</strong> — the #1 factor reducing P(hit | swing, pitch). High spin creates sharper, later break that is harder to square up cleanly.</li>
    <li><strong>Vertical break (pfx_z = −7.09 in.)</strong> — strong downward movement forces the barrel below the ball's trajectory, inducing weak contact or whiffs.</li>
    <li><strong>Speed (76.8 mph)</strong> — a 20+ mph differential from Cheng's fastball disrupts Ohtani's swing timing.</li>
    <li><strong>Spin axis (45°)</strong> — creates a combination of drop and arm-side fade that makes the pitch's movement deceptive.</li>
  </ul>
  <p style="line-height: 1.7; margin-bottom: 0;">Even though the pitch was in the zone (which increases P(swing | pitch)), these qualities kept P(hit | swing, pitch) at just ~13% — well below Ohtani's overall batting average on swings. <strong>It was genuinely a good pitch.</strong></p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit | pitch) ≈ 9%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">Combining swing likelihood and contact quality, this curveball had only a <strong>~9% chance of becoming a hit</strong>. The pitch's spin, break, and speed differential all worked to suppress P(hit | pitch) — a 91% survival rate is a defensible gamble.</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">Cheng is a Courageous Pitcher</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">With bases loaded, Cheng chose to <strong>compete head-on</strong> — unlike the Blue Jays in the 2025 World Series, who intentionally walked Ohtani in similar situations. The models confirm this was both a brave and strategically sound decision.</p>
  </div>
</div>

### Optimal Pitching Strategy: Where Should Cheng Have Aimed?

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">We've established that Cheng's grand slam curveball had P(hit | pitch) ≈ 9% — already low. To answer the pitch strategy question, we fix Cheng's pitching profile — using his average speed, spin rate, and movement for each pitch type — and use the models to compute the probability of a swing and a hit after swinging at different <strong>locations</strong> for each pitch type, i.e. P(swing | Cheng's profile, loc) and P(hit | swing, Cheng's profile, loc), to find the better pitching strategies.</p> Given the 2-1 count and the many walks issued earlier, Cheng needed to avoid throwing more balls. Therefore, in the following analysis, we only consider pitching strategies within the strike zone.


<img src="/images/jpn_ohtani_pitch_strategy_decomp.png" alt="Pitch Strategy Decomposition — Cheng vs Ohtani, conditioned on Cheng's profile" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">The figure shows the average predictions from both GBM and RF models, given <strong>Cheng's average pitch profile</strong> for each pitch type, for P(swing | Cheng's profile, loc), P(hit | swing, Cheng's profile, loc), and P(hit | Cheng's profile, loc). Each row corresponds to one of Cheng's four pitch types (Four-Seam Fastball, Curveball, Changeup, Slider); each column corresponds to a different probability. <strong>Left: P(swing | Cheng's profile, loc)</strong> — where Ohtani would swing against Cheng's pitches. <strong>Middle: P(hit | swing, Cheng's profile, loc)</strong> — where contact is most dangerous after a swing. <strong>Right: P(hit | Cheng's profile, loc)</strong> — the combined danger at each location. The red cross marks where Cheng actually threw the grand slam curveball; the blue star marks the optimal (lowest P(hit | Cheng's profile, loc)) location for each pitch type.</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">Model Recommendation (Blue Star = Optimal Location)</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Fastball</span><br><span style="color: #aaa;">Low & away — P(hit | Cheng's FF, loc*) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Changeup</span><br><span style="color: #aaa;">Low & inside — P(hit | Cheng's CH, loc*) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Curveball</span><br><span style="color: #aaa;">Optimal spot — P(hit | Cheng's CU, loc*) = 4.8%</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">loc* = blue star (optimal location).</p>
</div>

---

## Conclusions

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>Falling behind in the count was the main problem</strong> — Cheng repeatedly fell behind batters, creating a bases-loaded situation before Ohtani's at-bat. The meltdown was the cumulative result of a series of count disadvantages.</li>
    <li><strong>But the grand slam pitch was not a bad pitch</strong> — the RF/GBM models give P(swing | pitch) ≈ 71%, P(hit | swing, pitch) ≈ 13%, and P(hit | pitch) ≈ 9%. The curveball's high spin rate (2,483 rpm), strong vertical break (−7.09 in.), and ~20 mph speed differential all effectively suppressed hit probability. Cheng chose to compete head-on rather than issue an intentional walk, showing courage.</li>
    <li><strong>There was still slight room for improvement</strong> — given Cheng's condition on that day, the optimal curveball location (blue star) could have reduced P(hit | Cheng's CU, loc) from 9% to 4.8%. But a low-and-away fastball (3.6%) or low-inside changeup (4.1%) might have been slightly safer options.</li>
    <li><strong>The bleeding continued after Cheng left</strong> — the relievers who followed still gave up earned runs, and Cheng's overall pitching quality was not worse than theirs.</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  Baseball is full of probability battles. A pitch with high spin rate, sharp break, and a 20 mph speed differential — with a hit probability P(hit | pitch) of only about 9% — gets crushed for a grand slam... You can only say that Ohtani is simply that incredible.
</div>
