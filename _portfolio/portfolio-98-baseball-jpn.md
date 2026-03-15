---
title: "Baseball Analytics: Dissecting the 2nd Inning Meltdown — Taiwan vs. Japan, WBC 2026"
excerpt: "Was Cheng really to blame for the 10-run disaster? Using pitch-level data, Random Forest, and GBM models trained on Ohtani's 2025 MLB season, we decompose the damage and propose an optimal pitching strategy.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #1a0a0a 0%, #4a1a1a 50%, #8b0000 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #ff6b6b; margin-top: 0; font-size: 1.6em;">WBC 2026 Pool C: Taiwan vs. Japan (Mar 9, 2026)</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    Japan scored <strong style="color: #ff6b6b;">10 runs in the 2nd inning</strong> — a devastating single-inning collapse. Starter <strong>Hao-Chun Cheng</strong> was pulled after 1.2 IP with 8 ER, and the narrative quickly blamed him for the disaster. But was that fair? I used pitch-level data and machine learning models to find out.
  </p>
</div>

## Two Questions

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 280px; background: #fff3f3; border-left: 5px solid #dc2626; padding: 20px; border-radius: 8px;">
    <h3 style="color: #dc2626; margin-top: 0;">Q1: Was it really Cheng's fault?</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">Did the starter single-handedly cause the meltdown, or did the damage stem from a systemic problem that carried across all three pitchers in the inning?</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #eff6ff; border-left: 5px solid #2563eb; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2563eb; margin-top: 0;">Q2: Could Cheng have done better vs. Ohtani?</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">On the fateful 2-1 count with bases loaded, Cheng threw a curveball that Ohtani crushed for a grand slam. Was there a smarter pitch choice?</p>
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
  <p style="line-height: 1.7;">Cheng repeatedly fell behind in the count, putting himself in hitter-friendly situations. By the time Ohtani stepped up, the bases were already loaded — not because of one bad pitch, but because of a <strong>pattern of lost count battles</strong> against the previous batters. The damage was set up before Ohtani even entered the box.</p>
</div>

### All Three Pitchers Suffered

<img src="/images/jpn_damage_pitch_map.png" alt="Damage Pitch Locations by Pitcher" style="width: 100%; max-width: 1000px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Red stars mark run-scoring pitches for all three pitchers: Cheng (1.2 IP, 8 ER), Hu (0.1 IP, 2 ER), and Sha (2.0 IP, 3 ER). The bleeding continued long after Cheng was pulled — this was not a one-man problem.</p>

### Cheng's Pitch Arsenal

<img src="/images/jpn_cheng_pitch_location.png" alt="Cheng Pitch Locations by Type" style="width: 100%; max-width: 600px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Cheng's 54 pitches broken down by type: Changeup (11), Curveball (7), Four-Seam Fastball (29), Slider (7). His fastball command was inconsistent, with many pitches drifting to the middle of the zone.</p>

---

## Part 2: The Grand Slam — Could Cheng Have Done Better?

<div style="background: linear-gradient(135deg, #0f172a 0%, #1e3a5f 100%); padding: 25px; border-radius: 12px; margin: 25px 0; color: #e0e0e0;">
  <h3 style="color: #93c5fd; margin-top: 0; font-size: 1.3em;">Modeling Ohtani's Hit Probability</h3>
  <p style="font-size: 1.05em; line-height: 1.7; color: #f5f5f5;">
    Using Ohtani's complete <strong>2025 MLB season data</strong>, I trained <strong>Random Forest</strong> and <strong>Gradient Boosting Machine</strong> models to separately predict <strong>P(swing)</strong> and <strong>P(hit|swing)</strong> as functions of pitch location, type, speed, spin rate, and movement. The combined metric <strong>P(hit) = P(swing) × P(hit|swing)</strong> gives the overall danger of each pitch. The models were then applied to Cheng's actual grand slam pitch to evaluate the decision.
  </p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">Random Forest</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Non-parametric ensemble for P(swing) and P(hit|swing) separately</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">GBM</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Gradient boosting for P(swing) and P(hit|swing) separately</p>
  </div>
  <div style="flex: 1; min-width: 200px; background: #eff6ff; border: 2px solid #2563eb; padding: 15px; border-radius: 10px; text-align: center;">
    <strong style="color: #1e3a5f; font-size: 1.05em;">SHAP Analysis</strong>
    <p style="margin: 8px 0 0; font-size: 0.9em; color: #666;">Feature importance & pitch-level explanation</p>
  </div>
</div>

### Ohtani's Hitting Profile: P(swing), P(hit|swing), P(hit) (2025 MLB Season)

<img src="/images/jpn_ohtani_kde_heatmap.png" alt="Ohtani KDE Heatmaps — P(swing), P(hit|swing), P(hit) by Pitch Type" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Kernel-smoothed rate estimates based on Ohtani's 2025 MLB batting data, conditioned on <em>location only</em>. Each row is a pitch category (Overall, Fastball, Breaking, Offspeed); each column is a probability component. <strong>Left: P(swing | loc)</strong> — where Ohtani offers. <strong>Middle: P(hit | swing, loc)</strong> — where contact is dangerous given a swing. <strong>Right: P(hit | loc)</strong> — the combined danger at each location. The red star marks Cheng's grand slam curveball (pX=−0.46, pZ=2.16).</p>

<div style="background: #eff6ff; border: 2px solid #2563eb; padding: 20px; border-radius: 10px; margin: 20px 0;">
  <h4 style="color: #1e3a5f; margin-top: 0;">What the KDE tells us about Cheng's curveball location</h4>
  <p style="line-height: 1.7;">Looking at the <strong>Breaking ball row</strong> (3rd row), the grand slam curveball landed in a zone with <strong>moderate P(swing | loc)</strong> and <strong>relatively low P(hit | swing, loc)</strong>. The combined P(hit | loc) at this location is not in a hot zone — Cheng placed the pitch in a reasonable location. The high-danger zones for breaking balls concentrate in the middle-inside region and up in the zone; Cheng's curveball was slightly away from these.</p>
</div>

### The Grand Slam Pitch: Model Verdict

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">The KDE heatmaps above are conditioned on location only. To evaluate the <em>specific</em> grand slam pitch, we feed its full pitching profile — location, speed, spin rate, movement, and count — into the RF and GBM models:</p>

<div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
  <div style="flex: 1; min-width: 180px; background: #f0fdf4; border: 2px solid #059669; padding: 18px; border-radius: 10px; text-align: center;">
    <p style="color: #059669; font-weight: bold; font-size: 1.1em; margin: 0;">P(swing)</p>
    <p style="font-size: 1.8em; font-weight: bold; margin: 8px 0 4px; color: #1a1a2e;">~71%</p>
    <p style="font-size: 0.8em; color: #666; margin: 0;">GBM: 74.8% · RF: 67.5%</p>
  </div>
  <div style="flex: 0 0 30px; display: flex; align-items: center; justify-content: center; font-size: 1.5em; color: #999;">×</div>
  <div style="flex: 1; min-width: 180px; background: #f0fdf4; border: 2px solid #059669; padding: 18px; border-radius: 10px; text-align: center;">
    <p style="color: #059669; font-weight: bold; font-size: 1.1em; margin: 0;">P(hit|swing)</p>
    <p style="font-size: 1.8em; font-weight: bold; margin: 8px 0 4px; color: #1a1a2e;">~13%</p>
    <p style="font-size: 0.8em; color: #666; margin: 0;">GBM: 12.5% · RF: 14.0%</p>
  </div>
  <div style="flex: 0 0 30px; display: flex; align-items: center; justify-content: center; font-size: 1.5em; color: #999;">=</div>
  <div style="flex: 1; min-width: 180px; background: #ecfdf5; border: 2px solid #047857; padding: 18px; border-radius: 10px; text-align: center;">
    <p style="color: #047857; font-weight: bold; font-size: 1.1em; margin: 0;">P(hit)</p>
    <p style="font-size: 1.8em; font-weight: bold; margin: 8px 0 4px; color: #047857;">~9%</p>
    <p style="font-size: 0.8em; color: #666; margin: 0;">GBM: 9.4% · RF: 9.5%</p>
  </div>
</div>

<div style="background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px; margin: 20px 0;">
  <h4 style="color: #92400e; margin-top: 0;">Why pitch qualities — not just location — made this a good pitch</h4>
  <p style="line-height: 1.7; margin-bottom: 12px;">SHAP analysis reveals the features that suppressed P(hit|swing) beyond location alone:</p>
  <ul style="line-height: 2;">
    <li><strong>Spin rate (2,483 rpm)</strong> — the #1 factor reducing P(hit|swing). High spin creates sharper, later break that is harder to square up cleanly.</li>
    <li><strong>Vertical break (pfx_z = −7.09 in.)</strong> — strong downward movement forces the barrel below the ball's trajectory, inducing weak contact or whiffs.</li>
    <li><strong>Speed (76.8 mph)</strong> — a 20+ mph differential from Cheng's fastball disrupts Ohtani's swing timing.</li>
    <li><strong>Spin axis (45°)</strong> — creates a combination of drop and arm-side fade that makes the pitch's movement deceptive.</li>
  </ul>
  <p style="line-height: 1.7; margin-bottom: 0;">Even though the pitch was in the zone (which increases P(swing)), these qualities kept P(hit|swing) at just ~13% — well below Ohtani's overall batting average on swings. <strong>It was genuinely a good pitch.</strong></p>
</div>

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit) ≈ 9%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">Combining swing likelihood and contact quality, this curveball had only a <strong>~9% chance of becoming a hit</strong>. The pitch's spin, break, and speed differential all worked to suppress the damage probability — a 91% survival rate is a defensible gamble.</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">Cheng Chose Courage</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">With bases loaded, Cheng chose to <strong>compete head-on</strong> — unlike the Blue Jays in the 2025 World Series, who intentionally walked Ohtani in similar situations. The models confirm this was a brave and statistically reasonable call.</p>
  </div>
</div>

### Optimal Pitching Strategy: Where Should Cheng Have Aimed?

<p style="color: #666; font-size: 0.95em; margin-bottom: 5px;">We established that Cheng's grand slam curveball had P(hit) ≈ 9% — already low. But could he have done even better? The KDE heatmaps above condition on location only; the model verdict conditions on <em>one specific pitch</em>. To answer the strategy question, we need to vary <strong>location</strong> while holding Cheng's pitching profile fixed — using his average speed, spin, and movement for each pitch type. This gives an actionable map: for each of Cheng's four pitch types, where should he have targeted?</p>

<img src="/images/jpn_ohtani_pitch_strategy_decomp.png" alt="Pitch Strategy Decomposition — Cheng vs Ohtani, conditioned on Cheng's profile" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">GBM & RF ensemble average, conditioned on <strong>Cheng's average pitch profile</strong> for each pitch type on a 2-1 count. Each row is one of Cheng's four pitches (Four-Seam Fastball, Curveball, Changeup, Slider). <strong>Left: P(swing | Cheng's profile, loc)</strong> — where Ohtani would offer against Cheng's pitches. <strong>Middle: P(hit | swing, Cheng's profile, loc)</strong> — where contact is most dangerous. <strong>Right: P(hit | Cheng's profile, loc)</strong> — the combined danger metric. The white square marks where Cheng actually threw the grand slam curveball; the blue square marks the optimal (lowest P(hit)) location for each pitch type. Key insight: some zones have high P(hit | swing) but low P(swing) (e.g., low-outside), making them strategically safe despite contact danger.</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">Model Recommendation</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Changeup</span><br><span style="color: #aaa;">Low & inside — P(hit) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Fastball</span><br><span style="color: #aaa;">Low & away — P(hit) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #fca5a5;">Curveball</span><br><span style="color: #aaa;">Cheng's choice — P(hit) = 4.8%*</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">*Optimal curveball location at Cheng's average curveball profile. Cheng's actual curveball had P(hit) ≈ 9% — already low, but a better-located curveball could reach 4.8%. A low-and-away fastball (3.6%) or low-inside changeup (4.1%) with Cheng's typical profiles would have been the statistically safest options.</p>
</div>

---

## Conclusions

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>Cheng's count control was the real problem</strong> — he repeatedly fell behind batters, loading the bases before Ohtani's at-bat. The meltdown was set up by a pattern, not a single pitch.</li>
    <li><strong>The grand slam pitch was not a bad pitch</strong> — with P(swing) ≈ 71%, P(hit|swing) ≈ 13%, and P(hit) ≈ 9%, the curveball had low overall danger. Its high spin rate (2,483 rpm), strong vertical break (−7.09 in.), and speed differential all suppressed hit probability. Cheng showed courage competing against Ohtani rather than issuing an intentional walk.</li>
    <li><strong>There was room for improvement</strong> — conditioned on Cheng's own pitch profiles, the models suggest a low-and-away fastball (P(hit) = 3.6%) or low-inside changeup (P(hit) = 4.1%) would have been safer than the curveball location he chose (9% actual vs. 4.8% at the optimal curveball spot).</li>
    <li><strong>The damage continued after Cheng</strong> — Hu and Sha combined for 5 more ER, proving this was a team-wide defensive collapse, not one pitcher's failure.</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  Baseball is a game of probabilities. A pitch with 9% P(hit) — suppressed by elite spin, sharp break, and a 20 mph speed differential — becomes a grand slam, and a narrative is born. But the data tells a more nuanced story — one of systemic count management issues, a courageous pitching decision, and the cruel randomness that makes this sport beautiful.
</div>
