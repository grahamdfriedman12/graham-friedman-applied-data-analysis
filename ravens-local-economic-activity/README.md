# Baltimore Ravens & Local Economic Activity

![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Applied%20Economics](https://img.shields.io/badge/Focus-Applied%20Economics-blue)

Related project: [Ravens Football and Crime in Baltimore City](../ravens-crime-study)

## Do Baltimore Ravens Home Games Boost Local Spending? (Baltimore, 2020–2024)

**Key takeaway:**  
Using daily citywide spending data from 2020–2024 (981 days) merged with Baltimore Ravens game indicators, this study finds **no statistically significant evidence** that Ravens home games, the three days after home games, game magnitude, or game outcomes measurably shift **aggregate** consumer spending in Baltimore City. The regression’s explanatory power is extremely low (R² ≈ 0.01), consistent with the idea that macro conditions (COVID-era volatility, seasonality, holidays, inflation, etc.) dominate daily spending variation.

---

## Role & Tools
**Role:** Applied Data Analyst / Applied Econometrics  
**Tools:** Excel (data merging, indicators, tables, graphs), OLS regression reporting  
*(All figures, tables, and numeric outputs in the paper were generated via Excel functions.)*

---

## Research Question
Do Ravens home games create measurable short-run changes in citywide consumer spending in Baltimore from 2020–2024?

This project extends earlier Ravens-related work by testing whether the emotional/event-day channel that can influence behavior also shows up in high-frequency spending outcomes.

---

## Data Overview (Daily, 2020–2024)
- **Unit of observation:** calendar day
- **Time window:** January 2020 – December 2024
- **Observations:** 981 days
- **Outcome variable:** `spend_all` = daily percent change in total consumer spending relative to a January 2020 baseline (Baltimore City, cityid = 23) :contentReference[oaicite:1]{index=1}
- **Spending source:** Opportunity Insights / Affinity Solutions city-daily spending series :contentReference[oaicite:2]{index=2}
- **Game data source:** Pro Football Reference (game dates, outcomes, home/away) :contentReference[oaicite:3]{index=3}

### Football-related variables (constructed)
- `GameDay` = 1 if Ravens played on day t, else 0 :contentReference[oaicite:4]{index=4}  
- `PostGame` = 1 for the three days following each **home** game, else 0 :contentReference[oaicite:5]{index=5}  
- `Magnitude` = 0 low, 1 high, 2 very high/playoffs (carried over from prior work) :contentReference[oaicite:6]{index=6}  
- `Outcome` = 1 win, 0 loss, 2 tie; blank on non-game days :contentReference[oaicite:7]{index=7}  

---

## Empirical Strategy
A simple OLS regression tests whether football-related variables explain variation in daily spending:

spend_all ~ Outcome + Magnitude + GameDay + PostGame

The model is intentionally simple to evaluate whether any “game signal” is detectable in aggregate citywide spending during a highly volatile economic period.

---

## Results (Main Regression)
The paper’s OLS results show no statistically significant football-related effects. :contentReference[oaicite:8]{index=8}

- `GameDay`: coefficient ≈ 0.0390, p = 0.244  
- `PostGame`: coefficient ≈ 0.00073, p = 0.9739  
- `Magnitude`: coefficient ≈ 0.0294, p = 0.3223  
- `Outcome`: coefficient ≈ 0.0431, p = 0.1530 :contentReference[oaicite:9]{index=9}  

Model fit:
- R² = 0.00995 (≈ 1% of variation explained)
- Observations = 981 :contentReference[oaicite:10]{index=10}  

Interpretation: daily spending is influenced by many omitted factors (COVID phases, seasonality, holidays, inflation, etc.), making subtle sports-related effects difficult to detect in a citywide aggregate series. :contentReference[oaicite:11]{index=11}

---

## Repository Contents

### Report
- **Paper (DOCX):**  
  [Do Baltimore Ravens Home Games Boost Local Spending.docx](./reports/Do%20Baltimore%20Ravens%20Home%20Games%20Boost%20Local%20Spending.docx)  
  *(If GitHub won’t preview the file, click the link above and then use the **Download** button left of the pencil to view locally.)*

### Data
- **Merged dataset (CSV):**  
  [Local Ravens Spending data.csv](./data/Local%20Ravens%20Spending%20data.csv)

---

## Notes on Reproducibility
This project’s cleaning, variable construction, tables, and figures were produced in Excel. The final paper and dataset are provided for transparency and auditing. A replication script (Python/R/Stata) could be added in the future if the Excel workflow is migrated to code.
