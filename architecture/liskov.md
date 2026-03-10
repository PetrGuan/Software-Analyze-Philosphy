# Liskov Mindset — Design Trustworthy Behavioral Contracts

> "Interfaces are promises about behavior, not just shape."

**Category:** Architecture
**Skill:** `/liskov` — audits substitutability and contract stability in APIs and types

## When to Use

- Implementations share an interface but behave inconsistently
- Refactors break clients unexpectedly
- Inheritance/composition boundaries are unclear

## Core Move

Verify preconditions, postconditions, and invariants across implementations.

## Output Format

```
Contract Surface:
  [interface and clients]

Substitutability Risks:
  [where an implementation violates expectations]

Contract Fixes:
  [tighten/relax clauses, split interfaces]
```
