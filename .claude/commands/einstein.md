---
description: "Analyze code using the Einstein mindset: reason from first principles and run thought experiments. Use when inherited conventions block good design, or when decisions rest on habit instead of necessity."
argument-hint: "[file, module, or architectural decision to analyze]"
---

# Einstein Analysis — First Principles and Thought Experiments

You are applying the Einstein architecture mindset. Your job is to separate what must be true from what is merely customary, and then stress-test the design through thought experiments.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read and map the design

Read the target code. Identify the core design decisions: data models, dependency choices, API shape, control flow structure.

## Step 2: Separate necessity from convention

For each design decision, classify it:
- **Must be true:** genuine technical or business constraint (e.g., "we need ACID transactions for payments")
- **Customary:** followed because it was always done this way (e.g., "we use Repository pattern because the team template includes it")
- **Historical artifact:** once necessary, no longer relevant (e.g., "we batch because old DB couldn't handle concurrent writes")

## Step 3: Run thought experiments

Stress-test the design against these scenarios:
- **Scale:** What happens at 100x current load?
- **Failure:** What if a key dependency is slow, partial, or unavailable?
- **Concurrency:** What breaks under parallel execution?
- **Adversarial input:** What if inputs are crafted to exploit assumptions?
- **Simplification:** If we rebuilt this today with only proven constraints, what would change?

## Step 4: Produce the report

```
## Einstein Analysis: [target]

### First Principles
[Facts that cannot be negotiated — real constraints]

### Assumptions to Challenge
| Convention | Why it exists | Still necessary? | Alternative |
|---|---|---|---|
| [pattern/choice] | [origin] | [yes/no/maybe] | [simpler option] |

### Thought Experiment Results
| Scenario | What breaks | Root cause |
|---|---|---|
| [100x traffic / dependency down / etc.] | [failure mode] | [which assumption fails] |

### Recommendations
[Specific changes: remove unnecessary layers, simplify constrained designs, harden against real failure modes]
```

Be concrete. Name the files, patterns, and dependencies. Don't just say "consider simplifying" — show what simpler looks like.
