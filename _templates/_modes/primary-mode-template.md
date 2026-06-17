# [Mode Name] — Task Contract
## Context Layer 2 · [Primary Mode] Execution

---

## Trigger

TODO: Describe what input fires this mode.
Example: "Default mode. Fires when [primary input type] is submitted with no mode modifier."

---

## Pre-Execution Checklist (Run Before Output)

- [ ] Guardrails loaded? (`_guardrails/shared/` × 4 + domain file) — if not, load before proceeding
- [ ] Adversarial input flags scanned? Run `adversarial-input-flags.md` against input now
- [ ] Confidence level assessed? (HIGH / MEDIUM / LOW per `confidence-floor.md`)
- [ ] Minimum inputs present? If [KEY VARIABLE A] and [KEY VARIABLE B] both absent: output STOP block, do not proceed
- [ ] Input type identified? ([TYPE A] / [TYPE B] / combo)
- [ ] Domain-specific criteria loaded? (`shared-criteria.md` + type-specific file)
- [ ] Prior sessions in `_[working-folder]/_calibration_log.md` for this case type checked?
- [ ] `_market_data/` files — are any >90 days old? If so, flag before proceeding.

---

## Output Structure

Produce in this order. No deviations.

### 0. Input Integrity Flag (if triggered)
If any adversarial input patterns detected: prepend the `⚠️ INPUT INTEGRITY FLAG` block from `adversarial-input-flags.md` before everything else. If none detected: omit this section entirely.

### 1. [Summary Section]
TODO: 3–5 bullets. Factual only. What is this? Sector, geography, scale, defining characteristic.

### 2. [Primary Verdict / Finding]
One of: TODO — define your verdict options (e.g., PURSUE / CAUTION / PASS, or HIGH / MEDIUM / LOW, or APPROVE / HOLD / DECLINE)

One-line rationale. This is the most important line in the output. Write it as a complete sentence that could stand alone.

Immediately after the verdict line, add:
- Verdict-specific disclaimer from `output-disclaimers.md`
- Confidence level block from `confidence-floor.md` (🟢 / 🟡 / 🔴)

### 3. [Strengths / Positives]
What's working in favor of a positive outcome. Be specific — cite metrics against criteria thresholds.

### 4. [Risk Flags / Concerns]
Ranked by severity:
- 🔴 [CRITICAL] — explain the mechanism of failure, not just the label
- 🟡 [MODERATE] — state the risk and the structural tool that addresses it
- 🟢 [MONITOR] — state what to watch and when it becomes material

### 5. [Inversion Check]
On positive verdict only: name 2–3 specific failure modes for this case. What would have to go wrong? What's the signal that would flag it during follow-up?

### 6. [Data Gaps]
What you'd need to upgrade confidence. Not a generic checklist — specific to this case.

### 7. [Domain-Specific Section]
TODO: Add any domain-specific standing section here.
Example from HVAC: "PE Competitive Context" — is this deal visible to PE buyers?
Example from Praeceptor: "Pattern Recognition" — what's this operator's primary constraint?

### 8. [Domain-Specific Section 2 — if applicable]
TODO: Add second domain-specific section if needed. Otherwise delete.

### 9. Professional Required Block (if triggered)
Check all conditions in `_guardrails/shared/escalation-triggers.md` + domain guardrail file.
If any trigger fires: insert the `🔴 PROFESSIONAL REQUIRED` block here, before Next Step.
If none fire: omit this section entirely.

### 10. Next Step Recommendation
One specific sentence. An action, not a category.

### 11. Disclaimer Block (always)
Append the full disclaimer block from `_guardrails/shared/output-disclaimers.md`. No exceptions.

---

## Session Log Entry (Mandatory After Every Session)

After completing the output, append to `_[working-folder]/_calibration_log.md`:

```
## [YYYY-MM-DD] [Codename/ID] — [Verdict]
- Type: [input type]
- Context: [geography/context/domain]
- Key metrics: [relevant numbers]
- Primary reason for verdict: [one sentence]
- Primary concern(s) if negative: [list]
- Primary strength if positive: [one sentence]
- Data gaps at session time: [list]
- Follow-up date: [30 days from session]
```

---

*Layer placement: L2 Task Contract · Mode-specific · Load only when this mode is active*
