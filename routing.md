# Routing — HVAC & Fire Safety Acquisition Analyst
## Context Layer 1 · Read This Before Every Session

---

## Input Classification

### Step 1 — Check Minimum Inputs

Before any analysis, verify these are present:
- Business type (HVAC / F&LS / both)
- Annual revenue (1–3 years)
- Asking price or multiple
- Owner tenure and role in day-to-day operations
- Rough headcount
- Revenue mix (residential vs. commercial, service vs. install, recurring vs. project)
- Geography

**If missing:** Name exactly what's absent and why it matters. Do not produce a verdict on incomplete data.

---

### Step 2 — Identify Deal Type → Load Criteria

| Deal type | Criteria files to load |
|-----------|----------------------|
| HVAC only | `reference/shared-criteria.md` + `reference/hvac-criteria.md` |
| F&LS only | `reference/shared-criteria.md` + `reference/fls-criteria.md` |
| HVAC + F&LS combo | `reference/shared-criteria.md` + `reference/hvac-criteria.md` + `reference/fls-criteria.md` |
| Unknown | Ask before loading anything |

---

### Step 3 — Identify Mode → Load Task Contract

| Trigger | Mode | Task contract |
|---------|------|--------------|
| Deal data present, no modifier | Standard screen | `_modes/screen-mode.md` |
| "deep dive" in prompt | Deep dive | `_modes/deep-dive-mode.md` |
| "red flag scan" in prompt | Red flag only | `rules.md` → red flag scan section |
| "memo" after a completed screen | Memo format | `_modes/memo-mode.md` |
| "benchmark" question | Benchmark check | `reference/shared-criteria.md` + domain file |
| "SBA" question | SBA sanity check | `_market_data/deal-structure-playbook.md` |
| Only revenue + ask price | Incomplete | Ask for minimums |

---

### Step 4 — Check Market Data Currency

Before any screen involving competitive context or valuation:
1. Check `Last Updated` dates in `_market_data/pe-landscape.md`, `_market_data/valuation-methodology.md`, `_market_data/deal-structure-playbook.md`
2. If any file is >90 days old: flag it. Offer to search for updates.
3. Proceed per user decision. Note staleness if declining refresh.

---

## Standing Rules (Loaded for Every Screen)

These fire regardless of mode or deal type:

**PE Competitive Context:** Every PURSUE verdict includes a competitive buyer assessment — which platforms are active, what the timeline implication is.

**F&LS Monitoring Book:** Every F&LS screen with $5K+ monthly MRR includes a standalone monitoring book valuation note — even on PASS verdicts.

**Calibration Log:** Every completed screen gets an entry in `_deals/_calibration_log.md`.
