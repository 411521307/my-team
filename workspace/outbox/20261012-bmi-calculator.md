> **Handoff:** Built single-file BMI calculator in `20261012-bmi-calculator.html`; verified against all specified test cases (170/65 -> 22.5 Normal, 160/50 -> 19.5 Normal, 170/90 -> 31.1 Obese) with input validation; ready to use.

# BMI Calculator Delivery

- **Artifact:** [`20261012-bmi-calculator.html`](20261012-bmi-calculator.html)
- **Author:** Member · Taroko (太魯閣)
- **Date:** 2026-10-12
- **Mode:** Manual relay

## Features Implemented
1. Single self-contained file with HTML5, CSS3, and JavaScript (no external libraries or build step).
2. Input fields for height (cm) and weight (kg).
3. Formula implementation: `BMI = weight / (height / 100)²` rounded to 1 decimal place.
4. WHO categorization:
   - `< 18.5` → Underweight 過輕
   - `18.5 – 24.9` → Normal 正常
   - `25.0 – 29.9` → Overweight 過重
   - `≥ 30.0` → Obese 肥胖
5. Friendly error handling for empty, non-numeric, or non-positive input (avoids `NaN`).
6. Clean responsive card layout with quick test buttons.
