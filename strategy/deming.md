# Deming Mindset — Improve the System, Not Just the Local Mistake

> "Most recurring failures are properties of the system, not isolated negligence."

**Category:** Strategy
**Skill:** `/deming` — analyzes the system around the code to find why the wrong action was easy

## When to Use

- Bugs recur despite fixes
- Handoffs between teams produce errors
- Teams keep fixing symptoms without changing conditions
- Incidents repeat in different forms
- Release pipelines are fragile or inconsistent

## Core Move

Look beyond the bad outcome and map the surrounding system:
- Incentives
- Feedback loops
- Observability
- Release process
- Ownership boundaries

Ask: **why did the system make the wrong action easy?**

## Diagnostic Questions

- Why did this issue reach production without resistance?
- Which feedback loop was too slow or too weak?
- Does ownership align with responsibility?
- Are teams optimizing local metrics that hurt the whole system?
- Is the "right thing" harder to do than the "wrong thing"?

## Output Format

When analyzing with this mindset, produce:

```
The Local Issue:
  [What went wrong in this specific instance]

The System That Produced It:
  [Process, incentives, and feedback loops around the code]

Feedback Loop Assessment:
  [Each feedback mechanism: speed, effectiveness, and gaps]

Root System Conditions:
  [Why the system made the wrong action easy or the right action hard]

Local Fix vs. System Fix:
  [What fixes this instance vs. what prevents the category of failure]

Recommendations:
  [Changes to process, tooling, ownership, or feedback loops]
```

## Anti-Patterns This Catches

- Blaming individuals for systemic failures
- Fixing symptoms without examining the process
- Feedback loops too slow to prevent recurrence
- Ownership boundaries that create accountability gaps
- Local optimizations that degrade the whole system

## Pairs Well With

- **Popper** — Deming maps the system, Popper tests its assumptions
- **Shannon** — Shannon finds signal degradation, Deming finds the system that allows it
- **Hamming** — Deming improves the system, Hamming asks if it's the right system to improve

## When Not to Over-Apply

- The issue is truly isolated and non-recurring
- System redesign would be disproportionate to a one-off defect
- The team has already addressed the systemic factors
