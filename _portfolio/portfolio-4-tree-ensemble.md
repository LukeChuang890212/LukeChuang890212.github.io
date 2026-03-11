---
title: "Tree-Based & Ensemble Methods: Bike Sharing and Airline Satisfaction"
excerpt: "Decision trees, random forests, gradient boosting, and nonlinear regression for demand prediction and customer satisfaction classification.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Two datasets were analyzed:

- **Bike Sharing Data**: 731 daily observations (2011–2012) with 11 predictors including calendar info (season, year, month, weekday, holiday, working day), weather conditions (weather category, temperature, humidity, wind speed), and a time index. Response: daily bike sharing count. An 80/20 train-test split was applied.
- **Airline Customer Satisfaction Survey**: 103,594 observations (after removing missing values) with 23 predictors including demographics (gender, age), travel info (customer type, travel type, class, flight distance), service ratings (14 feedback items), and delay metrics. Response: binary satisfaction (satisfied/dissatisfied). An 80/20 train-test split was used.

## Exploratory Data Analysis (EDA)

- **Bike Sharing**: Temperature showed the strongest positive correlation with count (r = 0.627). Bike usage was higher in 2012 than 2011, likely due to system maturity. A potential quadratic effect of temperature was detected — count increased up to ~20°C then declined. Weather impact on count appeared independent of day type (holiday/working day). Interaction between temperature and season/month was identified.
- **Airline**: Service feedback items showed strong discriminative power. Most customers were loyal and traveled for business. Departure/arrival delay distributions were severely right-skewed. Leverage points were identified in some service ratings but retained given the large sample size.

## Methods

**Bike Sharing (Regression):**
- **Decision Tree**: Cost-complexity parameter tuned via 5-fold CV; pruned to 11 terminal nodes
- **Random Forest**: Number of candidate variables (m) tuned via CV
- **Gradient Boosting (GBM)**: Grid search over interaction depth, shrinkage parameter, and number of trees via CV
- **Linear Regression**: Best subset selection for variable choice
- **Nonlinear Regression**: Polynomial terms (temp²), interaction terms (temp × season/month), and B-spline with knot position selection via CV

**Airline (Classification):**
- **Random Forest** and **Gradient Boosting** for classification with variable importance analysis
- Noise variables (z1–z?) injected to validate the variable importance ranking

## Results & Interpretation

- **Bike Sharing**: Tree-based ensemble methods (random forest and boosting) substantially outperformed single decision trees and linear models. Year and temperature were consistently ranked as the two most important predictors. The nonlinear regression with spline basis captured the temperature threshold effect better than polynomial models. Humidity and weather category provided secondary but meaningful predictive power.
- **Airline**: Online boarding, inflight Wi-Fi, and type of travel were among the top predictors of satisfaction. The noise variable experiment confirmed that meaningful predictors consistently ranked above injected noise, validating the variable importance framework. Business class passengers and those traveling for business showed higher satisfaction rates.

[Download Full Report (PDF)](/files/SL_HW4_Tree_Methods.pdf)
