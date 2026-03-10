---
description: "Analyze code using the Popper mindset: try to falsify assumptions before reality does. Use when a design sounds convincing but hasn't been tested against failure modes, or when writing test plans."
argument-hint: "[file, feature, or claim to falsify]"
---

# Popper Analysis — Falsify Assumptions

You are applying the Popper testing mindset. Your job is to identify the claims the code makes (explicitly or implicitly) and find what evidence would prove each claim wrong. Strong code survives serious attempts to break it.

Analyze $ARGUMENTS by following these steps:

## Step 1: Read the code and extract claims

Read the target code. Every piece of software makes implicit claims:
- "This input is always valid"
- "This cache is consistent with the source"
- "This retry policy converges"
- "This migration is backward compatible"
- "This refactor preserves behavior"
- "This lock prevents races"

Extract the specific claims this code makes.

## Step 2: Design falsifiers

For each claim, define what observation would prove it wrong:
- What input would violate the validation assumption?
- What timing would break the consistency guarantee?
- What sequence of events would make the retry diverge?
- What client behavior would reveal the migration broke compatibility?

A claim that cannot be falsified is not a guarantee — it's a wish.

## Step 3: Check evidence

For each claim:
- Is there a test that attempts to falsify it?
- Is the test actually rigorous, or does it only confirm the happy path?
- Are edge cases and failure modes exercised?
- Is there monitoring that would detect falsification in production?

## Step 4: Identify confirmation bias

Look for patterns where the codebase only tests that things work, never that they don't:
- Tests that verify success without verifying failure handling
- Error paths that are never exercised
- Assumptions embedded in test fixtures that mirror production assumptions

## Step 5: Produce the report

```
## Popper Analysis: [target]

### Claims Extracted
| # | Claim | Location | Explicit? |
|---|---|---|---|
| 1 | [assumption] | [file:line] | [yes/no — is it documented or just implied?] |

### Falsification Tests
| Claim | Falsifier | Current test coverage | Gap |
|---|---|---|---|
| [claim] | [what would prove it wrong] | [existing test or "none"] | [what's missing] |

### Evidence Gaps
[Assumptions that have zero tests or monitoring attempting to falsify them]

### Recommended Test Cases
[Specific test cases to write — each designed to break an assumption, not confirm it]

### Confirmation Bias Patterns
[Where the test suite only checks happy paths]
```

The goal is not to prove the code works — it's to find where the code might be wrong and hasn't been challenged yet.
