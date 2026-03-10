# Dijkstra Mindset — Favor Correctness, Local Reasoning, and Explicit Control

> "Simplicity is prerequisite for reliability."

**Category:** Debugging
**Skill:** `/dijkstra` — audits code for hidden state, implicit control flow, and reasoning burden

## When to Use

- Code technically works but is too hard to verify, modify, or trust
- Refactoring core business logic
- Reviewing concurrency-sensitive code
- Error handling and resource cleanup feel fragile
- Large utility layers where bugs hide in complexity

## Core Move

Reduce the amount of hidden state and implicit control flow required to understand the code.

Prefer:
- Explicit branches over clever compression
- Narrow scopes over long-lived mutable context
- Clear invariants over hopeful sequencing
- Visible control flow over action-at-a-distance

## Diagnostic Questions

- Can this function be reasoned about from top to bottom without jumping elsewhere?
- What must a reader hold in their head to follow this logic?
- What hidden assumptions live outside the current scope?
- Would a new engineer know which code paths are impossible?
- Is this abstraction reducing complexity or spreading it around?

## Output Format

When analyzing code with this mindset, produce:

```
Reasoning Burden:
  [What a reader must keep in mind]

Hidden Assumptions:
  [Implicit dependencies, ordering requirements, or state expectations]

Correctness Issues:
  [Where correctness is hard to verify]

Simpler Form:
  [How to make correctness inspectable — explicit branches, narrower scopes, enforced invariants]
```

## Anti-Patterns This Catches

- Magic sequencing that only works in one specific order
- Shared mutable state across distant scopes
- Clever one-liners that optimize characters at the cost of clarity
- Error paths that silently swallow failures
- Implicit nullability and type coercions

## Pairs Well With

- **Feynman** — Feynman finds the confusion, Dijkstra structures the fix
- **Newton** — Dijkstra clarifies control flow, Newton maps state dynamics
- **Popper** — Dijkstra makes correctness inspectable, Popper tries to break it

## When Not to Over-Apply

- A terse construct is already obvious and safe
- Maximum explicitness would only add ceremony without reducing risk
- The code is a well-known idiom in its language/framework
