# OWASP Cognitive Vulnerability Companion Framework
### Human–Centered Security Layer for LLM Applications

Modern LLM systems do not fail only at the model or infrastructure level.  
They also fail in the **human–AI interaction layer**, where predictable cognitive patterns amplify technical vulnerabilities.

This repository defines a **Cognitive Vulnerability Companion Framework** to the **OWASP Top 10 for LLM Applications**, with a focus on:

- **CV-01 Automation Bias Exploitation**  
- **CV-02 Confirmation Bias Exploitation**  
- A **three-layer Human–Centered Security Architecture**:
  - Model-level cognitive integrity  
  - Interface-level bias countermeasures  
  - Human-level safeguards  

The goal is to provide a structured, OWASP-aligned way to talk about and mitigate cognitive risks in LLM deployments.

---

## Repository structure

- `00-Overview.md`  
  High-level introduction to the framework and its purpose.

- `01-Core-Concepts.md`  
  Core concepts: cognitive vulnerabilities, human–AI interaction risks, and the three-layer HCI model.

- `02-CV01-Automation-Bias.md`  
  Formal definition, detection signals and mitigations for CV-01 Automation Bias Exploitation.

- `03-CV02-Confirmation-Bias.md`  
  Formal definition, detection signals and mitigations for CV-02 Confirmation Bias Exploitation.

- `04-HCI-Architecture.md`  
  The Human–Centered Security Architecture: Model / Interface / Human layers and how they interact.

- `05-Detection-Matrix.md`  
  Detection & mitigation matrix linking signals (e.g. affective congruence, low narrative entropy) to concrete controls.

- `06-Failure-Modes.md`  
  Why single-layer interventions (only model, only UI, only training) are structurally insufficient.

- `07-Future-Bias-Expansion.md`  
  Community-led roadmap for developing additional Cognitive Vulnerabilities (CV-03–CV-10).

- `08-Contribution-Guide.md`  
  How to propose new CV entries, su
