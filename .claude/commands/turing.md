---
description: "Analyze code using the Turing mindset: convert vague intent into an explicit, executable procedure. Use when requirements sound reasonable but implementation drifts, branches incorrectly, or loops endlessly."
argument-hint: "[file, workflow, or multi-step process to analyze]"
---

# Turing Analysis — Intent to Procedure

You are applying the Turing architecture mindset. Your job is to verify that code translates intent into an explicit procedure with defined inputs, transitions, termination conditions, and error branches. If a human cannot trace the logic on paper, the machine will surprise you.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read the code

Read the target code. Identify the intended workflow or procedure it implements.

## Step 2: Extract the procedure

Write out the procedure the code implements as an explicit, numbered step list:
1. What are the inputs and preconditions?
2. What happens at each step?
3. What are the branching conditions?
4. How does each branch terminate?
5. What are the postconditions and outputs?

## Step 3: Find gaps

Compare the explicit procedure to the actual code:
- **Undefined cases:** inputs or transitions not handled (what happens with empty input? null? concurrent calls?)
- **Non-termination risks:** loops or recursion without guaranteed exit
- **Hidden state machines:** implicit states that aren't modeled (e.g., a request can be "pending", "processing", "failed", but these aren't explicit)
- **Ambiguous branches:** conditions where behavior depends on implicit ordering or fall-through

## Step 4: Validate termination

For every loop, recursion, and retry:
- Is there a bound?
- What guarantees progress toward termination?
- What happens on the boundary (timeout, max retries, overflow)?

## Step 5: Produce the report

```
## Turing Analysis: [target]

### Intended Procedure
1. [step]
2. [step]
3. [step]
...

### Actual Control Flow
[How the code actually executes — note deviations from intended procedure]

### Undefined Cases
| Input/Condition | What should happen | What actually happens |
|---|---|---|
| [case] | [expected] | [actual or "undefined"] |

### Termination Analysis
| Loop/Recursion | Bound | Progress guarantee | Edge case |
|---|---|---|---|
| [location] | [limit] | [what drives it forward] | [what could stall it] |

### Hidden State Machine
[If applicable: draw the implicit states and transitions the code models without naming them]

### Recommendations
[Make states explicit, add bounds, handle undefined cases, simplify branches]
```

Be precise. Trace actual code paths, not intentions. If the code does something different from what it appears to intend, that's the most important finding.
