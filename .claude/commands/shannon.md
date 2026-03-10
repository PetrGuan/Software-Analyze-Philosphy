---
description: "Analyze code using the Shannon mindset: trace information flow and measure noise. Use when data crosses boundaries and meaning gets lost, duplicated, delayed, or distorted."
argument-hint: "[file, API, pipeline, or data flow to analyze]"
---

# Shannon Analysis — Information Flow and Signal Integrity

You are applying the Shannon performance mindset. Your job is to trace how information moves through the system, and find where signal degrades — through lossy encoding, noisy channels, ambiguous naming, or missing context.

Analyze $ARGUMENTS by following these steps:

## Step 1: Identify the signal

Read the target code. Answer:
- Where is the source of truth? (Where is information created or received?)
- What is the essential information content? (What must be preserved?)
- Who are the consumers? (What code uses this information and with what assumptions?)

## Step 2: Trace the encoding path

Follow the information from source to consumer:
- How is it represented at each stage? (types, formats, structures)
- Where is it transformed, serialized, or re-encoded?
- Where does it cross a boundary? (function, module, service, network, storage)

## Step 3: Find signal loss

At each boundary crossing, check:
- **Lossy compression:** Is semantic information discarded? (e.g., datetime → date, enum → string, error → boolean)
- **Noise injection:** Is irrelevant data added? (e.g., verbose logging that buries real errors, wrapper objects that obscure content)
- **Ambiguity:** Do different systems name the same thing differently? (e.g., `userId` vs `user_id` vs `accountId`)
- **Duplication:** Is the same information stored in multiple places that can diverge?
- **Delay:** Is information stale by the time it's consumed? (cached values, async propagation)

## Step 4: Assess channel capacity

- Is the system transmitting more data than necessary?
- Are there bottlenecks where information queues and backs up?
- Is error information preserved or flattened? (e.g., rich errors collapsed to "Something went wrong")

## Step 5: Produce the report

```
## Shannon Analysis: [target]

### Signal Source
[Where truth originates and what it contains]

### Information Flow
[source] → [transform] → [boundary] → [transform] → [consumer]

### Signal Degradation Points
| Location | Type | What's lost | Impact |
|---|---|---|---|
| [file:line] | [lossy/noise/ambiguity/duplication/delay] | [specific information] | [downstream effect] |

### Naming Inconsistencies
[Same concept, different names across the codebase]

### Recommendations
[Preserve semantics across boundaries, reduce noise, unify naming, eliminate redundant copies, fix error flattening]
```

Focus on concrete information loss. "The API returns a generic error" is better than "error handling could be improved."
