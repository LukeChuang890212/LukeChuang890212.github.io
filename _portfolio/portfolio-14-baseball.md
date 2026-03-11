---
title: "Baseball Analytics: Umpire Strike Zone Bias in WBC 2026 Taiwan vs. Australia"
excerpt: "Kernel density estimation of the home plate umpire's practical strike zone reveals a striking asymmetry between teams — with Taiwan batters facing a significantly expanded zone and lower-edge calls systematically favoring Australia.<br/>"
collection: portfolio
---

<div style="background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #e94560; margin-top: 0; font-size: 1.6em;">WBC 2026 Pool C: Taiwan @ Australia (Mar 5, 2026)</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    How fair was the home plate umpire? Using pitch-level data and kernel density estimation, I reconstructed <strong>Omar Peralta's practical strike zone</strong> for each half-inning to quantify umpire bias in one of the most memorable games of the 2026 World Baseball Classic.
  </p>
</div>

## The Question

In baseball, the rulebook strike zone is well-defined — but the *practical* strike zone called by the home plate umpire can vary pitch by pitch. When a team suspects inconsistency, data can tell the story. After Taiwan's dramatic game against Australia in WBC 2026 Pool C, I set out to answer: **was the strike zone called consistently for both teams?**

## Data Source & Cleaning

- **Pitch-Level Data**: Ball-by-ball location data (horizontal and vertical coordinates in feet, from the catcher's perspective) for all called pitches (balls and strikes, excluding swings) in the Taiwan vs. Australia game.
- **142 called pitches** were analyzed: 75 when Taiwan was batting, 67 when Australia was batting.
- Each pitch was labeled as a called strike or called ball, and cross-referenced against the rulebook strike zone boundaries.

## Methods

- **2D Kernel Density Estimation**: Gaussian KDE applied to called-strike locations to estimate the umpire's practical strike zone contour for each team's at-bats separately.
- **Accuracy Classification**: Each called pitch was categorized into four types — Correct Strike, Correct Ball, Generous Strike (called strike outside the zone), and Erroneous Ball (called ball inside the zone).
- **Strike Zone Difference Map**: A differential heatmap (Taiwan zone probability minus Australia zone probability) was computed to visualize spatial bias.
- **Contour Comparison**: The 50% probability contours for each team were overlaid against the rulebook zone to highlight shape and size discrepancies.

## Key Findings

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 25px 0;">
  <div style="flex: 1; min-width: 250px; background: #fff3f3; border-left: 5px solid #e94560; padding: 20px; border-radius: 8px;">
    <h3 style="color: #e94560; margin-top: 0;">Taiwan Batting</h3>
    <p style="font-size: 2em; font-weight: bold; color: #e94560; margin: 5px 0;">77% accuracy</p>
    <p>The umpire's strike zone was <strong>dramatically expanded</strong> — bloated outward in almost every direction. The zone's shape was so irregular it almost resembled the map of Australia. Nearly <strong>two-thirds of all incorrect calls went against Taiwan</strong>.</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f0f7ff; border-left: 5px solid #3498db; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3498db; margin-top: 0;">Australia Batting</h3>
    <p style="font-size: 2em; font-weight: bold; color: #3498db; margin: 5px 0;">87% accuracy</p>
    <p>The zone collapsed into a <strong>flat, narrow rectangle</strong>. Low pitches were almost universally called balls, forcing Taiwan's pitchers to elevate — leaving them vulnerable to hard contact in the upper zone.</p>
  </div>
</div>

## Visualizations

### Umpire's Practical Strike Zone vs. Rulebook Zone

<img src="/images/strike_zone_accuracy.png" alt="Strike Zone Accuracy Comparison" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">The KDE-estimated strike zone (shaded contour) compared against the rulebook zone (dashed rectangle). When Taiwan bats (left), the zone expands well beyond the rulebook boundaries. When Australia bats (right), it shrinks — particularly at the bottom edge.</p>

### Strike Zone Heatmap Comparison by Team

<img src="/images/strike_zone_comparison.png" alt="Strike Zone Heatmap Comparison" style="width: 100%; max-width: 900px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;">Omar Peralta's practical strike zone reconstructed via 2D Gaussian KDE. Red regions indicate high strike probability. The asymmetry is immediately visible: Taiwan faces a large, amorphous zone while Australia faces a compact, high-centered one.</p>

### Strike Zone Difference Map

<img src="/images/strike_zone_diff.png" alt="Strike Zone Difference Map" style="width: 100%; max-width: 700px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.2); margin: 20px 0;">

<p style="color: #666; font-size: 0.95em;"><strong>Red = higher strike probability when Taiwan bats; Blue = higher when Australia bats.</strong> The red region dominates, confirming that the effective strike zone was substantially larger for Taiwan's at-bats across nearly all locations.</p>

## Results & Interpretation

| Metric | Taiwan Batting | Australia Batting |
|--------|:-:|:-:|
| Called pitches | 75 | 67 |
| Accuracy | **58/75 (77%)** | **58/67 (87%)** |
| Generous strikes (outside zone called strike) | 14 | 5 |
| Erroneous balls (inside zone called ball) | 3 | 4 |
| Tight calls | 5 | 5 |

The data tells a clear story. When Taiwan was at bat, the umpire's zone ballooned outward — calling strikes on pitches well off the plate. This 77% accuracy rate is notably poor by professional standards. Critically, the errors were **asymmetric**: generous strikes (bad calls *against* the batter) outnumbered erroneous balls by nearly 5-to-1 when Taiwan batted.

When Australia batted, the zone tightened dramatically. The bottom edge essentially vanished — low pitches that would have been called strikes against Taiwan were now called balls. This likely forced Taiwan's pitchers to elevate their offerings, increasing the risk of being hit hard.

<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 20px; border-radius: 8px; margin-top: 25px; font-style: italic; color: #555;">
  In memory of an unforgettable game. The numbers don't lie — but the strike zone certainly did.
</div>
