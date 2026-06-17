# Deep Dive Mode — Task Contract
## Context Layer 2 · Extended Deal Analysis

---

## Trigger

Fires when "deep dive" appears in the prompt alongside deal data.

---

## Extends Screen Mode

Complete everything in `screen-mode.md` first. Then add the following sections.

---

## Additional Sections (Deep Dive Only)

### D1. Operator Dependency Score

Score 1–10 across five dimensions. 10 = fully transferable business. 1 = business ceases to exist without owner.

| Dimension | Score | Evidence | Notes |
|-----------|-------|----------|-------|
| Operations | — | — | Can the business run 30 days without owner? |
| Sales | — | — | Who closes new accounts? Who maintains relationships? |
| Technical knowledge | — | — | Is expertise documented or in owner's head? |
| Vendor relationships | — | — | Are supplier terms tied to owner personally? |
| Client relationships | — | — | Do clients know/trust the entity or the person? |

**Composite score:** [total / 50]
- 40–50: Low dependency — acquirable with standard transition
- 25–39: Moderate dependency — structure required (transition period, escrow holdback)
- Below 25: High dependency — likely PASS or heavy structural mitigation required

---

### D2. Financing Scenario

Calculate for the current asking price AND a 10% discount scenario.

| Scenario | Purchase price | SBA loan | Equity injection | Seller note | Debt service / yr | DSCR |
|----------|---------------|----------|-----------------|-------------|-------------------|------|
| At ask | — | — | — | — | — | — |
| At 10% discount | — | — | — | — | — | — |

Notes:
- SBA 7(a): 10-year term at current prime + 2.75% (check `_market_data/deal-structure-playbook.md` for current rate)
- DSCR floor: 1.5× per thesis (vs. SBA's 1.25× minimum)
- If DSCR <1.25× at ask: the deal cannot be SBA-financed at asking price — note explicitly

---

### D3. Transition Risk Assessment

| Risk | Level | Mitigation |
|------|-------|-----------|
| Owner takes top 3 clients | — | — |
| Key tech leaves within 6 months | — | — |
| License transfer delay | — | — |
| SDE normalization post-close | — | — |
| Seasonal cash trough Year 1 | — | — |

For each HIGH or CRITICAL risk: name the deal structure tool that addresses it (forgivable seller note, escrow holdback, extended transition agreement, earn-in provision, etc.)

---

### D4. Deal Structure Recommendation

Based on risk profile from above:

- **Sale type:** Asset Sale (default) or Stock Sale (reason required)
- **SBA structure:** loan amount, term, down payment
- **Seller note:** amount, term, rate, forgivability conditions
- **Escrow holdback:** amount, trigger (client retention, revenue retention, tech retention)
- **Transition agreement:** duration, role, compensation
- **Non-compete:** geography, duration

---

### D5. Platform Optionality

If PURSUE and deal profile fits acquisition thesis:
- Does this business have add-on acquisition potential in the same geography?
- What is the platform multiple at 2–3 company scale vs. single-company multiple?
- Which PE platforms would be interested at platform scale?

---

## Calibration Log Entry

Same format as screen mode, plus:
```
- Deep dive: YES
- Operator dependency score: [composite score]
- DSCR at ask: [value]
- Primary structural mitigation recommended: [one sentence]
```
