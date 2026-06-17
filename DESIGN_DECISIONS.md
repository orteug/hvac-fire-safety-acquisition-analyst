# Design Decisions — v2 Architecture
## HVAC & Fire Safety Acquisition Analyst

> This document maps every structural change from v1 to v2 to its source concept in:
> **Van Clief & McDermott, "ICM-Folder-Structure-as-Agentic-Architecture" (arXiv:2603.16021)**
>
> The goal: make this a teaching artifact. Anyone reading this should understand not just *what* changed but *why* — grounded in the paper's framework for building reliable, context-stable AI systems using folder structure as architecture.

---

## The Core Insight from the ICM Paper

The paper argues that Claude Projects (and similar folder-based AI deployments) are not just knowledge bases — they are **Interpretable Context Methodologies (ICMs)**. The folder structure *is* the architecture. Files at different levels serve different cognitive roles. Mixing them degrades output.

The paper identifies five context layers:

| Layer | Role | Should contain |
|-------|------|----------------|
| L0 — Identity | Who the agent is | Fixed character, expertise, perspective |
| L1 — Routing | Where inputs go | Mode triggers, input classification |
| L2 — Task contract | How each task executes | Per-mode execution specifications |
| L3 — Reference (stable) | Stable constraints | Frameworks that don't change per-session |
| L4 — Working (per-run) | Per-session data | Active deal data, session notes, running logs |

v1 mixed these layers throughout. v2 makes each layer explicit.

---

## Decision 1: Split `reference/` into stable and `_market_data/`

**v1 behavior:** All reference files lived in `reference/`. The model had no way to distinguish between a timeless threshold (`red-flags-checklist.md`) and a number that was accurate in May 2026 but may be wrong today (`pe-landscape.md`).

**v2 change:** 
- `reference/` — timeless frameworks only (red flags, QoE framework, evaluation criteria structure)
- `_market_data/` — quarterly-refresh intelligence (PE landscape, current multiples, SBA structure)

**ICM source:** Layer 3 vs. Layer 4 distinction. The paper states that L3 files should be "stable per invocation cycle" — they are constraints, not data. Market intelligence is not a constraint; it is working data that happens to change slowly. Treating it as a constraint allows stale data to contaminate every screen silently.

**What this fixes:** v1 had a built-in staleness problem: the 90-day currency check was a runtime workaround for a structural problem. v2 makes the problem structural: `_market_data/` files have visible `Last Updated` headers and a required refresh cadence. The folder itself signals the category.

---

## Decision 2: Extract routing from `rules.md` into `routing.md`

**v1 behavior:** `rules.md` contained both routing logic (mode triggers, input classification) and behavioral rules (don't inflate, give verdicts, stay in lane). A single file served two distinct cognitive roles.

**v2 change:** 
- `routing.md` — L1 only: mode triggers, deal type routing, input requirements check
- `rules.md` — behavioral rules only: how to reason, what to do when inputs are missing, standing rules

**ICM source:** L1 (routing) and L3 (behavioral constraints) serve different cognitive functions. The paper argues that mixing routing logic with constraint definitions forces the model to hold two different types of context simultaneously — increasing the chance of context collapse where routing behavior bleeds into reasoning behavior or vice versa.

**What this fixes:** In v1, reading `rules.md` required parsing which sections were "do this for this input type" (routing) vs. "always behave this way" (constraint). In v2, mode selection happens in `routing.md` before any reasoning begins.

---

## Decision 3: Create L2 task contracts for each mode

**v1 behavior:** Standard deal screen execution was implied by reading `rules.md`. The output format and execution sequence existed only as prose inside a multi-purpose file. Deep dive mode added sections ad hoc. There was no explicit task contract for how each mode runs.

**v2 change:** 
- `_modes/screen-mode.md` — explicit execution contract for standard screens
- `_modes/deep-dive-mode.md` — explicit execution contract for deep dives (extends screen mode)
- `_modes/memo-mode.md` — moved from root (it was already a proto-L2 contract in v1)

**ICM source:** Context Layer 2 (task contract) is the paper's term for "how this specific task executes." The paper distinguishes L2 from L1 (routing) and L3 (constraints): L2 is mode-specific, loaded only when that mode is active. Loading all modes simultaneously wastes context. Mode-specific L2 contracts also make the system auditable — you can read `screen-mode.md` and know exactly what the analyst will do.

**What this fixes:** v1 produced inconsistent output format across sessions because the execution contract was implied, not explicit. A model starting cold had to infer output structure from examples and partial rules. v2 makes the execution contract unambiguous.

---

## Decision 4: Split deal screening criteria by domain (HVAC vs. F&LS)

**v1 behavior:** One `deal-screening-criteria.md` covered both HVAC and F&LS. Domain-specific nuances (NICET certification, monitoring book valuation, inspection contract stickiness for F&LS; seasonal cash flow, EPA 608, maintenance agreement thresholds for HVAC) were buried in notes at the bottom of shared tables.

**v2 change:**
- `reference/shared-criteria.md` — thresholds that apply to both domains
- `reference/hvac-criteria.md` — HVAC-specific thresholds (loaded only for HVAC deals)
- `reference/fls-criteria.md` — F&LS-specific thresholds (loaded only for F&LS deals)

**ICM source:** The paper's routing principle: "load only the context relevant to the current task." A F&LS screen does not need HVAC seasonal cash flow guidance loaded into context. An HVAC screen does not need NICET certification requirements. Loading both for every screen dilutes the domain-specific signal with irrelevant noise.

**What this fixes:** F&LS deals were systematically underserved in v1 — the monitoring book valuation framework, AHJ relationship assessment, and ITM contract stickiness analysis all existed in notes, not in the evaluation criteria layer. v2 makes F&LS a first-class screening context.

---

## Decision 5: Add L4 working layer (`_deals/`)

**v1 behavior:** No persistent state. Every session started cold. The rural Kentucky deal screen produced real calibration data (51% concentration + sole-technician = reliable deal-killer combination) but that knowledge existed only in the conversation that produced it.

**v2 change:**
- `_deals/_calibration_log.md` — screen outcomes logged after every screen; verdict vs. subsequent diligence outcome tracked
- `_deals/_patterns.md` — cross-deal patterns: when the same signal appears 2+ times, it surfaces here for criteria review

**ICM source:** Context Layer 4 (working/per-run data). The paper argues that the absence of L4 is the most common structural gap in Claude Projects deployments — the system is architected as if every session is the first session. A calibration log converts isolated screens into a compounding intelligence system: each screen makes the next screen more accurate.

**What this fixes:** In v1, the analyst had no way to learn. A threshold that was systematically wrong (too lenient on concentration, too strict on multiple) would fire incorrectly forever with no feedback mechanism. The calibration log is the feedback mechanism.

---

## What Didn't Change

- `identity.md` — v1 was a clean L0. Character, expertise, perspective, limits. No operational logic embedded. No changes needed.
- `examples.md` — updated with domain-split examples but structure unchanged
- The core evaluation framework — the screening criteria, thresholds, and deal structure logic from v1 are preserved. v2 is a structural upgrade, not a content rewrite.

---

## The Meta-Lesson

v1 was built as a knowledge base — a collection of useful files about HVAC/F&LS deal screening.

v2 is built as an ICM — a system where file *position and type* carry meaning, where context is loaded conditionally by mode and deal type, and where every output feeds back into a learning layer.

The content is similar. The architecture is different. The architecture is why v2 produces more consistent, more domain-specific, and more calibrated output than v1 — not because v2 "knows more" but because it is structured to use what it knows more precisely.

---

*Reference: Van Clief & McDermott, "ICM-Folder-Structure-as-Agentic-Architecture" (arXiv:2603.16021)*
*v2 built: 2026-06-17*
