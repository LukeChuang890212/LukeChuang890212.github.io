---
title: "Survival Analysis: Nonparametric Estimation and Censored Data Modeling"
excerpt: "Kaplan-Meier estimation, hazard functions, log-rank tests, and Cox proportional hazards models applied to clinical and reliability data.<br/>"
collection: portfolio
---

## Data Source & Cleaning

Two types of survival data were analyzed:

- **Simulated Reliability Data**: Lifetime data following exponential and Weibull distributions, used to derive theoretical properties of survival functions, hazard functions, and median failure times.
- **Clinical Survival Data**: 43 observed survival times with right-censoring, requiring careful handling of censored observations in all estimation procedures.

## Exploratory Data Analysis (EDA)

- Empirical survival function computed and plotted to visualize the survival pattern over time.
- Step-function plots of the Kaplan-Meier estimator compared across groups.
- Censoring patterns examined to assess informative vs. non-informative censoring assumptions.

## Methods

- **Kaplan-Meier Estimator**: Nonparametric estimation of survival curves with Greenwood's formula for variance estimation and pointwise confidence intervals.
- **Parametric Models**: MLE for exponential and Weibull hazard models; derivation of variance via inverse Gamma distribution and Fisher information.
- **Log-Rank Test**: Two-sample comparison of survival curves.
- **Nelson-Aalen Estimator**: Cumulative hazard estimation as an alternative to KM.

## Results & Interpretation

- Demonstrated that the Kaplan-Meier estimator appropriately handles right-censored data and provides consistent estimates of the survival function.
- Parametric analysis showed that the exponential model's MLE has variance scaling as O(1/n), with explicit closed-form expressions derived.
- Weibull model provided flexible hazard modeling, capturing both increasing and decreasing hazard patterns depending on the shape parameter.

[Download Report 1 (PDF)](/files/SA_HW1_Survival.pdf) | [Download Report 2 (PDF)](/files/SA_HW2_Survival.pdf)
