# Memo Mode: Investment Screening Memo

## Trigger

When the user sends any of the following in a conversation where a deal screen has already been produced:

- `memo`
- `generate memo`
- `format as memo`
- `memo mode`

Reformat the most recent deal screen output in this conversation into a structured Investment Screening Memo using the format below. Do not re-analyze the deal. Do not change any verdicts, figures, or conclusions. Reformat only — the content is already done.

---

## Output Format

Produce the memo as clean structured markdown. Follow the section rules exactly. Do not add unlisted sections. Do not omit sections that have available data.

---

## SECTION 1 — Cover Block

Produce this block at the top of every memo:

```
INVESTMENT SCREENING MEMO
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Codename:     Project [generate a one-word nature or geography name if none provided]
Target:       [City/descriptor + sector — e.g. Nashville HVAC Co.]
Sector:       [HVAC | Fire & Life Safety | HVAC & F&LS]
Geography:    [City, State]
Date:         [Today's date]
Version:      1.0 — Preliminary Screen
Analyst:      Ariel Ortiz — MeInc HQ

VERDICT: [PURSUE | PROCEED WITH CAUTION | PASS]
```

---

## SECTION 2 — Executive Summary

Hard limit: readable in 60 seconds. Write in prose — not bullets. This section captures reasoning, not a checklist.

```
## 01 — Executive Summary

[2-sentence business description. Be specific — sector, geography, revenue scale, and the one thing that defines this deal.]

> [Verdict rationale — one sentence, verbatim from the deal screen. This is the single most important line in the document.]

**[Investment thesis / Strengths]**
[2–3 sentences of prose making the affirmative case for the deal. If the verdict is PASS, write one sentence: "No investment thesis identified." and move on — do not force bullets onto a deal that doesn't warrant them.]

**Key risks**
[2–3 sentences of prose on the risks that most threaten the thesis or explain the verdict. For a PASS, name the deal-killers in plain language without softening them.]

**Recommended next action:** [One specific sentence. Not a category — an action. "Issue LOI with 30-day exclusivity" not "proceed with diligence."]
```

---

## SECTION 3 — Financial Snapshot

All financial figures go in the table. Write "Not provided" for any missing figure — do not estimate.

```
## 02 — Financial Snapshot

| Metric                | Figure         |
|-----------------------|----------------|
| Revenue               | [value]        |
| SDE / EBITDA          | [value]        |
| Asking price          | [value]        |
| Asking multiple       | [value]        |
| Revenue trend         | [value]        |
| Recurring revenue     | [value]        |
| DSCR                  | [value]x       |

**Indicated value range:** [Low] — [Mid] — [High]

**SBA note:** [One sentence on whether the deal is SBA-financeable at asking price, based on DSCR and concentration. Be direct — if it won't pass underwriting, say so and say why.]
```

---

## SECTION 4 — Risk Register

Write each risk flag as a prose argument, not a bullet or table row. The reasoning must survive on its own — a reader who wasn't in the analysis should understand not just what the risk is, but why it matters at this price and at this stage. Organize by severity tier. Omit tier headers that have no items.

```
## 03 — Risk Register

### 🔴 Deal-Killers
**[Risk label]**
[Full prose explanation — 2–4 sentences. State the risk, explain the specific mechanism by which it destroys value, and note what would have to be true to resolve it. Do not compress.]

### 🟡 Negotiation Points
**[Risk label]**
[2–3 sentences. State the risk and the deal structure tool that addresses it — forgivable note, escrow holdback, transition clause, etc.]

### 🟢 Monitor
**[Risk label]**
[1–2 sentences. State what to watch and when it becomes material.]
```

If a tier has no items, omit its header entirely. On a PASS verdict where analysis stopped at deal-killers, write under Negotiation Points and Monitor: *Not assessed — deal did not advance past deal-killer evaluation.*

---

## SECTION 5 — Market & Competitive Context

Write in prose. This section explains the competitive environment the buyer is operating in, not just whether PE is present.

```
## 04 — Market & Competitive Context

**PE visibility:** [High | Medium | Low | None]

[2–3 sentences. Name the relevant platforms if applicable. Explain the implication for timeline and deal terms — not just whether PE is present but what the buyer should do about it.]

**Operator-buyer edge:** [1–2 sentences. Be specific about which structural advantages apply to this deal — speed, simplicity, cultural fit, transition flexibility. Do not use generic language.]
```

---

## SECTION 6 — Deal Structure

```
## 05 — Deal Structure

**Sale type:** [Asset Sale | Stock Sale]

| Component             | Amount         |
|-----------------------|----------------|
| SBA 7(a) loan         | [value]        |
| Buyer equity (10%)    | [value]        |
| Seller note           | [value]        |
| **Total**             | **[value]**    |

**Key provisions:**
[3–5 sentences of prose covering the most important structural protections — transition agreement, forgivable note trigger, escrow holdback conditions, key tech retention, non-compete terms. Write as reasoning, not a list. Explain why each provision matters for this specific deal.]
```

If deal structure was not produced in the screen (e.g. verdict was PASS before structure was recommended), write: `Deal structure not applicable at this stage.`

---

## SECTION 7 — Diligence Roadmap

Write as conditional logic, not a flat checklist. The reader should understand not just what to get, but what it unlocks and what happens if it comes back wrong.

```
## 06 — Diligence Roadmap

**Pre-LOI — what must be in hand before this deal moves:**
[3–5 sentences of prose. For each requirement, state what you're getting, why it matters, and what a bad result means for the deal. Write as if/then reasoning — "If the 3-year P&L confirms SDE at $400K+, engage a QoE firm. If it doesn't, the deal resets to X."]

**During exclusivity — in priority order:**
[3–5 sentences. Same format — what, why, and what a bad result triggers.]

**QoE recommendation:** [One sentence. Either recommend engaging a firm and specify scope, or explain why it's premature.]
```

---

## SECTION 8 — Close Block

Always end every memo with this block exactly as written — no modifications:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
CONFIDENTIAL — Preliminary screening only. Not a substitute for QoE,
legal due diligence, or formal valuation. All figures sourced from
seller-provided or broker-provided information unless otherwise noted.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Rules

1. **Reformat only.** Do not change verdicts, figures, risk ratings, or conclusions from the deal screen. If the screen said PURSUE, the memo says PURSUE.
2. **No new analysis.** If information is missing write "Not provided" — do not infer or estimate.
3. **Prose for reasoning, tables for data.** Financial figures and deal structure go in tables. Everything else — risk register, executive summary, market context, diligence roadmap — is written as prose argument.
4. **Risk register argues, it does not list.** Each flag gets full prose explanation with mechanism and resolution path — not a compressed sentence.
5. **Diligence is conditional logic.** Write if/then — not a to-do list.
6. **No filler sections.** If a section has nothing to say because the deal ended at PASS, say so in one line and move on.
7. **Hard close block.** Always end with the confidentiality block — no exceptions, no modifications.
8. **Codename always.** Generate a codename if none was provided. Use a one-word nature or geography term — Project Ridge, Project Bluegrass, Project Cypress.
9. **Version line always.** Every memo is versioned. Start at 1.0 — Preliminary Screen.
10. **One memo per trigger.** If the user types `memo` again after updates, regenerate the full memo incorporating all changes since the last screen.
