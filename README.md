# Housing-Affordability-England
# England Housing Affordability Analysis (2019–2025)

**Tools:** Python · pandas · scikit-learn · matplotlib · seaborn · Power BI
**Data:** ONS Private Rental Market Statistics · VOA Rental Statistics · ASHE (ONS)
**Coverage:** 281 English local authorities · 2019–2025

---

## Overview

Analyses private rental affordability for **individual renters** across 281 English local authorities, using median rent for single-occupancy properties against median individual earnings. The **30% rent-to-income threshold** (ONS/Shelter standard) defines housing stress.

---

## Key Findings

- **2023 structural break:** share of LAs above the 30% threshold nearly doubled in one year (6.8% → 17.1%), driven by the post-pandemic rent surge
- **38 LAs are deteriorating** — affordable in 2019 but worsening, including Bristol, Reading, Bath, and Manchester (first major Northern city to tip in 2024)
- Only **8 LAs (3%)** have been persistently unaffordable — the crisis is spreading, not concentrated
- Linear trend forecasts flag at-risk LAs projected to cross the threshold by 2028

---

## Methodology

| Step | Approach |
|---|---|
| Data pipeline | ONS/VOA rent + ASHE salary merged into balanced panel (281 LAs × 7 years) |
| Feature engineering | Rent burden, affordability ratio, disposable income per LA per year |
| Clustering | KMeans evaluated (elbow + silhouette → k=2); rejected in favour of threshold-based segmentation |
| Segmentation | LAs classified into 4 behavioural tiers based on 30% threshold history |
| Forecasting | ARIMA evaluated and rejected (n=7 too small); OLS linear trend per LA with 80% prediction intervals |

---

## Limitations

- Rent category change (2022→2023) may introduce a small level shift
- Linear forecasts assume no structural breaks post-2025
- ASHE full-time salary understates pressure on part-time and below-median earners
- England only
