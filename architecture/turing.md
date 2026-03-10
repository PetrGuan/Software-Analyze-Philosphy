# Turing Mindset — Turn Intent Into an Executable Procedure

> "A good explanation is one that can be carried out step by step."

**Category:** Architecture
**Skill:** `/turing` — verifies that code correctly translates intent into an explicit, terminating procedure

## When to Use

- Requirements sound reasonable but implementation drifts or loops incorrectly
- Workflow engines and multi-step business processes
- Parsers, validators, and format converters
- Multi-step forms and user journeys
- Background jobs with retry policies

## Core Move

Translate the problem into an explicit procedure with:
1. Inputs and preconditions
2. State transitions
3. Termination conditions
4. Error branches

If a human cannot run the logic manually on paper, the machine will surprise you.

## Diagnostic Questions

- What are the exact inputs and outputs?
- Does every branch terminate?
- Is there a hidden state machine here that isn't modeled explicitly?
- Which cases are undefined but currently accepted?
- What guarantees progress toward completion?

## Output Format

When analyzing with this mindset, produce:

```
Procedure:
  1. [Step one]
  2. [Step two]
  3. [Step three]

Termination:
  [How the flow ends successfully or fails cleanly]

Undefined Cases:
  [Inputs or transitions not handled — what should happen vs. what actually happens]

Hidden State Machine:
  [Implicit states and transitions the code models without naming]
```

## Anti-Patterns This Catches

- Implicit state machines never made explicit
- Loops and recursion without guaranteed termination
- Undefined input cases that silently produce wrong results
- Branching logic that diverges from stated requirements
- Retry policies that can retry forever

## Pairs Well With

- **Einstein** — Einstein identifies what's necessary, Turing makes it executable
- **Newton** — Newton finds the state, Turing sequences the transitions
- **Popper** — Turing defines the procedure, Popper finds the cases it doesn't handle

## When Not to Over-Apply

- The issue is conceptual rather than procedural
- A simple data model fix removes the need for procedural complexity
- The code is a straightforward data transformation with no branching
