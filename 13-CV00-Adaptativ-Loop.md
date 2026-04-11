# CV-00: The Adaptive Loop
### Primary Interaction-Level Risk-Generating Mechanism
*OWASP HCI Cognitive Layer*

| | |
|---|---|
| Document ID | CV-00 |
| Status | Draft v2.0 |
| Version | 2.0 |
| Domain | Interaction Dynamics |
| Classification | Risk-generating mechanism (not a vulnerability entry) |
| See also | README: Scope and Positioning; CV-01 through CV-07 |

---

> **Epistemological status note:** CV-00 should be read as a security-oriented synthesis of several convergent mechanisms, not as a fully validated unified construct. The component mechanisms are empirically supported; the loop as a single measurable risk class is a theoretical integration with partial but not yet direct longitudinal validation.

---

## 1. Purpose

This document defines the adaptive loop as the primary interaction-level risk-generating mechanism in the OWASP HCI Cognitive Layer framework. It is not a vulnerability catalogue entry in the same sense as CV-01 through CV-07. It describes the structural dynamic that produces and amplifies the vulnerabilities those documents address.

CV-01 through CV-07 describe what happens to a user's cognition under sustained AI interaction. CV-00 describes the mechanism through which it happens, and why standard epistemic defences are under-scoped to prevent it.

See README: Scope and Positioning for the framework's broader positioning within established cognitive security traditions.

---

## 2. Definition

The adaptive loop is a self-reinforcing dynamic that emerges from sustained, repeated interaction between a user and an AI system. It is characterised by three co-occurring properties.

### Mutual adaptation

The system adjusts its outputs based on the user's inputs; the user adjusts their framing, vocabulary, and query structure based on the system's outputs. Neither party announces this. No single exchange is decisive. This is grounded in established HCI and sociolinguistic research on lexical entrainment (Brennan, 1996) and Communication Accommodation Theory (Giles, 1973), both of which have been replicated in human-computer interaction contexts.

### Cumulative reference frame shift

Over time the shared context narrows. The space of questions that feel worth asking contracts. The space of outputs that feel self-evidently correct expands. This occurs without the user internalising a discrete new belief or narrative that they could subsequently identify and evaluate. The mechanism is consistent with bounded rationality (Simon, 1955): as AI output becomes the primary source of readily available information, it defines the effective boundaries of the user's decision space.

### Metacognitive invisibility

Because each exchange is locally reasonable and the shift is incremental, the loop operates below the threshold at which standard metacognitive monitoring triggers. The user does not experience drift. The user experiences accumulated familiarity. This is explained mechanistically by processing fluency effects (Reber and Schwarz, 1999): increased fluency of AI output over repeated sessions is interpreted by the cognitive system as a signal of correctness and trustworthiness, suppressing System 2 evaluation (Kahneman, 2011). The Illusion of Explanatory Depth (Rozenblit and Keil, 2002) describes the closely related tendency to mistake growing familiarity with an AI's reasoning for genuine understanding and control.

---

## 3. Boundary Conditions

The adaptive loop is a specific form of human-AI co-adaptation. Not all adaptation is security-relevant. The loop becomes a risk-generating mechanism when the following conditions are met:

- Shared context becomes more stable than evidential review. The user relies on the established interaction context rather than seeking external verification of AI outputs.
- Local coherence outcompetes external verification. The internal consistency of the AI-user dialogue feels more informative than comparison against independent sources.
- Query generation space measurably narrows over time. The user asks fewer questions that challenge the established framing, and more questions that extend it.
- Metacognitive monitoring is suppressed by fluency. The ease of the interaction is interpreted as a signal of reliability rather than as a feature of the system's design.

The loop is **not** present in the following cases:

- Repeated use of AI without co-calibration, such as using AI as a lookup tool for discrete facts with external verification.
- Productive scaffolding with maintained independent verification norms, such as expert use with domain knowledge that enables output evaluation.
- Short-session interaction without accumulation of shared context across sessions.
- Interaction contexts where the user has strong external performance feedback that corrects miscalibration.

> **Note:** The distinction between beneficial scaffolding and harmful drift cannot be determined from a single session. It requires longitudinal observation of query breadth, verification behaviour, and metacognitive accuracy over time.

---

## 4. Distinction from Existing Risk Models

The adaptive loop is not adequately captured by three existing models that address related but distinct phenomena. The distinction is not that earlier models are wrong, but that they are under-scoped for persistent conversational AI interaction.

### Lens model (framing and narrative)

Lens model approaches describe discrete frame installation: a narrative or framing that, once internalised, structures subsequent interpretation. The adaptive loop does not require a discrete installation point. It is distributed across many interactions, none of which constitutes a decisive framing event. There is no lens the user can identify in retrospect and examine.

### Automation bias (task-level reliance)

Automation bias is primarily documented as a within-session, task-level phenomenon: users follow automated recommendations even when they contradict the user's own judgment on a specific decision. The loop operates across sessions and across tasks. Existing trust calibration research does address learned trust over time (Lee and See, 2004; Hoff and Bashir, 2015), and this is acknowledged. The loop's specific contribution is the conversational, context-co-constructive, metacognitively low-salience form of drift that emerges specifically in sustained language interaction, which existing automation models do not capture.

### Social engineering (intentional manipulation)

Social engineering requires an actor with intent to manipulate. The adaptive loop does not require actor intent. It emerges from the structural properties of repeated conversational AI interaction: the system's responsiveness, the user's natural linguistic adaptation, and the fluency effects that suppress metacognitive monitoring. This makes it harder to detect and harder to attribute.

---

## 5. Empirical Foundation by Loop Phase

Each phase of the adaptive loop is grounded in established empirical research. The loop as a unified security construct is a theoretical integration; the component mechanisms are individually supported.

| Loop phase | Mechanism | Primary sources | Empirical status |
|---|---|---|---|
| Mutual adaptation | Lexical entrainment, Communication Accommodation | Brennan (1996); Giles (1973); Nass and Moon (2000) | Well-established, replicated in HCI |
| Frame shift | Bounded rationality, Shared mental model formation | Simon (1955); Cannon-Bowers et al. (1993) | Established; note: SMM literature assumes external calibration feedback |
| Frame shift | Bias amplification across interactions | Glickman and Sharot (2024); Vicente and Matute (2023) | Peer-reviewed; demonstrates cross-session persistence |
| Metacognitive invisibility | Processing fluency and truth effect | Reber and Schwarz (1999) | Well-established, replicated |
| Metacognitive invisibility | Illusion of Explanatory Depth | Rozenblit and Keil (2002) | Well-established, replicated |
| Metacognitive invisibility | Cognitive ease and System 1 dominance | Kahneman (2011) | Foundational; widely replicated |
| Loop as unified construct | Cross-session drift without metacognitive detection | No direct longitudinal study yet exists | Theoretical integration; empirically motivated |

Two studies are particularly relevant to the loop's security implications. Glickman and Sharot (2024) demonstrated empirically that human-AI interaction amplifies human bias across interaction cycles, with participants largely unaware of the AI's influence. Vicente and Matute (2023) demonstrated that bias introduced by an AI system persisted in participants' independent decision-making even after the AI system was removed, providing the key irreversibility component. Both are peer-reviewed.

On epistemic narrowing: the epistemological version of the filter bubble, where intellectual isolation arises from the interaction between the user's cognitive profile and the system's interface rather than from algorithmic filtering alone (Brändén et al., 2022), is more relevant to CV-00 than the original Pariser formulation, which lacks robust empirical support for the strong effects claimed.

---

## 6. Why Standard Defences Are Under-Scoped

Standard epistemic defences are not wrong. They target discrete judgments more effectively than longitudinal interaction drift. The adaptive loop undermines them at a different point in the causal chain.

- **Critical thinking and media literacy:** most effective at the point of evaluating a specific claim. The loop operates before claim evaluation, narrowing which claims are generated and which feel worth evaluating.
- **Transparency and explainability:** increase the user's ability to scrutinise a single output. They do not interrupt the fluency effects that accumulate across sessions.
- **AI warnings and uncertainty displays:** can interrupt System 2 evaluation at the point of a specific judgment. They do not prevent the gradual increase in fluency that makes System 2 interruption feel less necessary.

This is not an argument that these measures are ineffective. It is an argument that they are necessary but not sufficient. They must be complemented by longitudinal controls that operate at the interaction-level rather than the judgment-level.

---

## 7. Defence-in-Depth Model

Because the loop operates across sessions and phases, effective mitigation requires controls at multiple points. No single intervention is sufficient.

### Layer 1: Fluency interruption

Introduce deliberate friction in AI-user interaction to prevent automatic processing fluency from accumulating unchecked. This includes: uncertainty markers in outputs, explicit source attribution requirements, and periodic prompting for independent verification. The goal is to keep the interaction above the threshold that triggers metacognitive monitoring.

### Layer 2: Query breadth monitoring

Track the breadth of questions a user asks across sessions. A measurable narrowing in query diversity, relative to baseline or control, is a detectable indicator of reference frame shift. This is the most directly operationalisable metric for loop-level drift.

### Layer 3: External calibration requirements

In high-risk deployment contexts, require periodic verification of AI-assisted decisions against external sources or independent expert review. The Shared Mental Model literature (Cannon-Bowers et al., 1993) shows that SMMs become safety risks when they are not calibrated against external performance feedback. The same principle applies here.

### Layer 4: Longitudinal drift monitoring

Because the loop operates across sessions, single-session observation is insufficient. Drift monitoring requires comparison across interaction history: logging of reasoning provenance, periodic review of framing shifts, and structured self-assessment at intervals longer than a single session. The Loop Sensitivity Audit, proposed in section 8, operationalises this.

---

## 8. Empirical Status and Proposed Measurement

The component mechanisms of the adaptive loop are empirically supported. The loop as a unified security construct is a theoretical integration grounded in convergent evidence from cognitive psychology, HCI, and human-AI interaction research. It has not yet been validated as a single measurable risk class in a dedicated longitudinal study.

This distinction matters for how CV-00 should be used. It provides a theoretically grounded framework for understanding risk in sustained AI interaction contexts. It should not be used as though it were a directly validated threat category.

### Proposed measurement framework: Loop Sensitivity Audit

A Loop Sensitivity Audit tests not whether the AI system is reliable, but whether the human-AI unit maintains critical distance over time. The audit has three measurement components, each corresponding to a loop phase:

| Loop phase | Empirical indicator | Measurement method |
|---|---|---|
| Mutual adaptation | Lexical and syntactic convergence | Semantic convergence analysis: track shift from user's natural language to AI-aligned vocabulary across session logs |
| Frame shift | Reduced exploration of alternatives | Counterfactual prompting: measure user's ability to generate alternative framings at session intervals |
| Metacognitive invisibility | Fluency blindness | Self-report vs objective drift gap: compare user's estimated objectivity against actual error detection rate for planted AI outputs |

The automation bias study associated with this framework (jsPsych v8, MindProbe) generates within-session baseline data relevant to the metacognitive invisibility phase. It does not directly measure the loop but establishes a methodological foundation for the Audit's third component.

---

## 9. Relationship to CV-01 through CV-07

Each document in the CV series addresses a specific cognitive vulnerability: a state or tendency that the adaptive loop produces or amplifies. CV-00 is the explanatory foundation for why those vulnerabilities arise in AI-interaction contexts specifically, as distinct from the broader cognitive science literature from which they are drawn.

CV documents should be read as describing effects. CV-00 describes the risk-generating mechanism. Mitigations documented in individual CV entries are most effective when implemented as part of the layered defence-in-depth model described in section 7 of this document, rather than as standalone interventions targeting individual vulnerabilities.

---

## References

Brennan, S.E. (1996). Lexical entrainment in spontaneous dialog. Proceedings of the 1996 International Symposium on Spoken Dialogue, 41-44.

Branden, A. et al. (2022). Through the Newsfeed Glass: Rethinking Filter Bubbles and Echo Chambers. Frontiers in Psychology. PMC8923337.

Cannon-Bowers, J.A., Salas, E. and Converse, S. (1993). Shared mental models in expert team decision making. In N.J. Castellan (Ed.), Individual and Group Decision Making. Erlbaum.

Giles, H. (1973). Accent mobility: A model and some data. Anthropological Linguistics, 15(2), 87-105.

Glickman, M. and Sharot, T. (2024). How human-AI feedback loops alter human perceptual, emotional and social judgements. Nature Human Behaviour, 9, 345-359. https://doi.org/10.1038/s41562-024-02077-2

Hoff, K.A. and Bashir, M. (2015). Trust in automation: Integrating empirical evidence on factors that influence trust. Human Factors, 57(3), 407-434.

Kahneman, D. (2011). Thinking, Fast and Slow. Farrar, Straus and Giroux.

Lee, J.D. and See, K.A. (2004). Trust in automation: Designing for appropriate reliance. Human Factors, 46(1), 50-80.

Nass, C. and Moon, Y. (2000). Machines and mindlessness: Social responses to computers. Journal of Social Issues, 56(1), 81-103.

Reber, R. and Schwarz, N. (1999). Effects of perceptual fluency on judgments of truth. Consciousness and Cognition, 8(3), 338-342.

Rozenblit, L. and Keil, F. (2002). The misunderstood limits of folk science: An illusion of explanatory depth. Cognitive Science, 26(5), 521-562.

Simon, H.A. (1955). A behavioral model of rational choice. The Quarterly Journal of Economics, 69(1), 99-118.

Vicente, L. and Matute, H. (2023). Humans inherit artificial intelligence biases. Scientific Reports, 13, 15737. https://doi.org/10.1038/s41598-023-42384-8

---

*King Che Magnusson*
*OWASP HCI Cognitive Layer, CV-00 v2.0*
