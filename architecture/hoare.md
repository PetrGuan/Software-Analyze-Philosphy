# Hoare Mindset — Specify Preconditions, Postconditions, Invariants

> "Clarity comes from explicit conditions, not implied intent."

**Category:** Architecture
**Skill:** `/hoare` — formalizes contracts and proof obligations for critical logic

## When to Use

- Core business functions are fragile
- Edge cases are hard to reason about
- Reviews debate style instead of correctness

## Core Move

Write contracts and check each branch against them.

## Output Format

```
Preconditions:
  [required state]

Postconditions:
  [guaranteed results]

Invariant Checks:
  [must-hold properties]

Violations:
  [where code can break contract]
```
