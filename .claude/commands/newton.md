---
description: "Analyze code using the Newton mindset: identify forces, state changes, and invariants. Use when state changes feel surprising, or when bugs come from hidden interactions between components."
argument-hint: "[file, module, or stateful component to analyze]"
---

# Newton Analysis — Forces, State, and Invariants

You are applying the Newton architecture mindset. Your job is to model the system as state acted on by forces, and identify the invariants that must hold despite change.

Analyze $ARGUMENTS by following these steps:

## Step 1: Map state

Read the target code. Identify all state:
- Explicit state (variables, database rows, cache entries, session data)
- Implicit state (closure captures, module-level singletons, environment variables)
- Derived state (computed from other state — is it kept in sync?)

## Step 2: Identify forces

For each piece of state, list what can change it:
- User actions
- API calls
- Background jobs / timers
- External system events
- Side effects from other state changes

Treat every mutation as caused, not magical. If you can't name the force, there's a bug hiding.

## Step 3: Define invariants

Identify what must always be true:
- Business rules (e.g., "balance never goes negative")
- Data integrity (e.g., "parent must exist before child")
- Ordering (e.g., "created_at <= updated_at")
- Consistency (e.g., "cache matches source of truth")

For each invariant, check: is it enforced by the code, or just hoped for?

## Step 4: Find violation paths

Look for scenarios where forces can violate invariants:
- Concurrent mutations to the same state
- Cascading side effects with uncontrolled momentum
- Missing guards on state transitions
- Partial failures that leave state inconsistent

## Step 5: Produce the report

```
## Newton Analysis: [target]

### State Map
| State | Location | Mutable by |
|---|---|---|
| [name] | [file:line or system] | [list of forces] |

### Invariants
| Invariant | Enforced? | Risk if violated |
|---|---|---|
| [rule] | [yes/partially/no] | [consequence] |

### Violation Paths
[Specific scenarios where forces can break invariants — include triggering conditions and affected state]

### Recommendations
[Add guards, enforce invariants in code, reduce number of forces acting on shared state, isolate mutations]
```

Focus on the dynamic behavior. Static analysis is useful, but this mindset is about what happens at runtime when forces interact.
