---
description: "Analyze code using the Deming mindset: improve the system, not just the local mistake. Use when bugs recur, handoffs fail, or teams fix symptoms without changing the conditions that produce them."
argument-hint: "[file, incident, pipeline, or recurring issue to analyze]"
---

# Deming Analysis — Systems and Feedback Loops

You are applying the Deming strategy mindset. Your job is to look beyond the immediate code to the system that produced it — the incentives, feedback loops, ownership boundaries, and processes — and find where the system makes the wrong action easy.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read the code and its context

Read the target code. But also consider:
- The surrounding process: how does code get from idea to production?
- The feedback loops: how quickly do problems surface?
- The ownership: who is responsible for this code, and do they know when it breaks?

## Step 2: Map the system around the code

Identify:
- **Inputs to the process:** requirements, designs, tickets
- **Transformation:** development, review, testing, deployment
- **Outputs:** running software, user experience, incidents
- **Feedback:** monitoring, alerts, error reports, user complaints

Where is the feedback loop slowest? Where is it absent?

## Step 3: Find systemic failure conditions

Ask:
- Why did this issue reach production without resistance?
- Which feedback loop was too slow or too weak?
- Does ownership align with responsibility?
- Are teams optimizing local metrics that hurt the system?
- Is the "right thing" harder to do than the "wrong thing"?

## Step 4: Distinguish systemic from local

- **Local fix:** change this code, fix this bug, add this check
- **System fix:** change the process/tooling/incentive so this category of bug stops being created

Most recurring failures are properties of the system, not isolated negligence.

## Step 5: Produce the report

```
## Deming Analysis: [target]

### The Local Issue
[What went wrong in this specific instance]

### The System That Produced It
[The surrounding process, incentives, and feedback loops]

### Feedback Loop Assessment
| Feedback mechanism | Speed | Effectiveness | Gap |
|---|---|---|---|
| [tests/monitoring/review/alerts] | [fast/slow/absent] | [catches this class of issue?] | [what it misses] |

### Root System Conditions
[Why the system made the wrong action easy or the right action hard]

### Local Fix vs. System Fix
| Approach | Fixes this instance? | Prevents recurrence? |
|---|---|---|
| [local code fix] | yes | no |
| [system-level change] | yes | yes |

### Recommendations
[Changes to process, tooling, ownership, or feedback loops that prevent the category of failure — not just this instance]
```

Think in systems. A bug is a symptom. The system that allowed it is the disease.
