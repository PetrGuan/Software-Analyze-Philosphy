# Einstein Mindset — Start From First Principles, Then Run Thought Experiments

> "Make everything as simple as possible, but not simpler."

**Category:** Architecture
**Skill:** `/einstein` — separates real constraints from convention and stress-tests designs

## When to Use

- Inherited conventions are blocking good design
- The team argues from habit instead of necessity
- Architecture decisions need validation against real constraints
- Evaluating whether a dependency or pattern is still justified
- Planning for scale, failure, or major requirement changes

## Core Move

Separate:
- What **must** be true (real constraints)
- What is **merely customary** (inherited patterns)
- What **breaks under changed conditions** (fragile assumptions)

Then run thought experiments: scale, failure, concurrency, latency, adversarial input.

## Diagnostic Questions

- If we rebuilt this today, what would still be necessary?
- Which constraints are real and which are historical artifacts?
- What happens if traffic is 100x higher?
- What happens if the dependency is slow, partial, or unavailable?
- What would the simplest possible solution look like if we only honored proven constraints?

## Output Format

When analyzing with this mindset, produce:

```
First Principles:
  [Facts that cannot be negotiated]

Assumptions to Challenge:
  [Conventions that may be optional — with origin and alternative]

Thought Experiment Results:
  [What fails when conditions are pushed — scale, failure, concurrency]

Recommendations:
  [Remove unnecessary layers, simplify constrained designs, harden against real failure modes]
```

## Anti-Patterns This Catches

- Patterns defended only by precedent ("we've always done it this way")
- Prematurely complex dependency graphs
- Over-engineering for scenarios that won't occur
- Under-engineering for scenarios that will

## Pairs Well With

- **Turing** — Einstein identifies what's necessary, Turing makes it executable
- **von Neumann** — Einstein reasons about design, von Neumann checks machine cost
- **Hamming** — Einstein questions conventions, Hamming questions priorities

## When Not to Over-Apply

- The task is a local fix with genuinely fixed constraints
- Re-deriving fundamentals would cost more than the decision is worth
- The team has already validated the constraints recently
