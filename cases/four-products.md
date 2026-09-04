# Case — Four Products, 741 Scored Specs

The authors of CIRK apply it to their own work. This is that data, collected on
2026-09-04 from the four repositories at their `dev` HEAD.

**This is dogfooding, not third-party adoption.** All four codebases belong to
the team that wrote the standard. Where the data is unflattering it is reported
anyway — a case study that only confirms its own standard is worth nothing.

Every spec below also carries a DD6 vector; the companion analysis lives in
[the DD6 case](https://github.com/core-618/dd6/blob/main/cases/four-products.md).

---

## The four products

### core618 — shared platform foundation

Reusable Django apps and React/TypeScript packages consumed by every other
product: multi-tenancy, plugin loader, BPMN workflow engine, messaging, dynamic
configuration.

| | |
| --- | --- |
| **Stack** | Python 3.11 · Django 5 · DRF · PostgreSQL + pgvector · Celery · React 19 · Next.js 15 |
| **Started** | 2026-02-28 |
| **Commits** | 773 |
| **Specs · ADRs** | 306 · 73 |
| **Source files** | 2 171 (1 586 Python, 572 TS/TSX) |

Infrastructure: no end users, but changes propagate to four consumers. High `K`
by construction.

### orbit618 — AI-native development governance engine

The product built to enforce this kind of discipline: intake classification,
spec governance, agent execution policy.

| | |
| --- | --- |
| **Stack** | Python 3.11 · Django · DRF · PostgreSQL · React · TypeScript |
| **Started** | 2026-02-14 |
| **Commits** | 425 |
| **Specs · ADRs** | 222 · 30 |
| **Source files** | 1 364 (737 Python, 619 TS/TSX) |

Included deliberately, because it produces the worst number here.

### myastralmap — consumer mobile product

Generated long-form readings with narrated audio, live in the App Store. The
only one of the four with real users and revenue.

| | |
| --- | --- |
| **Stack** | Django · React Native / Expo · Next.js · LLM generation + TTS pipeline |
| **Started** | 2026-02-28 |
| **Commits** | 2 548 |
| **Specs · ADRs** | 471 · 3 |
| **Source files** | 958 (519 Python, 431 TS/TSX) |

### connectus — services marketplace

Started six months after the others, and after CIRK was already in use.

| | |
| --- | --- |
| **Stack** | Planned: Django · PostGIS · React Native |
| **Started** | 2026-08-24 |
| **Commits** | 32 |
| **Specs · ADRs** | 26 · 5 |
| **Source files** | **4** |

**Read that last row before reading connectus's score below.** 26 specs and four
source files: specified but essentially unbuilt. Its perfect rate is worth much
less than it appears.

---

## Scored before the spec closed, or after?

A CIRK vector governs execution — review depth, test requirements, how the
change ships. Assigned after delivery it governs nothing.

| Product | With a vector | Scored at birth | Backfilled | Real |
| ------- | ------------: | --------------: | ---------: | ---: |
| connectus | 26 | 26 | 0 | **100%** |
| myastralmap | 229 | 169 | 60 | 74% |
| core618 | 270 | 86 | 184 | 32% |
| orbit618 | 216 | 29 | 187 | **13%** |
| **Total** | **741** | **310** | **431** | **42%** |

**orbit618 at 13%** — the governance engine adopted CIRK after most of its specs
already existed.

*Method: for each spec file, find the commit that created it, read the file as
it existed then, and check whether the vector was already present. Renamed files
whose creation commit is unreachable are excluded.*

---

## Backfilled scores are biased — and `K` is the exception

310 scored-at-birth vectors against 431 backfilled ones, in the same
repositories:

| Axis | Scored at birth | Backfilled | Delta |
| ---- | --------------: | ---------: | ----: |
| **R** — Review | 2.03 | 2.45 | **+0.43** |
| **C** — Context | 2.03 | 2.21 | +0.18 |
| **I** — Iteration | 1.89 | 1.99 | +0.10 |
| **K** — Integration risk | 1.86 | 1.84 | **−0.02** |

**`K` does not move.** Of the ten axes across CIRK and DD6, it is the only one
hindsight leaves alone.

That is worth dwelling on. Integration risk appears to be assessable equally
well before and after the work — it is a property of where the change lands in
the system, and where it lands is knowable up front. The other three are
properties of *how the work went*, and memory of how it went inflates them.
`R` rises most, which is the expected failure: after delivery, "how much review
did this need" and "how much review did this get" become the same recollection.

### Controlling for the repository

| Repository | n (birth / backfill) | R | K |
| ---------- | -------------------: | - | - |
| core618 | 86 / 184 | 2.13 → **2.70** | 1.98 → 1.99 |
| orbit618 | 29 / 187 | 2.28 → **2.35** | 2.03 → 1.72 |
| myastralmap | 169 / 60 | 1.88 → **2.03** | 1.71 → 1.77 |

`R` rises in all three. `K` has no consistent direction — flat, down, up. The
control confirms both findings.

**Practical consequence:** if you inherit backfilled CIRK vectors, `K` is the
axis you can still trust. `R` is the one to re-derive.

This is also the first measurement supporting the model's own note that
[the vector matters more than the total](../model/cirk.md#important-note) — the
distortion is concentrated in one axis, and a composite score hides exactly
that.

---

## Distribution

Across all 741 vectors:

| Score | Classification | Count |
| ----- | -------------- | ----: |
| 4–5 | Trivial | 63 |
| 6–7 | Simple | 201 |
| 8–9 | Medium | 267 |
| 10–11 | Complex | 192 |
| 12 | Split Required | 18 |

18 specs at 12 out of 741 — a band that says "this should have been two specs"
firing on 2.4% of intakes is roughly what you would hope for. Zero would mean
nobody was honest; eighty would mean the spec discipline had collapsed.

---

## What we could not measure

Whether CIRK scoring reduces rework. We tried: count follow-up `fix:` and
`revert:` commits per spec, split by scored-at-birth versus backfilled. The
result appears to show that scoring up front *triples* rework, which is wrong.

Writing the spec ID into commit messages and scoring intakes up front arrived in
these repositories at the same time. Older specs did get fixed — those fixes
just carry no spec ID and are uncountable. Measuring one discipline through an
instrument that arrived with it is circular, so no number is published here.

The honest fix is forward-looking: make the commit convention a hard gate, let a
cohort age, then compare. Instrumentation, not analysis.

---

## What we would tell an adopting team

1. **Start on day one, or do not count it.** Same team, same period, same
   tooling: connectus 100%, orbit618 13%. The only difference is whether the
   repository predates the discipline.
2. **Do not backfill `R`.** It is the axis hindsight distorts most, and it is
   the axis that decides how much human review a change gets.
3. **Trust inherited `K`.** It survives being assigned late — it describes where
   the change lands, not how the work felt.
4. **Instrument rework before you need it.** We could not prove the model pays
   for itself, because the instrument arrived with the practice.
