# Screen Mode — Task Contract
## Context Layer 2 · Standard Deal Screen Execution

---

## Trigger

Default mode. Fires when deal data is pasted with no mode modifier.

---

## Pre-Screen Checklist (Run Before Output)

- [ ] Minimum inputs present? If not: name what's missing, stop.
- [ ] Deal type identified? (HVAC / F&LS / combo)
- [ ] Domain-specific criteria loaded? (`shared-criteria.md` + type-specific file)
- [ ] `_config/acquisition-criteria.md` thresholds active?
- [ ] `fls-hvac.md` domain ground truth loaded?
- [ ] Prior screens in `_deals/_calibration_log.md` for this geography/type checked?
- [ ] `_market_data/` files — are any >90 days old? If so, flag before screening.

---

## Output Structure

Produce in this order. No deviations.

### 1. Deal Summary
3–5 bullets. What this business is — sector, geography, scale, defining characteristic. Factual only.

### 2. Initial Verdict
One of: `PURSUE` / `PROCEED WITH CAUTION` / `PASS`

One-line rationale. This is the most important line in the screen. Write it as a complete sentence that could stand alone.

### 3. Strengths
What's working in this deal's favor. Be specific — cite specific metrics against criteria thresholds.

### 4. Risk Flags
Ranked by severity. Use:
- 🔴 DEAL-KILLER — explain the mechanism of failure, not just the label
- 🟡 MODERATE — state the risk and the structural tool that addresses it
- 🟢 MONITOR — state what to watch and when it becomes material

### 5. Inversion Check
On PURSUE only: name 2–3 specific failure modes for this deal (from `_config/acquisition-criteria.md` inversion list). What would have to go wrong? What's the diligence signal that would have flagged it?

### 6. Data Gaps
What you'd need to upgrade confidence. Not a generic checklist — specific to this deal.

### 7. PE Competitive Context
Per standing rule in `rules.md`. Always include.

### 8. F&LS Monitoring Book (if applicable)
Per standing rule in `rules.md`. Include on every F&LS screen.

### 9. Next Step Recommendation
One specific sentence. An action, not a category.

---

## Calibration Log Entry (Mandatory After Screen)

After completing the screen, append to `_deals/_calibration_log.md`:

```
## [YYYY-MM-DD] [Codename] — [Verdict]
- Deal type: [HVAC | F&LS | combo]
- Geography: [city, state]
- Revenue: [value] | SDE: [value] | Asking: [value] | Multiple: [value]
- Primary reason for verdict: [one sentence]
- Deal-killer(s) if PASS: [list]
- Primary strength if PURSUE: [one sentence]
- Data gaps at screen time: [list]
- Domain library flag: [Y/N — if Y, note what to add to fls-hvac.md]
- Follow-up date: [30 days from screen]
```

---

## PURSUE → Route to 03_warwick

If verdict is PURSUE, append the Acquisition Routing Flag block from `CLAUDE.md` to the output before returning to COO.
