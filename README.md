# OWASP Cognitive Vulnerability Companion Framework  
### Version 1.0 – Research Framework for Human–Centered Security in LLM Systems

---

AI systems fail in two ways. The technical layer is well-documented.  
The human layer is not.

When a doctor accepts an AI diagnosis without questioning it.  
When a security analyst misses an anomaly because the AI said everything was fine.  
When a junior developer ships AI-generated code without review.

These are not user errors. They are predictable cognitive vulnerabilities —  
and no security framework addresses them systematically. Until now.

This framework provides vocabulary, structure, and research tools  
for the cognitive layer of LLM security.
##  Important Positioning: This Is a Research Framework, Not a Deployment Standard

This project is an **open research framework** for understanding, structuring, and validating **cognitive vulnerabilities** that arise in human–AI interaction, especially in systems using LLMs.

It provides conceptual foundations and methodological tools, **not deployment-ready controls**.

### Version 1.0 establishes:

####  Vocabulary and Taxonomy  
A structured language for describing cognitive vulnerabilities (e.g., CV-01, CV-02).

####  Hypothesis-Driven Research Structure  
A scientific workflow for discovery, incident analysis, community review, and evidence-based refinement.

####  Templates for Reporting and Testing  
Standardized formats for:  
- Cognitive vulnerability incident reports  
- Mitigation pilot studies  
- New vulnerability proposals  

---

### Version 1.0 does NOT provide:

####  Validated Mitigation Effectiveness Data  
All proposed mitigation strategies remain hypotheses until real-world testing confirms their reliability.

####  Implementation Requirements  
This framework does not prescribe how organizations *must* implement cognitive safety controls.

####  Compliance Checklists  
No part of this version is intended as a regulatory or audit standard.

**These elements will emerge through community contribution and empirical validation.**

## Who This Framework Is For

| Role | How to use this framework |
|------|--------------------------|
| AI Governance & Compliance | Use Detection Matrix for risk assessment |
| Security Architects | Integrate cognitive controls into AI system design |
| UX / Product teams | Apply Interface-Level controls from CV entries |
| Researchers | Contribute new CVs, incident reports, and empirical data |
| Auditors | Reference EU AI Act Article 14 alignment section |

---

##  Purpose of the Framework

## Regulatory Relevance

**EU AI Act — Article 14: Human Oversight**
Article 14 requires that high-risk AI systems enable human operators
to oversee, understand, and intervene in AI outputs.

Cognitive vulnerabilities are the primary mechanism through which
human oversight fails in practice:

- Automation Bias (CV-01) causes operators to accept outputs
  without sufficient scrutiny
- Confirmation Bias (CV-02) causes operators to miss errors
  that contradict their expectations

This framework provides the cognitive layer that Article 14
compliance requires but does not specify.

**ISO/IEC 42001 — AI Management Systems**
Section 6.1 (Risk assessment) and 8.4 (Human oversight) directly
benefit from the detection and mitigation patterns in this framework.

Modern LLM systems introduce risks that originate not only from technical flaws but also from predictable **cognitive patterns** on the human side of the interaction:

- Automation bias  
- Confirmation bias  
- Cognitive overload  
- Overconfidence  
- Selective attention  
- Misinterpretation of fluent but incorrect outputs  

These cognitive vulnerabilities can amplify or trigger technical vulnerabilities identified in the **OWASP Top 10 for LLM Applications**.

This framework aims to:

1. **Identify** cognitive failure modes that increase LLM security risk  
2. **Document** incidents where human cognition contributed to failure  
3. **Propose** detection signals and candidate mitigations  
4. **Test** them in real deployments  
5. **Validate** outcomes through shared evidence  

The long-term goal is to support safe, reliable, and cognitively sustainable AI systems.

---

##  What’s Included in Version 1.0

### Foundational Documents
- Core Concepts  
- CV-01: Automation Bias Exploitation  
- CV-02: Confirmation Bias Exploitation  
- Three-Layer HCI Security Architecture  
- Detection & Mitigation Matrix  
- Failure Mode Analysis  
- Community Expansion Roadmap  

### Research Infrastructure
- Incident Reporting Template  
- Mitigation Testing Template  
- New Vulnerability Proposal Template  
- Contribution Guide  

This structure enables systematic observation, testing, refutation, and refinement.

---

##  Relationship to OWASP LLM Top 10

This framework complements technical analysis by describing **how human cognition can amplify or fail to detect technical risks**, such as:

| OWASP LLM Top 10 | Cognitive Amplification |
|------------------|-------------------------|
| LLM01 Prompt Injection | Users overtrust output due to CV-01 |
| LLM02 Insecure Output Handling | Confirmation bias (CV-02) shapes interpretation |
| LLM08 Excessive Agency | Automation bias reduces oversight |
| LLM09 Overreliance | Direct manifestation of cognitive vulnerabilities |

Evaluating technical and cognitive layers together provides a more complete risk model.

---

##  Framework Status

### Research Phase (Version 1.0)
This version defines foundational concepts but requires **community evidence** to evolve.

### What Will Emerge Through Community Validation
- Severity classifications for vulnerabilities  
- Risk assessment models  
- Domain-specific implementation guidance  
- Verified mitigation effectiveness  
- Expanded taxonomy (CV-03, CV-04, ...)  

Nothing becomes “standard” until supported by real-world data.

---

##  How to Contribute

We invite practitioners, researchers, and organizations to participate through:

- Submitting incident reports  
- Running mitigation pilot tests  
- Proposing new vulnerabilities  
- Reviewing community submissions  
- Sharing empirical findings  

See **CONTRIBUTING.md** and templates in `/templates/`.

---

##  License & Governance

This project follows OWASP principles:
- Open participation  
- Transparent review  
- Evidence-based evolution  
- Community-driven governance  

---

##  Citation

If referencing this framework:


