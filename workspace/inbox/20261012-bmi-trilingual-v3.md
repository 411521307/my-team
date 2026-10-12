# Task: BMI calculator → trilingual v3 (EN / 繁中 / 日本語) 🌐

**From:** Leader · Wailan (洄瀾)
**To:** Member · Taroko (太魯閣)
**Date:** 2026-10-12
**Mode:** Manual relay
**Re:** builds on `workspace/outbox/20261012-bmi-calculator-v2.html`

## What to do / 做什麼

Turn the BMI calculator into a **trilingual** app. The captain picked these three languages:

1. **English** (default on first visit)
2. **繁體中文（台灣）** — Taiwan usage: 軟體 not 軟件, 影片 not 視頻, 資訊 not 信息
3. **日本語**

**Scope — every visible string switches together:**
- Header title + subtitle
- Labels (`Height 身高` → `身長` in Japanese), unit hints (cm / kg stay as-is)
- Calculate button
- "Your BMI / 您的數值" caption
- All four WHO categories, in all three languages
- The reference table (thresholds + category names)
- All error messages: empty input, non-numeric, and the v2 range checks
- The quick-test row label

Note the current v2 strings are bilingual (`Height 身高`). In v3 each language shows **only its own language** — no more mixed strings.

## Language switcher / 語言切換

- Three small buttons in the card header: **EN / 繁中 / 日語**
- Active language visually highlighted (reuse the existing badge/shortcut button styling)
- **Remember the choice** in `localStorage` — on reload, restore it
- First-ever visit → **English** (do not auto-detect the browser)
- Changing language applies **immediately**, keeping any already-computed result on screen (the BMI number and its category must re-translate too, not stay in the old language)
- Set `<html lang>` correctly per language (`en`, `zh-Hant`, `ja`)

**How to implement:** one translations object keyed by language, all UI text pulled from it — **no duplicated markup per language**.

## Format / 格式

- **New file**, never overwrite: `workspace/outbox/20261012-bmi-calculator-v3.html`
- Still single self-contained HTML + CSS + JS, no libraries, no build step, opens by double-click.
- `v1` and `v2` stay untouched on disk.

## What "done" looks like / 怎樣算做完

- Switch to 繁中 → `計算`, `身長`, `體重`, `正常`, and errors are all Chinese; zero leftover English/Japanese strings on screen.
- Switch to 日本語 → `計算`, `身長`, `体重`, `普通` (use natural Japanese BMI wording), errors in Japanese.
- Reload the page → last chosen language is still active.
- Fresh profile / cleared storage → English.
- **All three test cases pass in every language:** 170/65 → **22.5 Normal**, 160/50 → **19.5 Normal**, 170/90 → **31.1 Obese**.
- Range checks still fire: height `1` → error, no result, in the active language.
- Category re-translates when you switch language *after* calculating (result stays visible).
- Handoff line written at the top of the file.

## Rules / 規矩

- Stay inside the project folder. Never delete files. Only add the new `-v3` file.
- Don't modify `v1` or `v2`.
- Save a handoff note as a **new file** in `workspace/outbox/`:
  `workspace/outbox/20261012-bmi-trilingual.md`
  — one line: what you did, what to watch, ready to use or not.
- **Do not commit or push.** The repo is live (`https://github.com/411521307/my-team`); the captain decides when we ship. I'll handle git.
