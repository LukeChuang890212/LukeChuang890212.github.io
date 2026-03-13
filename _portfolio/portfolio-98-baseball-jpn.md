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

### Ohtani's Hit Zones (2025 MLB Season)

<img src="/images/jpn_ohtani_hit_heatmap.png" alt="Ohtani Hit Heatmap 2025" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Ohtani's 2025 hitting profile: KDE of hit density (top-left), P(hit) per zone bin (top-right), P(hit|swing) per zone bin (bottom-left), and single vs. extra-base hit locations (bottom-right). The red star marks Cheng's grand slam curveball location. Note: P(hit) and P(hit|swing) have different spatial patterns — high P(hit) zones reflect both swing tendency and contact quality, while P(hit|swing) isolates pure contact danger.</p></invoke>

### The Grand Slam Pitch: Model Verdict

<img src="/images/jpn_ohtani_hit_model.png" alt="Ohtani Grand Slam Model Analysis" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #ecfdf5; border-left: 5px solid #059669; padding: 20px; border-radius: 8px;">
    <h3 style="color: #059669; margin-top: 0;">P(hit|swing) = 13.2%</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">The curveball Cheng threw (76.8 mph, 2483 rpm, at pX=-0.46, pZ=2.16) had a <strong>predicted P(hit|swing) of only ~13%</strong> based on the RF/GBM ensemble. Given that Ohtani swings, the contact-to-hit probability was low — it was not a bad pitch by the numbers.</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #fefce8; border-left: 5px solid #ca8a04; padding: 20px; border-radius: 8px;">
    <h3 style="color: #ca8a04; margin-top: 0;">Cheng Chose Courage</h3>
    <p style="font-size: 1.05em; line-height: 1.6;">With bases loaded and first base open (if he walked Ohtani), Cheng chose to <strong>compete head-on</strong> — unlike the Blue Jays in the 2025 World Series, who intentionally walked Ohtani in similar situations. This was a brave call.</p>
  </div>
</div>

### What Drives Ohtani's Hit Probability?

<img src="/images/jpn_ohtani_shap.png" alt="SHAP Analysis for Ohtani Hit Model" style="width: 100%; max-width: 800px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">SHAP summary (top-left), individual breakdown for the grand slam pitch (top-right), and dependence plots for vertical location and speed (bottom). The SHAP breakdown for the grand slam curveball shows a predicted P(hit|swing) of 12.5% (RF model alone; the RF/GBM ensemble average is 13.2%). Spin rate and being in-zone pushed it slightly higher, but location and vertical break kept it suppressed.</p>

### Optimal Pitching Strategy

<img src="/images/jpn_ohtani_pitch_strategy.png" alt="Optimal Pitch Location Strategy" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>P(hit) = P(swing) x P(hit|swing)</strong> — the ensemble average of GBM and RF, constrained to the strike zone. The blue dot marks the optimal (lowest P(hit)) location for each pitch type; the red X marks where Cheng actually threw the grand slam curveball. For each pitch type, there existed locations with even lower predicted hit probability.</p>

<div style="background: #1a1a2e; padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center;">
  <p style="color: #93c5fd; font-size: 1.3em; font-weight: bold; margin: 0;">Model Recommendation</p>
  <div style="display: flex; justify-content: center; gap: 40px; margin-top: 20px; flex-wrap: wrap;">
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Changeup</span><br><span style="color: #aaa;">Low & inside — P(hit) = 4.1%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #7fecb3;">Fastball</span><br><span style="color: #aaa;">Low & away — P(hit) = 3.6%</span></div>
    <div><span style="font-size: 1.6em; font-weight: bold; color: #fca5a5;">Curveball</span><br><span style="color: #aaa;">Cheng's choice — P(hit) = 4.8%*</span></div>
  </div>
  <p style="color: #888; font-size: 0.85em; margin-top: 15px;">*Optimal curveball location. P(hit) = P(swing) × P(hit|swing) accounts for both swing likelihood and contact quality. Cheng's actual curveball had P(hit|swing) = 13.2% but was thrown in a high-swing-probability zone. A low-and-away fastball or low-inside changeup would have been the statistically safest options.</p>
</div>

---

## Conclusions

<div style="background: #f8fafc; border: 2px solid #334155; padding: 25px; border-radius: 10px; margin: 20px 0;">
  <ol style="line-height: 2; font-size: 1.05em;">
    <li><strong>Cheng's count control was the real problem</strong> — he repeatedly fell behind batters, loading the bases before Ohtani's at-bat. The meltdown was set up by a pattern, not a single pitch.</li>
    <li><strong>The grand slam pitch was not a bad pitch</strong> — at P(hit|swing) = 13.2%, the curveball had low contact danger. Cheng showed courage competing against Ohtani rather than issuing an intentional walk.</li>
    <li><strong>There was room for improvement</strong> — the models suggest a low-and-away fastball (P(hit) = 3.6%) or low-inside changeup (P(hit) = 4.1%) would have minimized the combined P(swing) × P(hit|swing) danger better than the curveball location Cheng chose.</li>
    <li><strong>The damage continued after Cheng</strong> — Hu and Sha combined for 5 more ER, proving this was a team-wide defensive collapse, not one pitcher's failure.</li>
  </ol>
</div>

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  Baseball is a game of probabilities. A pitch with 13% P(hit|swing) becomes a grand slam, and a narrative is born. But the data tells a more nuanced story — one of systemic count management issues, a courageous pitching decision, and the cruel randomness that makes this sport beautiful.
</div>
