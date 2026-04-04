OWASP HCI Cognitive Layer

**A research framework for the cognitive attack surface in AI-assisted decision-making.**

> AI systems fail in two ways. The technical layer is well-documented. The human layer is not.

When KAIROS runs autonomously overnight and a security analyst trusts its output without review, that is not a user error. It is a predictable cognitive vulnerability. This framework names, structures, and provides detection tools for that layer.

---

## Why this exists

The OWASP Top 10 for LLM Applications covers what AI systems do wrong technically.

This framework covers what happens in the human brain when those systems are in use.

When a doctor accepts an AI diagnosis without questioning it.
When a security analyst misses an anomaly because the AI said everything was fine.
When a junior developer ships AI-generated code without review.

These failure modes are predictable, repeatable, and currently unnamed in any security standard. EU AI Act Article 14 requires human oversight of high-risk AI systems but does not specify how cognitive failures undermine that oversight in practice. This framework provides that layer.

---

## Start here: Detection Matrix

The **[Detection Matrix](05-Detection-Matrix.md)** is the most operationally useful document in this repository.

It maps cognitive vulnerabilities to observable signals, detection methods, and candidate mitigations. Use it for:

- Risk assessment of AI-assisted workflows
- Designing human oversight mechanisms
- Audit preparation against EU AI Act Article 14

---

## Cognitive Vulnerabilities (CV taxonomy)

| ID | Vulnerability | Status |
|---|---|---|
| CV-01 | Automation Bias Exploitation | v1.0 |
| CV-02 | Confirmation Bias Exploitation | v1.0 |
| CV-03 | Anchoring Bias | In review |
| CV-04 | Cognitive Overload | Proposed |
| CV-05 | Emotional Dysregulation Exploitation | In review |
| CV-06 | Overconfidence Calibration Failure | Proposed |
| CV-07 | Selective Attention Manipulation | Proposed |

Each CV document includes: definition, attack scenario, observable signals, candidate mitigations, and open research questions.

---

## Real-world relevance: KAIROS

In March 2026, a source code leak revealed that Anthropic had built a fully functional autonomous background agent called KAIROS inside Claude Code.

KAIROS runs continuously, rewrites its own memory nightly, and includes an Undercover Mode designed to hide its AI origin in commits and code reviews.

This is not a hypothetical. It is a deployed architecture that activates CV-01 (Automation Bias), CV-03 (Anchoring), and CV-06 (Overconfidence) simultaneously in any team that uses it without awareness.

A governance case study analyzing KAIROS against EU AI Act and GDPR, including a Python governance test suite, is available in the [ai-governance-case-studies](https://github.com/kingchemagnussonhr-sudo/ai-governance-case-studies) repository.

---

## Regulatory alignment

| Framework | Relevant section | How this framework helps |
|---|---|---|
| EU AI Act | Article 14 (Human Oversight) | Cognitive vulnerabilities are the primary mechanism through which Article 14 compliance fails in practice |
| EU AI Act | Article 9 (Risk Management) | CV taxonomy provides structured vocabulary for cognitive risk assessment |
| ISO/IEC 42001 | Section 6.1, 8.4 | Detection and mitigation patterns for human oversight requirements |
| OWASP LLM Top 10 | LLM01, LLM08, LLM09 | Cognitive amplification layer for existing technical risks |

---

## What this is and what it is not

**This is** a research framework. Version 1.0 establishes vocabulary, taxonomy, and detection tools.

**This is not** a deployment standard, compliance checklist, or validated control framework. All mitigations are hypotheses until empirically tested.

Nothing becomes standard until supported by real-world evidence.

---

## Who should use this

| Role | How to use |
|---|---|
| AI Governance and Compliance | Detection Matrix for risk assessment and Article 14 audit preparation |
| Security Architects | Integrate cognitive controls into AI system design |
| UX and Product Teams | Interface-level controls from CV entries |
| Researchers | Contribute new CVs, incident reports, empirical data |
| Red Teams | Cognitive attack scenarios for AI-assisted system testing |

---

## Repository structure

```
/
├── README.md
├── 01-Core-Concepts.md
├── 02-CV-01-Automation-Bias.md
├── 03-CV-02-Confirmation-Bias.md
├── 04-Three-Layer-HCI-Architecture.md
├── 05-Detection-Matrix.md          ← start here
├── 06-Failure-Mode-Analysis.md
├── 07-Community-Expansion-Roadmap.md
└── templates/
    ├── Incident-Report-Template.md
    ├── Mitigation-Testing-Template.md
    └── New-Vulnerability-Proposal-Template.md
```

---

## How to contribute

- Submit an incident report using the template in `/templates/`
- Propose a new CV with supporting evidence
- Run a mitigation pilot and share results
- Review open issues and pull requests

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## Connection to OWASP LLM Top 10

| OWASP LLM | Cognitive amplification |
|---|---|
| LLM01 Prompt Injection | Automation bias causes users to trust injected output |
| LLM02 Insecure Output Handling | Confirmation bias shapes how errors are interpreted |
| LLM08 Excessive Agency | Automation bias reduces oversight of autonomous actions |
| LLM09 Overreliance | Direct manifestation of CV-01 through CV-07 |

---

## License

EUPL-1.2. Open participation, transparent review, evidence-based evolution.

---

## Citation

King Che Magnusson. *OWASP HCI Cognitive Layer: A Research Framework for Cognitive Vulnerabilities in AI-Assisted Decision-Making*. Version 1.0, 2025. GitHub: kingchemagnussonhr-sudo/Owasp-hci-cognitive-layer


