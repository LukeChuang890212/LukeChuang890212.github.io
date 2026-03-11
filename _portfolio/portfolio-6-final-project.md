---
title: "Cost of Living Analysis: Global City Comparison via Multivariate Methods"
excerpt: "PCA, factor analysis, and clustering applied to global cost-of-living data across 55 expenditure categories to identify city groupings and spending patterns.<br/>"
collection: portfolio
---

## Data Source & Cleaning

**Cost-of-Living Dataset**: A comprehensive dataset covering living expenses across cities worldwide, with 55 cost variables organized into 8 domain categories:

| Category | Variables | Description |
|----------|-----------|-------------|
| Food & Dining | 1–27 | Groceries, restaurant meals, beverages |
| Transportation | 28–35 | Public transit, fuel, taxi fares |
| Facilities | 36–38 | Utilities, internet, phone plans |
| Entertainment | 39–41 | Cinema, gym, leisure activities |
| Education | 42–43 | Childcare, school fees |
| Clothing | 43–47 | Apparel, shoes |
| Housing | 48–53 | Rent, property prices |
| Others | 54–55 | Miscellaneous expenses |

Missing data was present and handled through **multiple imputation** (producing a fully imputed dataset stored for reproducible analysis). Data was standardized prior to multivariate analysis.

## Exploratory Data Analysis (EDA)

- Domain-grouped summary statistics revealed large variation in cost across cities, particularly in housing and education categories.
- Correlation analysis within and across domains identified strong intra-domain correlations (e.g., food items were highly correlated with each other) and moderate cross-domain correlations (e.g., housing costs correlated with dining costs).
- Distribution analysis guided decisions about standardization and transformation.

## Methods

- **Principal Component Analysis (PCA)**: Applied to the standardized imputed data to identify the main dimensions of variation in global living costs. Scree plot and cumulative variance plots guided component retention.
- **Factor Analysis**: Exploratory factor analysis to identify latent spending pattern factors and relate them to the 8 predefined domain categories.
- **Cluster Analysis**: Cities grouped by cost-of-living profiles, revealing natural tiers of expense levels.
- **Multiple Imputation**: Missing values imputed to produce a complete dataset for downstream multivariate analysis.

## Results & Interpretation

- PCA revealed that a small number of components captured the majority of variation, with the first component representing overall cost level and subsequent components distinguishing specific spending patterns (e.g., high housing but moderate food costs).
- Factor analysis produced interpretable factors that largely aligned with the predefined domain categories, validating the domain knowledge structure.
- Cluster analysis identified distinct city groups: high-cost global cities (e.g., major Western capitals), moderate-cost cities, and low-cost cities, with sub-clusters revealing nuanced differences in spending profiles.
- The analysis provided a data-driven framework for comparing cities beyond simple cost rankings, capturing multidimensional spending patterns useful for relocation decisions or economic policy analysis.

[Download Full Report (PDF)](/files/SL_Final_Cost_of_Living.pdf)
