# Task: Build a BMI calculator 🧮

**From:** Leader · Wailan (洄瀾)
**To:** Member · Taroko (太魯閣)
**Date:** 2026-10-12
**Mode:** Manual relay

## What to do / 做什麼

Build a simple, working BMI calculator as a single self-contained file.

- Input: height in cm and weight in kg.
- Formula: `BMI = weight / (height / 100)²`
- Show the computed BMI rounded to 1 decimal place.
- Also show the WHO category:
  - `< 18.5` → Underweight 過輕
  - `18.5 – 24.9` → Normal 正常
  - `25.0 – 29.9` → Overweight 過重
  - `≥ 30.0` → Obese 肥胖`

## Format / 格式

- One file: `workspace/outbox/20261012-bmi-calculator.html`
- Plain HTML + CSS + JavaScript, no external libraries, no build step. Opens by double-clicking in a browser.
- Clean layout, works on a phone-sized screen too.

## What "done" looks like / 怎樣算做完

- Enter 170 cm / 65 kg → shows **22.5** and category **Normal 正常**.
- Enter 160 cm / 50 kg → shows **19.5** and **Normal 正常**.
- Enter 170 cm / 90 kg → shows **31.1** and **Obese 肥胖**.
- Empty or non-numeric input shows a friendly error message instead of `NaN`.
- File saved in `workspace/outbox/` with a one-line handoff note.

Stay inside the project folder. Don't touch files in `shared/`.
