# 00: Overview:  HCI Cognitive Layer

---

AI systems do not only fail technically. They fail at the boundary between the system and the human who is supposed to oversee it. A radiologist approves a diagnosis she does not understand. An officer acts on a risk score he cannot challenge. An analyst misses an anomaly because the system did not flag it. None of these are software bugs. The systems worked as designed. The failures happened in the interaction layer, and that layer is not covered by existing security frameworks.

HCI Cognitive Layer defines that layer.

---

**If you are a security auditor**, you have tools for technical risk. You do not have tools for what happens when a well-calibrated system meets an operator under time pressure, with no structured way to challenge the output in front of them. This framework gives you a classification system for those failure modes: observable, testable, and mappable to your existing audit processes.

**If you are a developer**, you have built a system that signals uncertainty correctly and rarely hallucinates. Your benchmarks look good. And yet users overtrust it, miss the warning signals, and delegate decisions the system was never designed to make. Technical correctness is necessary but not sufficient. This framework maps what happens after your model produces its output, and what you can do about it at the model, interface, and organizational level.

**If you are a GRC professional**, EU AI Act Article 14 requires meaningful human oversight. Meaningful is the operative word. An operator rubber-stamping 200 flags per day is not oversight. A risk score that is institutionally difficult to override is not oversight. A system that has built a competence anchor making deviation cognitively costly is not oversight. This framework gives you the vocabulary and the controls to close that gap, mapped against EU AI Act and GDPR.

---

## Definition

**Cognitive Layer Failure**
A failure that occurs when a human operator, interacting with an AI system, produces a decision outcome that deviates from intended oversight due to predictable cognitive mechanisms, despite the system operating within its technical specifications.

**Cognitive Vulnerability**
A predictable, repeatable cognitive pattern that amplifies the effect of a technical vulnerability, degrades human oversight or judgment, distorts interpretation of AI outputs, or creates new failure pathways unique to human–AI interaction. Cognitive vulnerabilities are treated analogously to software vulnerabilities: they are observable, classifiable, and testable.

---

## Position in the Security Stack

The cognitive layer exists above the technical system layer and below organizational decision outcomes.

| Layer | Focus |
|---|---|
| Technical Layer | Model behavior, data integrity, system security |
| **Cognitive Layer** | Human interpretation, trust calibration, decision behavior |
| Organizational Layer | Policy, accountability, governance outcomes |

Failures in the cognitive layer can occur even when the technical layer is functioning as intended.

---

## Scope

The framework focuses on cognitive failure modes in AI-assisted decision-making, including:

- Overreliance on system output despite available contradictory signals
- Failure to detect model uncertainty or limitations
- Reduced verification under time or workload constraints
- System-induced anchoring and confirmation bias
- Delegation of decisions beyond system design intent

These are treated as observable and testable phenomena, not abstract behavioral concepts.

---

## Objective

The objective of this framework is to make cognitive failure modes:

- **Visible**: defined in concrete, non-ambiguous terms
- **Measurable**: testable through structured scenarios and behavioral indicators
- **Auditable**: mappable to controls and regulatory requirements
- **Actionable**: addressable at system, interface, and organizational levels

---

## Vulnerability Taxonomy

The framework classifies cognitive vulnerabilities using the CV prefix. Current vulnerabilities are documented in `/vulnerabilities/`.

| ID | Name | Brief Description |
|---|---|---|
| CV-00 | Adaptive Loop | The foundational risk-generating mechanism: fluency as a continuous trust signal driving confirmation drift and calibration shift |
| CV-01 | Automation Bias | Overreliance on automated outputs, particularly under time pressure or cognitive load |
| CV-02 | Confirmation Bias | Selective acceptance of outputs that align with pre-existing beliefs or expectations |
| CV-03 | Anchoring Bias | Disproportionate reliance on the first piece of information encountered |
| CV-04 | Cognitive Overload | Degraded decision quality when information volume or complexity exceeds cognitive capacity |
| CV-05 | Algorithmic Authority Bias | Deference to AI outputs because the deploying institution carries legitimate authority |

New vulnerabilities are proposed through the contribution process. See `CONTRIBUTING.md`.

---

## Three-Layer Mitigation Architecture

Cognitive vulnerabilities are addressed across three layers. No single layer is sufficient.

**Layer 1: Model Level**
Focus: Inference behavior and uncertainty expression.
Examples: epistemic calibration, forced disagreement sampling, confidence signaling.
Goal: Reduce output characteristics that trigger cognitive failure modes.

**Layer 2: Interface and UX Level**
Focus: How users perceive and interpret AI outputs.
Examples: bias warning indicators, verification friction, counterfactual surfacing.
Goal: Make critical cognitive cues visible and actionable.

**Layer 3: Human and Organizational Level**
Focus: Training, workflows, and decision protocols.
Examples: metacognitive resilience training, structured review procedures, override metrics.
Goal: Strengthen human decision-making where technical and interface controls cannot compensate.

---

## Research Methodology

The framework uses a hypothesis-testing model. Each vulnerability progresses through defined evidence stages:

1. **Propose**: define and describe a cognitive failure pattern
2. **Observe**: collect real-world incident reports
3. **Detect**: map measurable behavioral indicators
4. **Mitigate**: generate candidate mitigations across the three layers
5. **Test**: organizations run pilots and collect outcome data
6. **Classify**: results classified as Hypothesis / Early Evidence / Validated / Refuted
7. **Refine**: integrate validated findings; remove unsupported claims

---

## Relationship to OWASP LLM Top 10

Cognitive vulnerabilities explain how technical risks escalate into real harm.

| OWASP LLM Risk | Cognitive Amplifier |
|---|---|
| LLM01 Prompt Injection | Automation bias reduces operator scrutiny of outputs |
| LLM02 Insecure Output Handling | Confirmation bias shapes selective acceptance |
| LLM08 Excessive Agency | Authority bias and automation bias reduce override behavior |
| LLM09 Overreliance | Direct manifestation of CV-01 and CV-00 |

This framework complements OWASP LLM Top 10 by modeling the human interaction layer that determines whether technical risks become operational harms.

---

## Failure of One-Sided Approaches

Training users not to overtrust AI collapses under cognitive overload. Well-calibrated models cannot protect against users who ignore or misinterpret signals. Warnings without underlying model support become noise.

A coordinated three-layer approach is required because each layer compensates for the limits of the others.

---

## Relationship to Regulatory Requirements

| Regulation | Article | Cognitive Layer Relevance |
|---|---|---|
| EU AI Act | Art. 14 | Human oversight must be meaningful; cognitive vulnerabilities determine whether it is |
| EU AI Act | Art. 13 | Transparency requirements must account for how outputs are actually interpreted |
| GDPR | Art. 22 | Right to human review is only meaningful if the reviewing human is not cognitively compromised |

---

## How to Contribute

Contribution areas include incident reports, mitigation pilot results, new vulnerability proposals, UX and HCI experiments, cross-domain analysis, and evidence reviews. See `CONTRIBUTING.md` for templates and process.

---

## Status

This is a research framework, not a deployment standard. For the framework to progress toward standardization, community participation must increase, empirical evidence must accumulate, vulnerabilities must demonstrate generalizability, and mitigations must show measurable effectiveness.

Version 1.0 defines the structure. The community will determine the content.
