# ICM v3 Starter Templates

> Drop these into any new Claude Projects repository to start at v3 — no audit/upgrade required.

---

## How to Use

### New repo (starting from zero)

1. Copy `_guardrails/shared/` → your repo's `_guardrails/shared/` (verbatim, no changes)
2. Copy `_guardrails/domain/domain-guardrail-template.md` → your repo's `_guardrails/domain/[your-domain]-guardrails.md` and fill in the TODOs
3. Copy `routing-template.md` → your repo's `routing.md` and fill in the TODOs
4. Copy `_modes/primary-mode-template.md` → your repo's `_modes/[mode-name].md` and fill in the TODOs
5. Copy `_working/` → your repo's `_[working-folder]/` (rename to match your domain: `_deals/`, `_cases/`, `_sessions/`, etc.)
6. Copy `reference/shared-criteria-template.md` → your repo's `reference/shared-criteria.md`
7. Write `identity.md` and `rules.md` for your domain (no templates needed — these are domain-specific)
8. Write `CHANGELOG.md` starting at v1.0 (the version you're about to ship)
9. Update `README.md` with your folder tree

### Existing repo (upgrading to v3)

Read `UPGRADE_GUIDE.md` at the repo root. It documents both tiers with checklists.

---

## What's in Each Template

| File | What it gives you |
|------|------------------|
| `_guardrails/shared/` | Portable shared guardrails — copy verbatim, no changes |
| `_guardrails/domain/domain-guardrail-template.md` | Domain-specific additions scaffold |
| `routing-template.md` | routing.md with Step 0–4 pre-wired, domain TODOs |
| `_modes/primary-mode-template.md` | 11-section output contract with guardrail hooks |
| `_working/_calibration_log.md` | Pre-formatted calibration log |
| `_working/_patterns.md` | Pre-formatted cross-session patterns tracker |
| `reference/shared-criteria-template.md` | Evaluation criteria scaffold |

---

## What's NOT templated (write per repo)

- `identity.md` — character, expertise, perspective, limits. These are always domain-specific.
- `rules.md` — behavioral rules after routing is extracted. Always domain-specific.
- Domain criteria files — thresholds require domain knowledge.
- `_market_data/` files — content is always domain-specific.
- `examples.md` — domain-specific examples.

---

## The Shared Guardrails Are Canonical

The files in `_guardrails/shared/` are owned by the HVAC & Fire Safety Acquisition Analyst repo — the reference implementation. When those files are updated, propagate to all other repos that have copied them.

**Update signal:** If you modify any `_guardrails/shared/` file in any repo, add a note to that repo's CHANGELOG.md AND update this repo's copy.

*Templates version: v3.0 · Last updated: 2026-06-17*
