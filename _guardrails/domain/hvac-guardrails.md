# HVAC Domain Guardrails
## _guardrails/domain · Load alongside shared/ for HVAC deals

> Domain-specific escalation triggers and input flags for HVAC acquisitions.
> Load shared/ first, then this file. Both apply.

---

## HVAC-Specific Escalation Triggers

These extend `_guardrails/shared/escalation-triggers.md`. Add to the Professional Required block when conditions are met.

| Condition | Trigger | Required action |
|-----------|---------|----------------|
| License in owner's name only | Any HVAC deal | State licensing attorney — license transfer timeline before LOI |
| EPA 608 certification not confirmed for technician team | Any HVAC deal | Verify EPA 608 status for every tech before close |
| Fleet >5 vehicles, no fleet service records provided | Any PURSUE or CAUTION | Fleet inspection before close — independent mechanic |
| Residential/commercial split unknown | MEDIUM or HIGH confidence screen | Clarify before LOI — split determines debt service stability |
| Seasonal cash flow model not discussed | Any PURSUE | CPA to build 13-week cash model for Year 1 before LOI |

**HVAC license escalation block addition:**
```
• License Transfer (HVAC): Verify that the HVAC contractor license is
  held by the business entity — not the owner personally. If it's in the
  owner's name only, the business cannot legally operate after close until
  transfer is complete. This can take 60–180 days depending on the state.
  A licensing attorney in the relevant state should confirm the transfer
  process and timeline before you sign anything.
```

---

## HVAC-Specific Input Flags

These extend `_guardrails/shared/adversarial-input-flags.md`. Add to the Input Integrity Flag block when patterns are detected.

| Pattern | Flag reason |
|---------|------------|
| Maintenance agreement count given without specifying active vs. lapsed | Agreement count is meaningless without active status. Ask for the roster with last service dates. |
| "Established routes" described without technician headcount | Routes without headcount could mean one overextended technician. |
| "Seasonal business" used to explain revenue variance without cash model | Seasonality is manageable with the right cash structure. "Seasonal business" without a 13-week model is an explanation, not a plan. |
| Equipment described as "well-maintained" without service records | Self-reported maintenance history. Request fleet logs before relying on asset condition. |
| "Lots of repeat customers" without maintenance agreement count or renewal rate | Repeat customers without contracts are relationships, not revenue. They leave with the owner. |
