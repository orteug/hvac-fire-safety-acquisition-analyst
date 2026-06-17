# Changelog

## v2.0 — 2026-06-17 — ICM Architecture Upgrade

This version applies the Interpretable Context Methodology (ICM) framework from Van Clief & McDermott (arXiv:2603.16021) to the folder architecture. Every structural change is documented in `DESIGN_DECISIONS.md` with its source concept from the paper.

### Added

- `DESIGN_DECISIONS.md` — maps every v1→v2 structural change to its ICM source concept. Read this to understand *why* v2 is structured differently.
- `routing.md` — L1 routing extracted from `rules.md`. Mode triggers, deal type routing, input classification. Read before any session.
- `_modes/screen-mode.md` — explicit L2 task contract for standard deal screens. Output structure, execution sequence, calibration log requirement.
- `_modes/deep-dive-mode.md` — explicit L2 task contract for deep dives. Operator dependency score, financing scenarios, transition risk, deal structure recommendation.
- `_market_data/` folder — time-sensitive intelligence separated from timeless frameworks:
  - `pe-landscape.md` (moved from `reference/`)
  - `valuation-methodology.md` (moved from `reference/`)
  - `deal-structure-playbook.md` (moved from `reference/`)
  - `market-benchmarks.md` (new — multiples and market rates extracted from `industry-benchmarks.md`)
- `reference/hvac-criteria.md` — HVAC-specific screening criteria (seasonal cash flow, EPA 608, maintenance agreement thresholds, technician retention intelligence)
- `reference/fls-criteria.md` — F&LS-specific screening criteria (monitoring book valuation, NICET requirements, AHJ relationships, ITM contract stickiness, inspection contract concentration)
- `reference/shared-criteria.md` — common criteria (renamed from `deal-screening-criteria.md`)
- `_deals/_calibration_log.md` — L4 working file: screen outcomes tracked over time, 30-day follow-up flags, calibration patterns
- `_deals/_patterns.md` — cross-deal pattern tracker: when the same signal appears 2+ times, surfaces here for criteria review

### Changed

- `rules.md` — trimmed to behavioral rules only. Routing logic removed to `routing.md`.
- `examples.md` — updated to include domain-split examples (HVAC-specific and F&LS-specific screens demonstrating the domain criteria in action)
- `README.md` — updated folder structure, setup instructions, and v2 architecture explanation
- `_modes/memo-mode.md` — moved from root to `_modes/` (unchanged content, correct location)

### Removed

- `reference/deal-screening-criteria.md` — replaced by `reference/shared-criteria.md` + `reference/hvac-criteria.md` + `reference/fls-criteria.md`

### Structural Changes Summary

| v1 location | v2 location | Reason |
|-------------|-------------|--------|
| `reference/pe-landscape.md` | `_market_data/pe-landscape.md` | Time-sensitive (L4), not stable constraint (L3) |
| `reference/valuation-methodology.md` | `_market_data/valuation-methodology.md` | Multiples change; timeless framework stays in reference |
| `reference/deal-structure-playbook.md` | `_market_data/deal-structure-playbook.md` | SBA SOP updates quarterly |
| `reference/deal-screening-criteria.md` | `reference/shared-criteria.md` + `hvac-criteria.md` + `fls-criteria.md` | Domain routing — load only relevant criteria |
| `memo-mode.md` (root) | `_modes/memo-mode.md` | Correct layer placement — L2 task contract |
| Routing logic in `rules.md` | `routing.md` | L1 routing separated from L3 behavioral constraints |

---

## v1.0 — 2026-05 — Initial Release

Built as a portfolio piece for the Jeff van Clief Skool community — Weekly Competition #3: The Specialist.

**Structure:**
```
hvac-fire-safety-acquisition-analyst/
├── README.md
├── identity.md
├── rules.md
├── examples.md
├── memo-mode.md
└── reference/
    ├── deal-screening-criteria.md
    ├── industry-benchmarks.md
    ├── red-flags-checklist.md
    ├── pe-landscape.md
    ├── valuation-methodology.md
    ├── qoe-framework.md
    └── deal-structure-playbook.md
```

**What it did well:**
- Clean L0 identity — character and expertise clearly defined
- Memo mode as a trigger — proto-L2 contract pattern
- 90-day currency check for time-sensitive data — correct instinct
- F&LS monitoring book standing rule — real domain edge

**What v2 fixes:**
- Routing logic embedded in rules (L1/L3 mixing)
- No explicit task contracts for screen and deep dive modes (missing L2)
- Time-sensitive data mixed with timeless frameworks in `reference/` (L3/L4 mixing)
- No L4 working layer — no persistent calibration, no cross-deal learning
- Single criteria file for both HVAC and F&LS — domain-specific nuances buried in notes
