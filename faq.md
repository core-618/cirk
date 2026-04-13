# FAQ

## Is CIRK a replacement for story points?

Yes, in AI-assisted development contexts where execution governance matters more than effort estimation.

Story points estimate human effort.
CIRK estimates execution conditions for AI-native workflows.

---

## Does CIRK estimate time?

Not directly.

CIRK is about execution complexity, review intensity, and rollout risk.
Teams may later derive time insights from calibration data, but duration is not the primary output.

---

## Can CIRK be used without coding agents?

Yes.

Even when humans perform the implementation, CIRK still helps classify review burden, context depth, and deployment sensitivity.

---

## Is CIRK tied to Orbit618?

No.

Orbit618 is one possible implementation environment for CIRK, but CIRK is designed as a standalone open standard.

---

## Is CIRK a product?

No.

CIRK is a standard and a shared execution language.
Products and platforms may implement it, but the model itself is implementation-agnostic.

---

## Why not keep story points and add AI rules separately?

Because effort is no longer the most important variable for AI-assisted execution.

CIRK makes the real constraints explicit instead of treating them as side rules.

---

## What is the most important part of CIRK?

The vector, not just the score.

`C3 I1 R1 K3` and `C1 I3 R3 K1` may have the same sum but require very different execution policies.

---

## Why doesn't CIRK include a time dimension?

Time obscures the real constraint. CIRK makes it explicit.

Duration is a byproduct of complexity, iteration depth, review burden, and rollout sensitivity — not an independent variable. Adding time to the model would conflate cause and effect.

Teams that need execution windows can derive them from the vector: high R means longer review cycles, high K means wider rollout windows, high I means more iteration rounds. The vector already encodes the information — time just reads it.

See [why-not-time.md](./why-not-time.md) for the full rationale.

---

## Is CIRK a framework or a standard?

CIRK is a proposed standard — not a framework, not a tool.

It defines a shared language for execution governance. Any team, tool, or platform can implement it. MIT licensed. We are looking for teams willing to test it.

---

## How do I start using CIRK?

Pick a task. Score it across C, I, R, K (1–3 each). Sum the vector. Apply the policy: 4–5 automate, 6–9 require review, 10+ control execution. That's it.

---

## Does CIRK work with Scrum?

Yes. CIRK replaces the estimation layer (story points), not the process.

Sprints, standups, and backlogs stay the same. The difference is that each task carries an execution policy instead of an effort guess.

---

## How does CIRK relate to DD6?

CIRK and DD6 are companion standards.

DD6 classifies the **problem** — how much discovery is needed before spec generation.
CIRK classifies the **execution** — how safely a task can be executed after spec.

They operate at different stages and measure different things. Together they form an end-to-end classification framework for AI-native development.

See [model/dd6-companion.md](./model/dd6-companion.md) for details.

---

## What references support CIRK?

CIRK draws from established frameworks and is validated by emerging industry standards for AI agent governance, including Chip Huyen's *AI Engineering* (O'Reilly, 2025), OWASP Agentic AI Top 10 (2025), NIST AI RMF 1.0, ISO 42001, the Singapore Model Agentic AI Framework (2026), and the EU AI Act.

See [model/references.md](./model/references.md) for the full list.
