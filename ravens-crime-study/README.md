# Baltimore Ravens Football and Crime in Baltimore City (2011–2023)

**Key takeaway:**  
This study examines whether Baltimore Ravens football games influence crime in Baltimore City. While game outcomes (wins vs. losses) show little effect, **very high-magnitude games (such as playoff games)** are associated with noticeable reductions in both violent and property crime. At the same time, average daily crime rates are **higher on football-related days** than on non-football days, complicating simple claims that team success reduces crime.

---

## Role & Context

**Role:** Applied Data Analyst / Applied Econometrics  
**Context:** Public policy, urban economics, sports analytics

---

## Research Questions

1. Do Ravens wins reduce violent or property crime in Baltimore City?
2. Do high-magnitude and playoff games affect crime differently than low-magnitude games?
3. Does game location (home vs. away) matter for post-game crime?
4. Are crime rates different on football-related days compared to non-football days?

---

## Project Overview

This project analyzes Baltimore crime data alongside **226 Baltimore Ravens games from 2011 to 2023**.  
Crime totals were measured in **three-day periods following each game** to capture lingering emotional and behavioral effects while avoiding same-day stadium noise.

Games were classified by:
- Outcome (win vs. loss)
- Location (home, away, neutral)
- Magnitude (low, high, very high)

---

## Data Overview

- **Dataset:** Ravens-Crime Study Data.csv  
- **Outcomes:**  
  - Violent crime totals (3-day post-game windows)  
  - Property crime totals (3-day post-game windows)
- **Predictors:**  
  - Game outcome  
  - Game magnitude  
  - Game location  

Crime data were aggregated to the three-day level to focus on post-game effects rather than immediate crowd-related activity.

---

## Methods Summary

This study uses **count-based statistical analysis** appropriate for crime data.  
Results are interpreted in terms of **direction, magnitude, and statistical significance**, with careful attention to overdispersion and realistic inference rather than purely predictive accuracy.

---

## Core Findings

- **Game outcomes (wins vs. losses):**  
  No consistent or statistically strong effect on violent crime; weak effects for property crime.

- **Game magnitude:**  
  Very high-magnitude games (playoffs) are associated with reductions in both violent and property crime in post-game periods.

- **Game location:**  
  Home vs. away games show no meaningful difference in post-game crime totals.

- **Football vs. non-football days:**  
  Average daily crime rates are higher on football-related days, suggesting increased activity and exposure rather than crime suppression.

---

## Interpretation & Implications

- Sports success alone should not be treated as a crime-reduction strategy.
- High-stakes games may temporarily reduce crime through community cohesion or behavioral shifts.
- Policymakers should distinguish **event magnitude** from simple win–loss narratives when evaluating sports-related social effects.

---

## Repository Contents

### Report
- **Final paper:**  
  [The Effects of Baltimore Ravens Football on Crime in Baltimore City (Job Ready).docx](./reports/The%20Effects%20of%20Baltimore%20Ravens%20Football%20on%20Crime%20in%20Baltimore%20City%20(Job%20Ready).docx)

### Data
- **Cleaned dataset:**  
  [Ravens-Crime Study Data.csv](./data/Ravens-Crime%20Study%20Data.csv)

---

## Notes on Reproducibility

The original analysis was conducted using statistical software. The final written paper and cleaned dataset are provided here to document the methodology, results, and conclusions. Reproduction code can be added in the future if the original analysis scripts are recovered or reconstructed.
