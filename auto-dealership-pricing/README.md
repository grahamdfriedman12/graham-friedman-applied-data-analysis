# Used Car Pricing & Model Selection

![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)
![Applied%20Econometrics](https://img.shields.io/badge/Focus-Applied%20Econometrics-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

**Key takeaway:** This project compares interpretable and flexible pricing models (linear/regularized regression, GAMs, and tree-based methods) and recommends a final approach that balances predictive accuracy with explainability for dealership pricing and inventory decisions.

**Role:** Applied Data Analyst  
**Tools:** R, mgcv (GAM), glmnet (Lasso), Random Forest, Cross-Validation  

## Deliverables

- **Technical Report:**  
  [`Auto Technical Report.pdf`](./reports/Auto%20Technical%20Report.pdf)

- **Executive (Non-Technical) Report:**  
  [`Auto Non-Technical Report.pdf`](./reports/Auto%20Non-Technical%20Report.pdf)

- **Reproducible Analysis:**  
  [`Auto Code.html`](./code/Auto%20Code.html)  
  *(Large HTML file — click on the link above and then click the download button left of the pencil button on the righthand side of the screen to view full analysis)*

---

## Project Overview

This project analyzes used car listings to support **pricing strategy and inventory selection** for a hypothetical dealership, *Three Rivers Auto*.  
The goal was to balance **predictive accuracy** with **model interpretability**, allowing stakeholders to both forecast prices and understand *why* vehicles are valued the way they are.

To capture real market conditions, extreme listings were retained rather than removed, ensuring the models reflected realistic pricing boundaries.

---

## Data Overview

The dataset contains used car listings with the following features:

- Vehicle age (year)
- Mileage
- Horsepower
- Engine size (liters, cylinders)
- Brand / manufacturer
- Fuel type
- Transmission type
- Accident history

**Target variable:** log-transformed vehicle price

The log transformation was applied due to heavy right-skew in raw prices, improving model stability and interpretability.

---

## Data Cleaning & Modeling Decisions

- Inconsistent categorical labels were standardized (e.g., transmission and fuel type)
- Rare category levels were retained when economically meaningful
- High-leverage observations (e.g., very high-mileage vehicles) were **kept** to preserve real-world price bounds
- Rank-deficiency warnings were evaluated rather than blindly corrected, prioritizing data realism over cosmetic model fit

---

## Modeling Approach

Multiple models were estimated and evaluated using train/test splits and cross-validation:

| Model | Evaluation Metric | Performance |
|------|------------------|-------------|
| Linear Regression (Interactions) | CV RMSE | ~0.343 |
| Lasso Regression | Test RMSE | ~0.323 |
| Generalized Additive Model (GAM) | CV RMSE | ~0.323 |
| Random Forest | RMSE | ~0.317 |

While Random Forest achieved the lowest error, it lacked transparency.  
The **GAM** was selected as the final model due to its ability to capture nonlinear relationships *while remaining interpretable*.

---

## Key Insights

### Mileage Depreciation
- Vehicle price declines sharply up to ~60,000 miles
- Depreciation flattens beyond this point, indicating strong value opportunities in mid-mileage inventory

### Horsepower Effects
- Price premiums rise rapidly up to ~250 horsepower
- Beyond this threshold, additional horsepower yields diminishing returns

### Brand × Transmission Interaction
- Manual transmissions generally reduce price
- However, manual transmissions **increase value** for enthusiast brands (e.g., Porsche), highlighting segmentation effects

---

## Business Recommendations

- Prioritize vehicles in the **60k–100k mile range** to maximize price-to-value ratios
- Avoid overpaying for high-horsepower trims above ~250 HP
- Treat transmission effects as **brand-specific**, not universal
- Use GAM smooths to communicate nonlinear depreciation patterns to non-technical stakeholders

---

## Limitations & Next Steps

**Missing data:**
- Vehicle condition
- Service history
- Geographic location

**Future improvements:**
- Incorporate regional pricing controls
- Add condition proxies
- Estimate prediction intervals for pricing risk assessment
These limitations suggest pricing recommendations should be used as decision support rather than deterministic rules.
---

## Repository Contents

- `reports/Auto_Technical_Report.pdf` – Full statistical methodology and diagnostics  
- `reports/Auto_NonTechnical_Report.pdf` – Executive-facing summary and recommendations  
- `code/Auto_Code.html` – Reproducible analysis and modeling walkthrough  

---

## How to Reproduce

1. Open `code/Auto_Code.html`
2. Review preprocessing, model estimation, and evaluation steps
3. Refer to reports for interpretation and recommendations

### How to Navigate This Project

- Start with this README for context and methodology
- Read the **Executive Report** for insights and recommendations
- Refer to the **Technical Report** for statistical details
- Download the **HTML analysis** to inspect the full reproducible workflow
