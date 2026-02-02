# NBA Salary Determinants (2022–23)

**Key takeaway:**  
Using a cross-sectional log-salary regression for the 2022–23 season, this project finds that **availability (games played)** and **recognition (All-Star selection)** explain player pay more consistently than advanced metrics like **BPM**, once institutional contract constraints (rookie scale, max contracts, etc.) are considered. The final model explains ~54% of variation in log salaries.

## Role & Tools
**Role:** Applied Data Analyst / Applied Econometrics  
**Tools:** Stata (data cleaning + OLS), robust standard errors, heteroskedasticity diagnostics

## Research Question
How do **performance (BPM)**, **age**, **availability (games played)**, and **awards (All-Star, All-NBA)** relate to NBA player salaries in the 2022–23 season? :contentReference[oaicite:1]{index=1}

---

## Data
- **Unit of observation:** player-season (one season, cross-section)
- **Sample size:** 467 players :contentReference[oaicite:2]{index=2}
- **Sources:**
  - Salaries from Spotrac
  - Stats/awards from Basketball-Reference (BPM, GP, age, All-Star, All-NBA) :contentReference[oaicite:3]{index=3}

### Variable construction highlights (in Stata)
- Excel import required renaming columns (A, B, C, …) into usable variables :contentReference[oaicite:4]{index=4}  
- Salary was log-transformed to handle heavy right-skew and interpret coefficients in % terms :contentReference[oaicite:5]{index=5}  
- All-Star and All-NBA indicators were created as manual dummies via roster matching :contentReference[oaicite:6]{index=6}  

---

## Model
Primary specification: OLS regression of **ln(salary)** on:
- BPM
- Age
- Games played (GP)
- All-Star dummy
- All-NBA dummy :contentReference[oaicite:7]{index=7}

Because salary dispersion increases at the top of the market, heteroskedasticity tests strongly reject homoskedastic errors:
- Breusch–Pagan χ²(1)=46.98, p<0.0001
- White χ²(18)=91.98, p<0.0001 :contentReference[oaicite:8]{index=8}  
Final inference uses **robust standard errors**. :contentReference[oaicite:9]{index=9}

---

## Results (robust SE)
- **BPM:** positive but not statistically significant once controls are included (β≈0.0199, p=0.329) :contentReference[oaicite:10]{index=10}  
- **Age:** strong positive predictor (β≈0.1125, p<0.001) :contentReference[oaicite:11]{index=11}  
- **Games Played (availability):** very strong positive predictor (β≈0.0358, p<0.001) :contentReference[oaicite:12]{index=12}  
- **All-Star:** one of the largest effects (β≈0.998, p<0.001) :contentReference[oaicite:13]{index=13}  
- **All-NBA:** positive but not statistically significant in this setup (β≈0.332, p≈0.16) :contentReference[oaicite:14]{index=14}  
- **Model fit:** R² ≈ 0.54 with 467 observations :contentReference[oaicite:15]{index=15}

### Interpretation
In a regulated labor market (rookie scale, max contracts, long-term deals), salaries often reflect contract timing and status signals. As a result, **durability and recognition** show up more strongly than advanced metrics like BPM in a one-season cross-section. :contentReference[oaicite:16]{index=16}

---

## Limitations & Next Steps
- Cross-sectional design: salary often reflects prior seasons and contract timing :contentReference[oaicite:17]{index=17}  
- Omitted variables (position, injuries, years of experience, etc.) :contentReference[oaicite:18]{index=18}  
- Extension: build a panel across seasons to connect performance changes to salary changes

---

## Repository Contents

### Report
- **Paper (DOCX):**  
  [What Drives NBA Players Salaries.docx](./reports/What%20Drives%20NBA%20Players%20Salaries.docx)  
  *(Large file — click the link above, then use the Download button left of the pencil to view locally.)*

### Data
- **Excel dataset (XLSX):**  
  [NBA Player Salaries and Performance Metrics (XLSX)](./data/NBA%20Player%20Salaries%20and%20Performance%20Metrics%20export%202025-11-28%2004-47-37.xlsx)  
  *(Large file — click the link above, then use the Download button left of the pencil to view locally.)*

---

## Notes on Reproducibility
The original analysis was completed in **Stata**, but the `.do` file was not recovered. This repository includes the final written report and the original dataset so the workflow, assumptions, and results are fully documented. A replication script can be added later if reconstructed.
