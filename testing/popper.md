# Popper Mindset — Try to Break the Theory Before Reality Does

> "Strong ideas survive serious attempts to refute them."

**Category:** Testing
**Skill:** `/popper` — extracts claims from code and designs tests to falsify them

## When to Use

- A design sounds convincing but hasn't been tested against failure modes
- Writing test plans for new features or migrations
- Reliability reviews before launch
- Migration and rollout strategy validation
- Incident postmortems to understand what wasn't tested

## Core Move

Write down the claim, then ask what evidence would prove it wrong.

Software claims often look like:
- "This cache is safe"
- "This migration is backward compatible"
- "This retry policy is harmless"
- "This refactor preserves behavior"
- "This lock prevents races"

A claim that cannot be falsified is not a guarantee — it's a wish.

## Diagnostic Questions

- What observation would falsify this assumption?
- Which edge case most threatens the design?
- What failure mode is still untested?
- Are we collecting evidence or just confirming what we already believe?
- Do our tests try to break the code, or only prove it works on happy paths?

## Output Format

When analyzing with this mindset, produce:

```
Claims Extracted:
  [The assumptions the code makes — explicit and implicit]

Falsification Tests:
  [For each claim: what would prove it wrong, and is there a test for that?]

Evidence Gaps:
  [Assumptions with zero tests or monitoring attempting to falsify them]

Recommended Test Cases:
  [Specific tests designed to break assumptions, not confirm them]

Confirmation Bias Patterns:
  [Where the test suite only checks happy paths]
```

## Anti-Patterns This Catches

- Tests that verify success without verifying failure handling
- Error paths never exercised in tests
- Assumptions embedded in test fixtures that mirror production assumptions
- "Works on my machine" confidence without edge case coverage
- Migration safety declared without rollback testing

## Pairs Well With

- **Dijkstra** — Dijkstra makes correctness inspectable, Popper tries to break it
- **Newton** — Newton defines invariants, Popper tries to violate them
- **Turing** — Turing defines the procedure, Popper finds the undefined cases

## When Not to Over-Apply

- The task is exploratory and no stability claim is being made yet
- The cost of falsification exceeds the impact of being wrong
- The code is a prototype not intended for production
