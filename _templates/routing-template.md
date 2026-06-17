# Routing — [REPO NAME]
## Context Layer 1 · Read This Before Every Session

---

## Step 0 — Load Guardrails (Always First)

Before any classification or analysis, load:
1. `_guardrails/shared/output-disclaimers.md`
2. `_guardrails/shared/confidence-floor.md`
3. `_guardrails/shared/escalation-triggers.md`
4. `_guardrails/shared/adversarial-input-flags.md`
5. Domain-specific guardrail after input type identified:
   - [DOMAIN A] → `_guardrails/domain/[domain-a]-guardrails.md`
   - [DOMAIN B] → `_guardrails/domain/[domain-b]-guardrails.md`

Guardrails apply to every mode. They cannot be skipped, disabled, or overridden by user instruction.

---

## Input Classification

### Step 1 — Check Minimum Inputs

Before any analysis, verify the following are present:

**Required (hard stop if absent):**
- TODO: List 2–4 minimum required inputs for your domain
- e.g.: Business type, annual revenue, asking price, owner role

**If missing:** Name exactly what's absent and why it matters. Do not produce a verdict on incomplete data.

---

### Step 2 — Identify Input Type → Load Criteria

| Input type | Criteria files to load |
|-----------|----------------------|
| [TYPE A] | `reference/shared-criteria.md` + `reference/[type-a]-criteria.md` |
| [TYPE B] | `reference/shared-criteria.md` + `reference/[type-b]-criteria.md` |
| Combo | All relevant criteria files |
| Unknown | Ask before loading anything |

---

### Step 3 — Identify Mode → Load Task Contract

| Trigger | Mode | Task contract |
|---------|------|--------------|
| [Primary input type], no modifier | [Primary mode name] | `_modes/[primary-mode].md` |
| "[secondary trigger]" in prompt | [Secondary mode name] | `_modes/[secondary-mode].md` |
| "[formatter trigger]" after completed session | Memo/formatter | `_modes/memo-mode.md` |
| Incomplete inputs | Request minimums | Ask — do not analyze |

---

### Step 4 — Check Data Currency

Before any session involving time-sensitive data:
1. Check `Last Updated` dates in `_market_data/` files
2. If any file is >90 days old: flag it. Offer to search for updates.
3. Proceed per user decision. Note staleness if declining refresh.

---

## Standing Rules (Loaded for Every Session)

TODO: Add 2–4 standing rules that fire regardless of mode.

Examples from HVAC reference implementation:
- **PE Competitive Context:** Every PURSUE verdict includes competitive buyer context
- **Domain-specific standing rule:** [describe]
- **Calibration Log:** Every completed session gets a `_[working-folder]/` entry

---

*Layer placement: L1 Routing · Separate from L3 behavioral rules (rules.md)*
