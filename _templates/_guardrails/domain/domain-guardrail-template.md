# [Domain] Guardrails
## Context Layer 3 · Domain-Specific Safety Additions

> These are additions to `_guardrails/shared/`. They do not replace shared guardrails.
> Load this file AFTER all 4 shared guardrail files.

---

## Escalation Triggers — [Domain]-Specific

The following conditions trigger the `🔴 PROFESSIONAL REQUIRED` block IN ADDITION TO the shared triggers.

> Reference: `_guardrails/shared/escalation-triggers.md` for the base trigger set and block format.

**How to fill this section:**
Answer these questions for your domain:
1. What licenses/certifications could be personally held by the owner vs. institutionally transferable?
2. What financial figures are self-reported and require professional verification?
3. What contractual liabilities could survive a transaction?
4. What regulatory relationships are personal vs. institutional?
5. What asset conditions require professional inspection before any commitment?

---

**[DOMAIN] Trigger 1: [Name]**

Condition: TODO — describe the condition (e.g., "Primary license held in owner's name and not confirmed as transferable")

Why it escalates: TODO — one sentence on the mechanism (e.g., "License transfer is not automatic in [state/jurisdiction]. Buyer could acquire a business they cannot legally operate.")

---

**[DOMAIN] Trigger 2: [Name]**

Condition: TODO

Why it escalates: TODO

---

**[DOMAIN] Trigger 3: [Name]**

Condition: TODO

Why it escalates: TODO

---

**[DOMAIN] Trigger 4: [Name]**

Condition: TODO

Why it escalates: TODO

---

**[DOMAIN] Trigger 5: [Name]**

Condition: TODO

Why it escalates: TODO

---

## Input Integrity Flags — [Domain]-Specific

The following patterns trigger the `⚠️ INPUT INTEGRITY FLAG` block IN ADDITION TO the shared patterns.

> Reference: `_guardrails/shared/adversarial-input-flags.md` for the base pattern set and block format.

**How to fill this section:**
Ask: What does a one-sided presentation look like in this domain? What does a seller/broker emphasize when they're hiding something? What numbers are always cited in favorable terms but require context to evaluate?

---

**[DOMAIN] Flag 1: [Pattern Name]**

Pattern: TODO — describe the framing pattern (e.g., "X metric cited without Y context that would change its meaning")

What to verify: TODO — what's the verification step (e.g., "Request [document] to confirm [the underlying reality]")

---

**[DOMAIN] Flag 2: [Pattern Name]**

Pattern: TODO

What to verify: TODO

---

**[DOMAIN] Flag 3: [Pattern Name]**

Pattern: TODO

What to verify: TODO

---

**[DOMAIN] Flag 4: [Pattern Name]**

Pattern: TODO

What to verify: TODO

---

**[DOMAIN] Flag 5: [Pattern Name]**

Pattern: TODO

What to verify: TODO

---

*Layer placement: L3 Stable Constraint · Domain-specific additions · Always loaded for [domain] sessions*
