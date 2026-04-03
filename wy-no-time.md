# Why CIRK Does Not Include Time

## The question

> "Where is the time estimate? How do I know when this will be done?"

This is the first question people ask about CIRK.

**CIRK does not estimate time. It defines execution conditions.**

Time becomes a consequence of those conditions — not an input to the model.

This is a deliberate design choice.

---

## The shift

In traditional development, time and effort were nearly interchangeable:

```
time ≈ effort ≈ cost
```

Story points worked because a human writing code was the bottleneck. Estimating how long a person would take to implement something was a reasonable proxy for planning.

In AI-native development, that relationship breaks:

- Code generation is fast.
- Iteration cycles are cheap.
- Execution can be automated.

The bottleneck has moved. It is no longer _"how long does this take?"_ — it is _"how safely can this run?"_

---

## What CIRK measures instead

CIRK captures the four dimensions that actually govern execution:

| Dimension                | Question                                    |
| ------------------------ | ------------------------------------------- |
| **C** — Context          | How much understanding does the agent need? |
| **I** — Iteration        | How many cycles until convergence?          |
| **R** — Review           | How much human validation is required?      |
| **K** — Integration Risk | How risky is rollout?                       |

These are execution constraints. They determine _how_ work runs — not _when_ it finishes.

---

## How time emerges from CIRK

Time is not absent. It is derived.

A task scored `C1 I1 R1 K1` implies:

- No context preparation needed
- One-pass execution
- Minimal review
- Safe rollout

→ **Near-instant delivery.**

A task scored `C3 I2 R3 K3` implies:

- Context must be gathered and structured
- Multiple iteration cycles
- Deep human review required
- Coordinated, staged deployment

→ **Longer execution window — not because the code is hard, but because the governance is heavy.**

The vector tells you _why_ something takes longer. Story points never did.

---

## Why adding time would break the model

If CIRK included a time dimension, two things would happen:

1. **Teams would optimize for time instead of safety.** A task with `R3 K3` might get scored as "2 hours" and shipped without proper review — because the time estimate said it was small.

2. **The model would conflate execution cost with execution risk.** A five-minute code change to a payment webhook is trivially fast to write but catastrophically risky to deploy wrong. Time says "small." CIRK says "supervised."

Time obscures the real constraint. CIRK makes it explicit.

---

## Deriving an Execution Window (optional)

For teams that need a time-adjacent signal — particularly during transition from traditional planning — CIRK vectors can be mapped to an **Execution Window**:

| Vector profile           | Execution window | Why                                    |
| ------------------------ | ---------------- | -------------------------------------- |
| All dimensions ≤ 1       | Minutes          | Autonomous, no gates                   |
| Low R, low K             | Hours            | Fast execution, light review           |
| High I (I3)              | Hours to 1 day   | Iteration cycles add elapsed time      |
| High R (R3)              | +1 day           | Human review is calendar-bound         |
| High K (K3)              | +1–2 days        | Deploy coordination, runbooks, staging |
| Score ≥ 10               | Days             | Multiple approval gates compound       |
| Max vector (C3 I3 R3 K3) | Blocked          | Must decompose before estimating       |

This is not a CIRK output. It is a derived heuristic that teams can calibrate to their own cadence.

> **Rule of thumb:** High R and high K add calendar time — not because the work is large, but because humans and processes are in the critical path.

---

## The mental model

```
Story points:    "How big is this?"        → estimate effort → derive time
CIRK:            "How should this run?"    → define policy  → time emerges
```

CIRK does not ask how long something takes.
It asks what must happen before it is safe to ship.
It asks how free something can run.

---

## FAQ

**"My PM needs a deadline. What do I tell them?"**

Give them an Execution Window derived from the vector. Explain that the window is governed by review and rollout constraints, not code complexity. This is more accurate than story points ever were — because it models the actual bottleneck.

**"Can I track velocity with CIRK?"**

Not in the story-point sense. But you can track throughput by execution mode: how many autonomous tasks shipped this week vs. how many supervised tasks completed. That tells you more about team capacity than a velocity chart.

**"What if my team is not using AI agents?"**

CIRK still works. Even in fully human workflows, the dimensions hold: context depth, iteration likelihood, review burden, and integration risk are real constraints regardless of who writes the code. The execution policies apply the same way.

---

## Summary

|                    | Story Points               | CIRK                     |
| ------------------ | -------------------------- | ------------------------ |
| Primary question   | How much effort?           | How should this execute? |
| Unit               | Abstract effort            | Execution vector         |
| Time               | Estimated directly         | Derived from constraints |
| Optimizes for      | Predictability of duration | Safety of execution      |
| Bottleneck assumed | Human developer            | Governance and review    |

---

_CIRK is an open standard by [Core618](https://core618.com). MIT licensed._
