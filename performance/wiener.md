# Wiener Mindset — Stabilize Feedback and Control Loops

> "Unstable feedback loops create oscillation, delay, and surprising failures."

**Category:** Performance
**Skill:** `/wiener` — analyzes control loops in autoscaling, retries, backoff, and alerting

## When to Use

- Systems oscillate under load
- Retry storms amplify incidents
- Autoscaling and queueing interact poorly

## Core Move

Map feedback loops, delays, and gain; tune for stability before peak throughput.

## Output Format

```
Control Loop Map:
  [signals, controller, actuator]

Instability Sources:
  [delay, overshoot, amplification]

Stability Fixes:
  [damping, bounds, cooldown, backpressure]
```
