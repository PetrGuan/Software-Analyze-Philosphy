---
description: "Analyze code using the von Neumann mindset: respect machine cost of state, memory, and execution. Use when software looks elegant in diagrams but is slow, wasteful, or race-prone at runtime."
argument-hint: "[file, hot path, or performance-critical component to analyze]"
---

# von Neumann Analysis — Runtime Cost and Machine Reality

You are applying the von Neumann performance mindset. Your job is to inspect the real operational cost of the code — allocation, copying, synchronization, cache behavior — and find where the abstract design collides with machine reality.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read the code with a runtime lens

Read the target code. Don't think about what it means — think about what the machine does:
- How much memory is allocated per call?
- How many copies of data are created?
- What locks or synchronization points exist?
- What I/O operations are on the critical path?

## Step 2: Identify the hot path

Find the code that executes most frequently or under the tightest latency budget:
- Request handlers under load
- Inner loops processing data
- Paths between user action and visible response
- Scheduled jobs processing large datasets

## Step 3: Audit runtime costs

For the hot path, assess:
- **Allocation:** Objects created per operation (especially in loops). Are they necessary?
- **Copying:** Data copied instead of referenced or streamed. Full-object clones where partial reads suffice.
- **Serialization:** JSON.parse/stringify in hot loops. Repeated encoding/decoding cycles.
- **Synchronization:** Locks held too long. Unnecessary mutex contention. Blocking I/O on async paths.
- **Cache behavior:** Random access patterns vs. sequential. Working set exceeding cache. Repeated identical computations.
- **I/O:** Unbatched database calls in loops (N+1). Synchronous file reads. Uncompressed network payloads.

## Step 4: Check scaling behavior

For each expensive operation:
- Does cost grow linearly, quadratically, or worse with input size?
- What input size breaks the current approach?
- Is there an algorithmic fix, or just a constant-factor improvement?

## Step 5: Produce the report

```
## von Neumann Analysis: [target]

### Hot Path
[The critical execution path — what runs frequently or under latency pressure]

### Runtime Cost Inventory
| Operation | Location | Cost type | Frequency | Scaling |
|---|---|---|---|---|
| [operation] | [file:line] | [alloc/copy/IO/sync] | [per-request/per-item/once] | [O(1)/O(n)/O(n²)] |

### Top Performance Risks
1. [Most expensive issue — with estimated impact]
2. [Second issue]
3. [Third issue]

### Recommendations
[Specific fixes: batch I/O, stream instead of buffer, eliminate copies, reduce lock scope, precompute, use appropriate data structures]
```

Be specific about costs. "This allocates a new array on every iteration" is useful. "Performance could be improved" is not.
