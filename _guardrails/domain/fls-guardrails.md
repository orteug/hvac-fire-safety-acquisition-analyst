# F&LS Domain Guardrails
## _guardrails/domain · Load alongside shared/ for Fire & Life Safety deals

> Domain-specific escalation triggers and input flags for Fire & Life Safety acquisitions.
> Load shared/ first, then this file. Both apply.

---

## F&LS-Specific Escalation Triggers

These extend `_guardrails/shared/escalation-triggers.md`. Add to the Professional Required block when conditions are met.

| Condition | Trigger | Required action |
|-----------|---------|----------------|
| NICET certification level not confirmed | Any F&LS deal | Verify NICET levels for all inspectors before LOI |
| AHJ relationships held personally by owner | Any F&LS deal | Formal AHJ introduction before close — not after |
| Monitoring MRR >$5K/mo | Any verdict | CPA to review monitoring contract terms before LOI |
| Active ITM deficiency reports outstanding | Any F&LS deal | Legal review of deficiency liability before LOI |
| Suppression system work in scope | Any F&LS deal | Verify state suppression contractor license — separate from inspection license in many states |

**F&LS monitoring book escalation block addition:**
```
• Monitoring Book (F&LS): This deal includes recurring monitoring revenue.
  Before advancing, have a CPA review the monitoring contracts specifically —
  not just the P&L. Key questions: Are contracts assignable on sale? What is
  the cancellation rate history? Are rates locked or month-to-month? The
  monitoring book may be the most valuable asset in this deal, and its value
  depends entirely on contract quality.
```

**F&LS NICET escalation block addition:**
```
• NICET Certification (F&LS): Verify the NICET certification level of every
  inspector before LOI. NICET II is the minimum for commercial inspection
  credibility. If the owner is the only NICET II or higher tech, you are
  buying a certification that walks out the door at close. Confirm this
  before committing.
```

---

## F&LS-Specific Input Flags

These extend `_guardrails/shared/adversarial-input-flags.md`. Add to the Input Integrity Flag block when patterns are detected.

| Pattern | Flag reason |
|---------|------------|
| "Inspection contracts" described without specifying term length or auto-renewal | Inspection contracts range from month-to-month to 5-year auto-renew. The stickiness value is completely different. |
| Monitoring revenue described without specifying RMR vs. one-time | RMR (recurring monthly revenue) is the valuable part. One-time monitoring fees are not. |
| "Good AHJ relationships" described without naming the AHJs or whether they know a successor | AHJ relationships are personal until they are formally transferred. Unnamed, untransferred relationships are the owner's asset, not the company's. |
| "Compliance-driven customer base" used without inspection contract roster | Compliance drives inspection demand — it does not guarantee that these specific clients will stay with a new owner. Contract roster required. |
| ITM records described as "complete" without specifying format or storage | Paper ITM records in a filing cabinet are not the same as a digital system with client access. Ask how records are stored and accessed. |
