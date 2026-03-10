# von Neumann Mindset — Respect the Cost of State, Memory, and Execution

> "The machine eventually gets a vote."

**Category:** Performance
**Skill:** `/von-neumann` — audits runtime cost of allocation, copying, synchronization, and I/O on hot paths

## When to Use

- Software looks elegant in diagrams but is slow, fragile, or race-prone at runtime
- Performance tuning and profiling
- Concurrency design with shared state
- Large data pipelines processing significant volumes
- High-frequency UI rendering or backend hot paths

## Core Move

Inspect the real operational cost of:
- Mutation and allocation
- Copying and serialization
- Synchronization and locking
- Cache-unfriendly access patterns
- I/O on the critical path

The abstract design is incomplete until the runtime story is clear.

## Diagnostic Questions

- Where is data copied instead of referenced or streamed?
- Which operations scale with input size, and how fast?
- Where does shared mutable state create coordination cost?
- What work is happening on the critical path that doesn't need to be?
- How many objects are allocated per request/per loop iteration?

## Output Format

When analyzing with this mindset, produce:

```
Hot Path:
  [What runs most often or under user-visible latency pressure]

Runtime Cost Inventory:
  [Operation, location, cost type (alloc/copy/IO/sync), frequency, scaling (O(n), O(n²))]

Top Performance Risks:
  1. [Most expensive issue with estimated impact]
  2. [Second issue]
  3. [Third issue]

Recommendations:
  [Batch I/O, stream instead of buffer, eliminate copies, reduce lock scope, precompute, fix data structures]
```

## Anti-Patterns This Catches

- N+1 database queries in loops
- Full-object clones where partial reads suffice
- JSON.parse/stringify in hot loops
- Blocking I/O on async paths
- Unbounded allocation growth with input size
- Locks held across I/O operations

## Pairs Well With

- **Shannon** — von Neumann measures cost, Shannon traces what's being moved
- **Einstein** — von Neumann checks machine reality, Einstein questions design necessity
- **Dijkstra** — von Neumann finds runtime cost, Dijkstra reduces structural complexity

## When Not to Over-Apply

- The system is far from any meaningful performance boundary
- Low-level optimization would distract from a major design flaw
- The code runs rarely and latency is not user-visible
