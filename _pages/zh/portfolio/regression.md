---
title: "迴歸建模：臭氧預測與前列腺癌分析"
permalink: /zh/portfolio/regression/
layout: single
author_profile: true
---


<div style="background: linear-gradient(135deg, #0d4f4f 0%, #1a7a5a 50%, #2d8f4e 100%); padding: 30px; border-radius: 12px; margin-bottom: 30px; color: #e0e0e0;">
  <h2 style="color: #7fecb3; margin-top: 0; font-size: 1.6em;">從原始數據到預測模型</h2>
  <p style="font-size: 1.1em; line-height: 1.7; color: #f5f5f5;">
    兩個截然不同的領域——<strong>環境科學</strong>與<strong>癌症生物學</strong>——透過迴歸理論的視角加以分析。從發現風速對臭氧濃度的閾值效應，到辨識前列腺癌進展最關鍵的預測因子。
  </p>
</div>

## 資料來源與清理

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 280px; background: #f0faf5; border-left: 5px solid #2d8f4e; padding: 20px; border-radius: 8px;">
    <h3 style="color: #2d8f4e; margin-top: 0;">臭氧資料</h3>
    <p><strong>111 筆每日測量值</strong>，包含臭氧、輻射、溫度和風速。無缺失值。應用 Box-Cox 轉換（五次方根）以滿足常態性假設。</p>
  </div>
  <div style="flex: 1; min-width: 280px; background: #f0f5fa; border-left: 5px solid #3a7bd5; padding: 20px; border-radius: 8px;">
    <h3 style="color: #3a7bd5; margin-top: 0;">前列腺癌資料</h3>
    <p><strong>97 筆觀測值</strong>，包含 8 個臨床預測因子與 log-PSA 反應變數。70/27 的訓練-驗證分割。根據 Dunn 多重比較檢定，將 Gleason 分數 7-9 合併為「高」等級。</p>
  </div>
</div>

## 探索性資料分析（EDA）

- **臭氧**：臭氧與輻射和溫度呈強正相關；與風速呈負相關。條件散佈圖揭示了**風速閾值效應**。
- **前列腺癌**：Kendall's tau 識別出 lcavol、lweight、lcp 和 pgg45 與 lpsa 顯著相關。Kruskal-Wallis 和 Wilcoxon 檢定確認離散變數的顯著效果。

## 方法

| 方法 | 用途 |
|--------|---------|
| Linear Regression | 多項式項與交互效應 |
| AIC/BIC Stepwise Selection | 精簡模型識別 |
| 模型診斷 | 殘差、VIF、槓桿值、影響力 |
| Box-Cox 轉換 | 反應變數常態化 |
| 無母數檢定 | 離散預測因子評估 |
| 預測區間 | 驗證集評估 |

## 主要結果

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #2d8f4e; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #2d8f4e; margin: 5px 0;">RMSE ≈ 19</p>
    <p style="color: #666;">臭氧預測——相對於臭氧範圍較小，顯示優良的預測表現</p>
  </div>
  <div style="flex: 1; min-width: 250px; background: #f8f9fa; border: 2px solid #3a7bd5; padding: 20px; border-radius: 12px; text-align: center;">
    <p style="font-size: 2.2em; font-weight: bold; color: #3a7bd5; margin: 5px 0;">lcavol + svi</p>
    <p style="color: #666;">前列腺癌進展（log-PSA）最重要的預測因子</p>
  </div>
</div>

- 發現了**風速閾值效應**——風速在閾值以下有強烈的負面影響，但在閾值以上效果可忽略。
- 最終前列腺癌模型在驗證集上達成了校準良好的預測區間。

<div style="margin-top: 25px;">
  <a href="/files/SL_HW1_Regression.pdf" style="display: inline-block; background: #2d8f4e; color: white; padding: 10px 24px; border-radius: 6px; text-decoration: none; font-weight: bold;">下載完整報告（PDF）</a>
</div>
