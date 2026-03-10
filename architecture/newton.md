# Newton Mindset — Identify Forces, State Changes, and Invariants

> "A system changes because something acts on it."

**Category:** Architecture
**Skill:** `/newton` — maps state, forces, and invariants to find hidden interaction bugs

## When to Use

- State changes feel surprising or hard to trace
- Bugs come from hidden interactions between components
- Stateful UI flows behave inconsistently
- Domain logic has many transitions and edge cases
- Retry loops and cascading side effects cause unexpected behavior

## Core Move

Model the system as:
- **State** — what exists and can change
- **Forces** — what acts on that state
- **Invariants** — what must hold true despite change

Treat every mutation as caused, not magical. If you can't name the force, there's a bug hiding.

## Diagnostic Questions

- What exact event causes this state transition?
- Which components are allowed to mutate this state?
- What invariant must never be violated?
- Where do side effects accumulate more momentum than expected?
- Is derived state kept in sync with its source?

## Output Format

When analyzing with this mindset, produce:

```
State Map:
  [What exists — variables, DB rows, cache entries, session data]

Forces:
  [What can change each piece of state — user actions, API calls, jobs, events]

Invariants:
  [What must remain true before and after — with enforcement status]

Violation Paths:
  [How forces can break invariants — concurrent mutations, cascading effects, partial failures]
```

## Anti-Patterns This Catches

- State mutated by too many forces without coordination
- Invariants enforced by convention instead of code
- Derived state that diverges from its source
- Side effects with uncontrolled cascading momentum
- Missing guards on critical state transitions

## Pairs Well With

- **Dijkstra** — Newton maps the dynamics, Dijkstra structures the control
- **Turing** — Newton identifies the state machine, Turing makes it explicit
- **Popper** — Newton defines invariants, Popper tries to violate them

## When Not to Over-Apply

- The code is stateless and the issue is purely transformational
- The main problem is unclear requirements, not state dynamics
- The system is simple enough that state is obviously correct
