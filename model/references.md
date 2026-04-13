# References

Theoretical foundations and industry context for DD6 and CIRK.

These references are shared across both standards.

---

## Primary references

These directly informed the design of CIRK and DD6.

### Huyen, C. (2025). *AI Engineering: Building Applications with Foundation Models*. O'Reilly Media.

Comprehensive guide to building production AI applications. Key contributions:
- **Compound mistakes** (p.278): agent accuracy drops exponentially with steps (95% per step → 60% over 10 steps). Justifies DD6's proportional discovery.
- **Agent failure modes** (pp.298-300): wrong tool, wrong plan, compound errors. CIRK dimensions map directly to these failure categories.
- **Guardrails architecture** (pp.451-455): input and output guardrails as standard AI engineering pattern.
- **Model router** (pp.456-460): routing queries to different models based on complexity. CIRK's model tier mapping implements this pattern.

### Snowden, D.J. — Cynefin Framework (2007, 2021)

Four complexity domains (Clear, Complicated, Complex, Chaotic) with domain-appropriate response strategies. DD6's depth mapping (Skip, Shallow, Standard, Deep, Emergency) adapts Cynefin's domains specifically for AI-assisted software discovery. Core principle: you must understand the domain before choosing a response.

### OWASP Agentic AI Top 10 (December 2025)

First formal taxonomy of risks specific to autonomous AI agents: goal hijacking, tool misuse, identity abuse, supply chain risks, and more. CIRK's K (Integration Risk) and R (Review) dimensions map directly to several of these categories. DD6's discovery process helps prevent goal hijacking by clarifying intent before execution.

### NIST AI Risk Management Framework 1.0 (January 2023)

Four functions: Govern, Map, Measure, Manage. DD6 operates in the "Map" function (understanding the problem space). CIRK operates in the "Measure" function (quantifying execution risk). Together they span two of the four NIST functions.

### EU AI Act (August 2026 — high-risk obligations)

First enforceable, risk-based AI regulatory regime. Requires documentation, monitoring, traceability, and human oversight for high-risk systems. DD6's discovery audit trail provides traceability. CIRK's R3 and K3 scores can trigger compliance review requirements.

### Singapore Model AI Governance Framework for Agentic AI (IMDA, January 2026)

Government framework structured around four dimensions: risk bounding upfront, human accountability, transparency, ecosystem trust. DD6 aligns with "risk bounding upfront" — classifying the problem before agents act. CIRK aligns with "human accountability" — defining when humans must review agent output.

### McKinsey 2026 AI Trust Maturity Survey (March 2026)

Survey of ~500 organizations: only 30% report governance maturity level ≥ 3; 64% of companies with revenue > $1B reported losses > $1M associated with AI system failures in 2025. Establishes the business case for both DD6 and CIRK.

---

## Related work

> The references below (Related Work section) were identified and mapped with the assistance of AI research. They inform or validate the model and are cited for context, not as endorsement of having read each in full.

### Torres, T. (2021). *Continuous Discovery Habits*. Product Talk.

Cadence-based discovery with hypothesis tracking and Opportunity Solution Trees. Influences DD6's structured session phases and proportional discovery principle.

### Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.

Bounded Contexts and Event Storming as discovery techniques. DD6's Domain depth (D) and Boundary clarity (B) dimensions address DDD's concern about understanding domain boundaries.

### Stacey, R.D. (1996). *Strategic Management and Organisational Dynamics*. Pitman Publishing.

The Stacey Matrix (Agreement × Certainty) for classifying organizational problems. DD6's two-axis nature draws conceptual inspiration from assessing agreement and certainty independently.

### Microsoft Agent Governance Toolkit (April 2026)

Open-source runtime security governance for AI agents. Validates that execution governance (CIRK) and pre-execution classification (DD6) are recognized industry needs.

### ISO/IEC 42001:2023 — AI Management Systems

First certifiable AI management system standard with 38 controls. DD6 and CIRK provide the operational layer ISO 42001 requires at the process level.

### ISO/IEC/IEEE 29148:2018 — Requirements Engineering

Standard for requirements quality and documentation. DD6's discovery output maps to BRS (Business Requirements Specification). CIRK's execution input maps to SRS.

### Adzic, G. (2011, 2012). *Specification by Example* & *Impact Mapping*.

Examples as specifications and WHY→WHO→HOW→WHAT structure for connecting goals to deliverables. DD6's Testability (T) and discovery template phases draw from these approaches.

### Richardson, C. (2026). "Why GenAI-based coding agents are a complex domain in Cynefin."

AI coding agents are inherently complex — consequences only visible through testing. Validates DD6's premise that problem classification must precede agent execution.

### Bühler (2024), Yawson & Goryunova (2025), Cascio (2020), INCOSE (2025), Emerald (2022)

AI Bubbles, Nested Complexity, BANI framework, Pleko framework, VUCA systematic review. Collectively validate multi-dimensional complexity classification and domain-specific adaptations of sense-making frameworks.

---

## Related standards

### CIRK — Execution Classification Model

Companion standard to DD6. Classifies execution risk across four dimensions (Context, Iteration, Review, Integration Risk). Score range 4–12.

Repository: [github.com/core-618/cirk](https://github.com/core-618/cirk)
Website: [cirk.dev](https://cirk.dev)

### DD6 — Deep Discovery Classification Model

Classifies problem complexity across six dimensions (Intent, Domain, Stakeholder, Testability, Precedent, Boundary). Score range 6–18.

Repository: [github.com/core-618/dd6](https://github.com/core-618/dd6)
Website: [dd6.dev](https://dd6.dev)
