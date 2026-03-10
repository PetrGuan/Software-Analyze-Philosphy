---
description: "Analyze code using the Hamming mindset: focus on the important problem, not the easy one. Use when the team is busy and productive yet the product or architecture isn't meaningfully advancing."
argument-hint: "[file, module, roadmap area, or codebase to analyze]"
---

# Hamming Analysis — Work on What Matters

You are applying the Hamming strategy mindset. Your job is to distinguish urgent from important, visible from high-leverage, and tractable from strategically valuable — then determine whether current work is improving the core system or decorating its edges.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read and understand current work

Read the target code or area. Understand what is actively being built, maintained, or optimized.

## Step 2: Classify current work

For each active area of effort:
- **Urgent or important?** Does it address an immediate need or a fundamental one?
- **Visible or high-leverage?** Is it noticeable to stakeholders or structurally impactful?
- **Tractable or strategically valuable?** Is it being done because it's easy or because it matters?

## Step 3: Identify the important problems being avoided

Look for:
- **Bottleneck problems:** Which single issue, if solved, would unlock or simplify many others?
- **Compounding debt:** What technical debt is accumulating interest fastest?
- **Deferred risks:** What important risk is being postponed because it's hard, uncertain, or lacks clear ownership?
- **Architecture gaps:** Where is local code being polished while structural problems grow?

## Step 4: Assess opportunity cost

What is the team not building because these resources are spent on current work? What would change if the highest-leverage problem were addressed instead?

## Step 5: Produce the report

```
## Hamming Analysis: [target]

### Current Work Classification
| Activity | Type | Leverage |
|---|---|---|
| [what's being done] | [urgent/important/both/neither] | [high/medium/low] |

### The Important Problem
[The highest-leverage problem that isn't being worked on]

### Why It's Being Avoided
[Cost, fear, ownership gap, uncertainty, or lack of visible payoff]

### Bottleneck Analysis
[Which problem, if solved, would simplify the most other problems?]

### Opportunity Cost
[What the team loses by not addressing the important problem]

### Recommendations
[Specific shift in priorities — what to stop, what to start, what to continue. Include a concrete first step for the important problem.]
```

Don't just identify the important problem — explain why it matters more than current work, and give a concrete entry point to start on it.
