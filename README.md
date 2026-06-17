# HVAC & Fire Safety Acquisition Analyst
### A Folder-Based AI Specialist for Claude Projects · v2.0

> **Get a structured deal screen on any HVAC or Fire & Life Safety business — in under 5 minutes.**

---

## What This Is

A folder-based AI specialist you drop into a Claude Project. Once it's in, Claude becomes a disciplined acquisition analyst for small HVAC and Fire & Life Safety businesses — the kind of operator-owned trades companies doing $500K–$5M in annual revenue.

This is for **micro-PE operator-buyers**: people who want to own and run a trades business, not flip it.

**It gives you:**
- Structured deal screens with a clear PURSUE / PROCEED WITH CAUTION / PASS verdict
- Domain-specific analysis — HVAC and F&LS have different deal logic and v2 treats them that way
- Ranked risk flags (deal-killers vs. negotiation points)
- Data gap identification before you waste time on bad deals
- Calibrated output grounded in real industry benchmarks
- Deal memory — screens accumulate into a calibration log that makes each subsequent screen more accurate

**v2 vs. v1:** v2 applies the ICM (Interpretable Context Methodology) architecture from Van Clief & McDermott (arXiv:2603.16021). If you want to understand exactly what changed and why, read `DESIGN_DECISIONS.md`. If you just want to screen deals, setup is below.

---

## Setup: 3 Steps

### Step 1 — Create a Claude Project
Go to [claude.ai](https://claude.ai) and create a new Project. Name it something like `Acquisition Analyst — Trades`.

### Step 2 — Upload This Folder
Upload all files from this folder into your Claude Project's knowledge base:

```
hvac-fire-safety-acquisition-analyst/
├── README.md                   ← This file
├── CHANGELOG.md                ← v1 → v2 diff
├── DESIGN_DECISIONS.md         ← Why v2 is structured this way (ICM paper)
├── identity.md                 ← L0: Who the analyst is
├── routing.md                  ← L1: Mode triggers + deal type routing (read first)
├── rules.md                    ← L3: Behavioral rules
├── examples.md                 ← Sample deal screens
├── _modes/
│   ├── screen-mode.md          ← L2: Standard screen execution contract
│   ├── deep-dive-mode.md       ← L2: Deep dive execution contract
│   └── memo-mode.md            ← L2: Investment memo formatter (type "memo")
├── reference/                  ← L3: Stable frameworks (timeless)
│   ├── shared-criteria.md      ← Evaluation thresholds for both domains
│   ├── hvac-criteria.md        ← HVAC-specific criteria
│   ├── fls-criteria.md         ← F&LS-specific criteria
│   ├── industry-benchmarks.md  ← Structural benchmarks (stable)
│   ├── red-flags-checklist.md  ← Ranked flags checklist
│   └── qoe-framework.md        ← Pre-QoE screening tests
├── _market_data/               ← Quarterly refresh (time-sensitive)
│   ├── pe-landscape.md         ← Active PE platforms — check Last Updated date
│   ├── valuation-methodology.md← Current multiples — check Last Updated date
│   └── deal-structure-playbook.md ← SBA structure — check Last Updated date
└── _deals/                     ← L4: Deal memory (update after each screen)
    ├── _calibration_log.md     ← Screen outcomes tracker
    └── _patterns.md            ← Cross-deal pattern tracker
```

> Upload each file individually, or zip the folder and upload the zip.

### Step 3 — Start Analyzing Deals

Open a new conversation inside your Project and paste in what you know about a deal.

**Minimum to get started:**
- Business type (HVAC, Fire Safety, or both)
- Annual revenue
- Asking price
- Owner's role in day-to-day operations
- Rough headcount

That's it. The analyst will tell you what else it needs.

---

## Example Prompt

```
HVAC company in Austin, TX. $1.8M revenue, owner says SDE is around $310K.
Asking $1.1M (3.5x SDE). Owner has been there 18 years and wants to retire
in 12 months. He runs sales but has 3 techs and a dispatcher handling ops.
55% residential, 45% light commercial. About 280 active maintenance agreements.
No single customer over 12% of revenue.

Run a deal screen.
```

---

## Modes

| What you type | What happens |
|---------------|-------------|
| Paste deal data | Standard deal screen — `_modes/screen-mode.md` |
| "deep dive" | Extended analysis with dependency score, financing scenarios, deal structure — `_modes/deep-dive-mode.md` |
| "red flag scan" | Flags only, ranked by severity — no verdict, no strengths |
| "memo" after a screen | Reformats screen as investment memo — `_modes/memo-mode.md` |
| "SBA sanity check" | Does this deal work with SBA 7(a) at 10% down? |
| "benchmark check" | How does this metric compare to industry standards? |

---

## Output Format (Standard Screen)

1. **Deal Summary** — What the business is, in plain terms
2. **Initial Verdict** — PURSUE / PROCEED WITH CAUTION / PASS + one-line rationale
3. **Strengths** — What's working in the deal's favor
4. **Risk Flags** — Ranked: 🔴 Deal-killer → 🟡 Moderate → 🟢 Monitor
5. **Inversion Check** (PURSUE only) — What would have to go wrong? What's the failure mode?
6. **Data Gaps** — What to request before moving forward
7. **PE Competitive Context** — Is this deal visible to PE? What's the timeline implication?
8. **Next Step Recommendation** — Exactly what to do next

---

## Why the Folder Structure Looks Like This

v2 is structured as an **ICM (Interpretable Context Methodology)** — a folder architecture where file *position and type* carry cognitive meaning. The structure is not cosmetic; it determines which context is loaded when.

The key architectural principle: **stable constraints and time-sensitive data are different things. Mixing them degrades output.**

- `reference/` — timeless frameworks. Valid indefinitely.
- `_market_data/` — current market data. Refresh every 90 days.
- `_deals/` — deal memory. Update after every screen.

Read `DESIGN_DECISIONS.md` for the full explanation, mapped to the ICM paper.

---

## What This Analyst Will Not Do

- Replace a formal QoE report
- Provide legal or tax advice
- Speculate without data — it will ask for specifics before evaluating
- Give you "it depends" without a clear framework for what it depends on

---

## Built By

Ariel Ortiz — Founder-Operator  
Acquisition thesis: Micro-PE in Fire & Life Safety and HVAC  
[arielortiz.me](https://arielortiz.me) · [LinkedIn](https://linkedin.com/in/arielortiz)

---

*v1 — May 2026: Initial release (Jeff van Clief Skool community — Weekly Comp #3: The Specialist)*  
*v2 — June 2026: ICM architecture upgrade. See `CHANGELOG.md` and `DESIGN_DECISIONS.md`.*
