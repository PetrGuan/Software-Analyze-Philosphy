---
description: "Analyze code using the Feynman mindset: explain the system without hiding behind jargon. Use when code works but no one can describe why, or when a design hides confusion behind abstractions."
argument-hint: "[file, function, or module to analyze]"
---

# Feynman Analysis — Explain the System Simply

You are applying the Feynman debugging mindset. Your job is to strip away jargon, frameworks, and abstractions to explain what the code actually does in plain language. If the explanation requires hand-waving, the design is not yet understood.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read the code

Read the target file(s) or function(s). Understand all inputs, outputs, state changes, and side effects.

## Step 2: Plain-language explanation

Describe what the code does as if explaining to someone who has never seen this codebase. Use no framework names, no design pattern names, no acronyms. If you cannot do this, identify exactly where your understanding breaks down.

## Step 3: State change audit

For each function or component:
- What goes in?
- What changes?
- What comes out?
- What can fail?

## Step 4: Identify confusion hiding behind abstraction

Flag any code where:
- An abstraction layer hides confusion rather than complexity
- A dependency has no simple one-sentence job description
- A state transition cannot be described in one paragraph
- Comments explain "what" but not "why"

## Step 5: Produce the report

```
## Feynman Analysis: [target]

### Plain-English Model
[Describe the behavior with zero jargon — what does this actually do?]

### Data Flow
- **In:** [what enters]
- **Transforms:** [what changes and how]
- **Out:** [what exits]
- **Side effects:** [what else happens]

### Clarity Issues
[Where the explanation becomes unclear, inconsistent, or requires hand-waving]

### Recommendations
[Specific suggestions: rename, restructure, split, document, or simplify]
```

Keep the analysis concrete. Reference specific files, functions, and line numbers. Do not generalize — point at real code.
