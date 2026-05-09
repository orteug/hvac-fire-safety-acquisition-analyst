# HVAC & Fire Safety Acquisition Analyst
### A Folder-Based AI Specialist for Claude Projects

> **Get a structured deal screen on any HVAC or Fire & Life Safety business — in under 5 minutes.**

---

## What This Is

A folder-based AI specialist you drop into a Claude Project. Once it's in, Claude becomes a disciplined acquisition analyst for small HVAC and Fire & Life Safety businesses — the kind of operator-owned trades companies doing $500K–$5M in annual revenue.

This is for **micro-PE operator-buyers**: people who want to own and run a trades business, not flip it.

**It gives you:**
- Structured deal screens with a clear PURSUE / PROCEED WITH CAUTION / PASS verdict
- Ranked risk flags (deal-killers vs. negotiation points)
- Data gap identification before you waste time on bad deals
- Calibrated output grounded in real industry benchmarks

---

## Setup: 3 Steps

### Step 1 — Create a Claude Project
- Go to [claude.ai](https://claude.ai) and create a new Project
- Name it something like `Acquisition Analyst — Trades`

### Step 2 — Upload This Folder
Upload all files from this folder directly into your Claude Project's knowledge base:

```
hvac-fire-safety-acquisition-analyst/
├── README.md               ← This file
├── identity.md             ← Who the analyst is
├── rules.md                ← How it responds and what it needs
├── examples.md             ← Sample deal screens
├── memo-mode.md            ← Type `memo` after any deal screen to generate an investment memo
└── reference/
    ├── deal-screening-criteria.md    ← Evaluation framework with thresholds
    ├── industry-benchmarks.md        ← HVAC & F&LS benchmarks + SBA financing
    ├── red-flags-checklist.md        ← Ranked flags from deal-killers to monitor
    ├── pe-landscape.md               ← Active PE platforms, deal counts, how to compete
    ├── valuation-methodology.md      ← Multi-method valuation + ARR/MRR layer
    ├── qoe-framework.md              ← Pre-QoE screening tests + trades-specific distortions
    └── deal-structure-playbook.md    ← SBA structure, seller notes, earnout workarounds, closing provisions
```

> Upload each file individually, or zip the folder and upload the zip.

### Step 3 — Start Analyzing Deals
Open a new conversation inside your Project and paste in what you know about a deal.

**Minimum to get started:**
- Business type (HVAC, Fire Safety, or both)
- Annual revenue
- Asking price
- Owner's role in day-to-day operations
- Rough headcount

That's it. The analyst will tell you what else it needs.

---

## Example Prompt to Get Started

```
HVAC company in Austin, TX. $1.8M revenue, owner says SDE is around $310K.
Asking $1.1M (3.5x SDE). Owner has been there 18 years and wants to retire
in 12 months. He runs sales but has 3 techs and a dispatcher handling ops.
55% residential, 45% light commercial. About 280 active maintenance agreements.
No single customer over 12% of revenue.

Run a deal screen.
```

---

## Output You'll Get

Every deal screen includes:
1. **Deal Summary** — What the business is, in plain terms
2. **Initial Verdict** — PURSUE / PROCEED WITH CAUTION / PASS + one-line rationale
3. **Strengths** — What's working in the deal's favor
4. **Risk Flags** — Ranked: 🔴 Critical → 🟡 Moderate → 🟢 Monitor
5. **Data Gaps** — What to request before moving forward
6. **Next Step Recommendation** — Exactly what to do next

---

## Advanced Use Cases

**Deep Dive Mode**
> "Run a deep dive on this deal — include operator dependency score, financing scenario, and deal structure suggestion."

**Red Flag Scan Only**
> "Run a red flag scan on this deal and return only the flags that apply."

**Benchmark Check**
> "How does this business's EBITDA margin compare to industry benchmarks for HVAC?"

**SBA Sanity Check**
> "Does this deal work with SBA 7(a) financing at a 10% down payment?"

---

## Memo Mode

After any deal screen, type `memo` to reformat the output into a structured Investment Screening Memo — cover block, executive summary, financial snapshot, risk register, market context, deal structure, and diligence roadmap.

The memo uses prose for reasoning and tables for data. Each risk flag is written as a full argument, not a compressed bullet. The diligence section is written as conditional logic — what each document unlocks and what a bad result triggers.

Upload `memo-mode.md` to your Claude Project alongside the other files to activate this mode.

---

## What This Analyst Will Not Do

- Replace a formal QoE (Quality of Earnings) report
- Provide legal or tax advice
- Speculate without data — it will ask for specifics before evaluating
- Give you "it depends" without a clear framework for what it depends on

---

## Folder Structure Explained

| File | Purpose |
|------|---------|
| `identity.md` | Who the analyst is — expertise, perspective, limits |
| `rules.md` | How it responds — inputs, output format, behavioral rules, freshness check |
| `examples.md` | Four complete deal screens: Pursue, Caution, Pass, Incomplete Input |
| `memo-mode.md` | Trigger-based investment memo formatter — type `memo` after any deal screen |
| `reference/deal-screening-criteria.md` | Evaluation thresholds — Green / Caution / Red for every category |
| `reference/industry-benchmarks.md` | HVAC and F&LS benchmarks + SBA financing data (2025–2026) |
| `reference/red-flags-checklist.md` | Ranked checklist: deal-killers → negotiate → monitor |
| `reference/pe-landscape.md` | Active PE platforms, what they pay, how an operator-buyer competes |
| `reference/valuation-methodology.md` | Multi-method valuation + separate ARR/MRR valuation layer + worked example |
| `reference/qoe-framework.md` | Five pre-QoE tests + trades-specific earnings distortions |
| `reference/deal-structure-playbook.md` | Asset vs. stock sale, SBA 7(a) (SOP 50 10 8), seller notes, closing protections |

---

## Built By

Ariel Ortiz — Founder-Operator  
Acquisition thesis: Micro-PE in Fire & Life Safety and HVAC  
[arielortiz.me](https://arielortiz.me) · [LinkedIn](https://linkedin.com/in/arielortiz)

---

*Built as a portfolio piece for the Jeff van Cleiff Skool community — Weekly Comp #3: The Specialist*
