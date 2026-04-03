# CIRK

## Example

**Task:** fix bug in payment calculation

C: 3 | I: 2 | R: 3 | K: 3

→ requires human review + controlled deployment

## AI writes the code. CIRK governs the execution.

**CIRK in one line:**
Define how autonomous a task can be based on **Context, Iteration, Review, and Risk**.

CIRK is an open standard for classifying how AI-assisted software work should be executed.

It does **not** estimate human effort.  
It defines execution conditions for AI-native delivery.

---

## What CIRK replaces

Story points were built to estimate human work.

But in AI-assisted development, the bottleneck is no longer code production. The constraint has shifted to:

- context availability
- convergence through iteration
- required human review
- deployment and integration risk

That is what CIRK models.

---

## The model

Each task is represented as:

```text
[C, I, R, K]
```

- **C — Context**: how much understanding the agent needs
- **I — Iteration**: how many cycles are likely needed to converge
- **R — Review**: how much human validation is required
- **K — Integration Risk**: how risky or sensitive the rollout is

Each dimension is scored from **1 to 3**:

- **1 — Low**
- **2 — Medium**
- **3 — High**

---

## In one sentence

CIRK answers this question:

> How safely can this task be executed?

---

## Why it matters

CIRK turns estimation into execution governance.

It helps teams decide:

- when an agent can run autonomously
- when a human must review the output
- when deployment needs tighter control
- when work should be split before execution

---

## Start here

1. Read [start-here.md](./start-here.md)
2. Review the full model in [model/cirk.md](./model/cirk.md)
3. See copy-paste patterns in [usage/quick-examples.md](./usage/quick-examples.md)
4. Map scores to execution behavior in [usage/policies.md](./usage/policies.md)

---

## Example

```text
Task: Login API
C2 I2 R3 K1
```

Implication:

- agent can prepare implementation
- human review is mandatory
- auto-merge is not allowed

---

## Design principles

CIRK is designed to be:

- **open** — not tied to any vendor or platform
- **simple** — usable by humans and systems
- **governable** — usable as execution policy input
- **adoptable** — usable before any custom tooling exists

---

## Adoption

CIRK is a standard, not a product.

It can be adopted in:

- issue tracking workflows
- agent execution pipelines
- pull request policies
- internal developer platforms
- governance layers such as Orbit618

No specific implementation is required.

---

## Notes

- [Why CIRK does not include time](./why-not-time.md)

---

## Contact

[hello@core618.com](mailto:hello@core618.com)

---

## License

MIT
