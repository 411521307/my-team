> **Handoff:** Fixed: added height (50–250 cm) and weight (10–300 kg) range checks with friendly bilingual error alerts in `20261012-bmi-calculator-v2.html`; all previous tests pass and edge cases verified; ready to use.

# Revision Delivery: BMI Calculator (v2)

- **Artifact:** [`20261012-bmi-calculator-v2.html`](20261012-bmi-calculator-v2.html)
- **Author:** Member · Taroko (太魯閣)
- **Date:** 2026-10-12
- **Mode:** Manual relay
- **Re:** Leader's send-back note `workspace/inbox/20261012-bmi-calculator-revision.md`

## What Changed
1. **Added plausible-range checks:**
   - Height range: `50 – 250 cm`. Out-of-range displays: `Height must be between 50 and 250 cm. / 身高須介於 50–250 公分。`
   - Weight range: `10 – 300 kg`. Out-of-range displays: `Weight must be between 10 and 300 kg. / 體重須介於 10–300 公斤。`
2. **Order of validation:**
   - Checks empty fields → NaN / `<= 0` → Plausible range limits.
   - Any failure displays the friendly error box and suppresses the result display.
3. **Preservation:**
   - Saved as new version `20261012-bmi-calculator-v2.html`.
   - Untouched the original file `20261012-bmi-calculator.html`.

## Verification
- Height `1` → Error shown (`Height must be between 50 and 250 cm. / 身高須介於 50–250 公分。`), no result shown (Fixed: no longer calculates or shows "Obese").
- Height `300` / Weight `400` → Error shown, no result.
- Height `1` / Weight `1` → Error shown, no result.
- Empty / non-numeric input → Existing friendly error shown.
- Standard test cases verified:
  - 170 cm / 65 kg → **22.5 Normal 正常**
  - 160 cm / 50 kg → **19.5 Normal 正常**
  - 170 cm / 90 kg → **31.1 Obese 肥胖**
