# Shannon Mindset — Follow the Information and Measure the Noise

> "Communication systems fail when signal degrades faster than people notice."

**Category:** Performance
**Skill:** `/shannon` — traces information flow across boundaries and finds where signal degrades

## When to Use

- Data moves across boundaries and meaning is lost, duplicated, or distorted
- API contracts feel brittle or misunderstood
- Event-driven systems have mysterious behavior
- Logging produces noise instead of signal
- Caching, serialization, or synchronization introduces subtle bugs

## Core Move

Trace the signal:
1. Where is information created?
2. How is it encoded?
3. Where can it be dropped or corrupted?
4. Who consumes it and with what assumptions?

## Diagnostic Questions

- Is this field carrying enough information to reconstruct intent?
- Where do we compress too aggressively and lose semantics?
- Where do logs and errors add noise instead of signal?
- Are multiple systems naming the same thing differently?
- Is error information preserved or flattened to "Something went wrong"?

## Output Format

When analyzing with this mindset, produce:

```
Signal Source:
  [Where truth originates and what it contains]

Encoding Path:
  [source] → [transform] → [boundary] → [consumer]

Signal Degradation:
  [Where ambiguity, duplication, lossy compression, or delay enters — with location and downstream impact]

Naming Inconsistencies:
  [Same concept, different names across the codebase]

Recommendations:
  [Preserve semantics, reduce noise, unify naming, fix error flattening]
```

## Anti-Patterns This Catches

- Lossy encoding at boundaries (datetime → date, enum → string, rich error → boolean)
- Same concept with different names across services
- Duplicated state that diverges over time
- Verbose logging that buries real errors
- Stale cached values consumed as truth

## Pairs Well With

- **von Neumann** — Shannon traces what information flows, von Neumann measures what it costs
- **Feynman** — Shannon finds where meaning is lost, Feynman clarifies what the meaning should be
- **Deming** — Shannon finds signal degradation, Deming finds the system that allows it

## When Not to Over-Apply

- The problem is local computation with no meaningful boundary crossing
- Observability already proves the information path is sound
- The system is a simple CRUD with no encoding transformations
