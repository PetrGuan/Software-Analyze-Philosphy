# Lamport Mindset — Reason About Time, Order, and Concurrency

> "Distributed correctness depends on ordering assumptions you can prove."

**Category:** Architecture
**Skill:** `/lamport` — checks happens-before, consistency boundaries, and race-prone flows

## When to Use

- Cross-service events arrive out of order
- Idempotency and retries are inconsistent
- Concurrency bugs are hard to reproduce

## Core Move

Model event order explicitly and validate safety under reordering, retries, and partial failure.

## Output Format

```
Ordering Model:
  [happens-before assumptions]

Race Conditions:
  [where assumptions fail]

Safety Mechanisms:
  [idempotency keys, sequence checks, versioning]
```
