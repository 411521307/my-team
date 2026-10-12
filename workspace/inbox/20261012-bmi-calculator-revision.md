# Revision: BMI calculator — add input range check 🧮

**From:** Leader · Wailan (洄瀾)
**To:** Member · Taroko (太魯閣)
**Date:** 2026-10-12
**Mode:** Manual relay
**Re:** send-back of `workspace/outbox/20261012-bmi-calculator.html`

## Verdict / 結果

Your file passes every test case and the spec. Good work — one gap to close before we ship.

## What to change / 改哪裡

**Add a plausible-range check.** Right now any positive number is accepted, so height `1` cm / weight `1` kg produces a huge BMI and shows "Obese 肥胖", which is nonsense.

Add these limits before calculating:

- Height: **50 – 250 cm**
- Weight: **10 – 300 kg**

Out-of-range input → show the friendly error box (same style as the existing one), do **not** show a result. Bilingual message, same tone as the current errors, e.g.:

> Height must be between 50 and 250 cm. / 身高須介於 50–250 公分。

Range check runs **after** the existing empty / NaN / `<= 0` checks, so keep those as they are.

## Save it / 存檔

- **New file**, do not overwrite the first version:
  `workspace/outbox/20261012-bmi-calculator-v2.html`
- Keep everything else exactly as-is (formula, categories, layout, quick-test buttons).
- Update the handoff note as a **new file** too:
  `workspace/outbox/20261012-bmi-calculator-revision.md`

## What "done" looks like / 怎樣算做完

- Height `1` → error, no result shown.
- Height `300` or weight `400` → error, no result shown.
- Height `1` / weight `1` → error, **not** "Obese".
- Original three test cases still pass: 170/65 → **22.5 Normal**, 160/50 → **19.5 Normal**, 170/90 → **31.1 Obese**.
- Empty / non-numeric input still shows the existing friendly error.
- First version `20261012-bmi-calculator.html` untouched.

Stay inside the project folder. Don't touch files in `shared/`.
