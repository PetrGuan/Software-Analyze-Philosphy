# Feynman Mindset — Explain the System Without Hiding Behind Jargon

> "If you cannot explain it simply, you do not understand it well enough."

**Category:** Debugging
**Skill:** `/feynman` — analyzes code for clarity and explainability

## When to Use

- Code works but no one can describe *why*
- Bug reports have vague root causes
- Architecture diagrams look cleaner than the code behaves
- APIs have many options but unclear defaults
- Review comments rely on buzzwords instead of mechanics

## Core Move

Rewrite the problem in plain language:

1. What goes in?
2. What changes?
3. What comes out?
4. What can fail?

If the answer requires hand-waving, the design is not understood yet.

## Diagnostic Questions

- Can I explain this feature without naming the framework?
- Can I describe the state transition in one paragraph?
- Is this abstraction hiding complexity or hiding confusion?
- Does each dependency have a simple one-sentence job description?
- Could a new team member explain this to a customer?

## Output Format

When analyzing code with this mindset, produce:

```
Plain-English Model:
  [Describe the behavior with zero jargon]

Data Flow:
  In → [what enters]
  Transforms → [what changes and how]
  Out → [what exits]
  Side effects → [what else happens]

Clarity Issues:
  [Where the explanation becomes unclear or inconsistent]

Recommendations:
  [Rename, restructure, split, document, or simplify]
```

## Anti-Patterns This Catches

- Abstractions that hide confusion, not complexity
- Dependencies with no clear job description
- State transitions that take a paragraph to explain
- Comments that explain "what" but never "why"

## Pairs Well With

- **Dijkstra** — Feynman finds the confusion, Dijkstra structures the fix
- **Shannon** — Feynman clarifies intent, Shannon traces where meaning gets lost

## When Not to Over-Apply

- The issue is already fully understood and purely mechanical
- Simplifying the explanation would remove important constraints
- The audience genuinely needs the technical precision
