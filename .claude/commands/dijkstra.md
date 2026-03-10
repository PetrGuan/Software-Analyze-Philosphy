---
description: "Analyze code using the Dijkstra mindset: favor correctness, local reasoning, and explicit control flow. Use when code technically works but is too hard to verify, modify, or trust."
argument-hint: "[file, function, or module to analyze]"
---

# Dijkstra Analysis — Correctness Through Local Reasoning

You are applying the Dijkstra debugging mindset. Your job is to reduce hidden state, implicit control flow, and reasoning burden so that correctness becomes inspectable.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read the code

Read the target file(s). Pay special attention to control flow, mutable state, scope boundaries, and error handling paths.

## Step 2: Measure reasoning burden

For each function or block, answer:
- Can this be understood from top to bottom without jumping elsewhere?
- What must a reader hold in their head to follow this logic?
- How many implicit assumptions live outside the current scope?
- Would a new engineer know which code paths are impossible?

## Step 3: Find hidden assumptions

Identify:
- Ordering dependencies that aren't enforced by the code
- Mutable state shared across scopes
- Implicit nullability or type coercions
- Error paths that silently swallow failures
- "Clever" compression that saves lines but costs clarity

## Step 4: Assess abstraction value

For each abstraction layer:
- Does it reduce complexity or spread it around?
- Does it have a single, testable contract?
- Could the code be simpler without it?

## Step 5: Produce the report

```
## Dijkstra Analysis: [target]

### Reasoning Burden
[What a reader must keep in mind to understand this code]

### Hidden Assumptions
| Assumption | Location | Risk |
|---|---|---|
| [implicit dependency or ordering] | [file:line] | [what breaks if violated] |

### Correctness Issues
[Specific places where correctness is hard to verify]

### Simpler Form
[Concrete refactoring suggestions to make correctness inspectable — explicit branches, narrower scopes, enforced invariants]
```

Prefer explicit branches over clever compression. Prefer narrow scopes over long-lived mutable context. Prefer clear invariants over hopeful sequencing. Reference specific code locations.
