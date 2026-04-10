# CV-00: The Adaptive Loop as Primary Threat Vector

*OWASP HCI Cognitive Layer*

| | |
|---|---|
| Document ID | CV-00 |
| Status | Draft |
| Version | 1.0 |
| Domain | Interaction Dynamics |
| Threat level | Foundational |
| See also | README: Scope and Positioning; CV-01 through CV-07 |

---

## 1. Purpose

This document defines the adaptive loop as the primary threat vector in the OWASP HCI Cognitive Layer framework. It is not a vulnerability catalogue entry in the same sense as CV-01 through CV-07. It describes the structural mechanism that produces the vulnerabilities those documents address.

CV-01 through CV-07 describe what happens to a user's cognition. CV-00 describes why it happens, and why standard epistemic defences are insufficient to prevent it.

See README: Scope and Positioning for the framework's broader positioning within established cognitive security traditions.

---

## 2. Definition

The adaptive loop is a self-reinforcing dynamic that emerges from sustained, continuous interaction between a user and an AI system. It is characterised by three properties:

**Mutual adaptation.** The system adjusts its outputs based on the user's inputs; the user adjusts their framing based on the system's outputs. Neither party announces this. No single exchange is decisive.

**Cumulative reference frame shift.** Over time the shared context narrows. The space of questions that feel worth asking contracts. The space of outputs that feel self-evidently correct expands. This occurs without the user internalising a new belief or narrative.

**Metacognitive invisibility.** Because each exchange is locally reasonable and the shift is incremental, the loop operates below the threshold at which standard metacognitive monitoring triggers. The user does not experience drift. The user experiences accumulated familiarity.

The adaptive loop is not an attack in the intentional sense. It does not require a malicious actor. It emerges from the structural properties of sustained interaction with a system optimised for coherence, responsiveness, and contextual relevance. Its effects are security-relevant regardless of intent.

---

## 3. Distinction from Existing Threat Models

### 3.1 The lens model

The lens model of cognitive drift holds that exposure to a narrative at a specific moment installs a cognitive frame. Subsequent evidence is interpreted through that frame. Path dependence arises because the sequence of idea-encounter determines the frame.

The lens model has an identifiable installation point. Defence is possible at that point: introduce friction before the frame hardens, force contact with falsifying evidence, make the frame itself an object of scrutiny.

The adaptive loop has no installation point. There is no moment at which a frame is acquired. There is a process by which a shared context is continuously co-constructed and continuously normalised. Defence at a single moment is insufficient because the mechanism is continuous.

### 3.2 Automation bias

Automation bias describes the tendency to over-rely on automated system outputs in specific decision contexts. It is a within-session, task-level phenomenon. CV-02 addresses it within this framework.

The adaptive loop operates across sessions and across task types. It produces the conditions under which automation bias is amplified, by shifting the user's baseline expectations and calibration standards before any specific decision is made. It is the precondition, not the event.

### 3.3 Social engineering and influence operations

Established COGSEC traditions address external actors who deliberately construct influence campaigns. The threat is external, the intent is identifiable, and the campaign has a beginning and an end.

The adaptive loop is internal to the user-system relationship. It is not constructed by an external actor. It emerges from the ordinary operation of a system the user chose to engage with, for purposes the user defined. This makes it resistant to standard social engineering defences, which are premised on the existence of an adversarial intent to identify and resist.

---

## 4. Primary Mechanisms

### 4.1 Fluency as a continuous trust signal

Coherent, responsive, contextually calibrated output generates a processing fluency effect: the brain interprets ease of comprehension as a signal of reliability. In a static text, fluency is a one-time property. In conversational AI interaction, fluency regenerates with every exchange.

The cumulative effect is that trust in the system becomes dissociated from any specific verifiable claim. It is attached to the interaction pattern itself. This dissociation is the mechanism by which the fluency effect persists even when individual outputs are incorrect or poorly calibrated.

### 4.2 Confirmation drift without a confirmable position

Classical confirmation bias requires a prior belief that evidence is filtered through. The adaptive loop produces drift without a fixed prior. As the user's framing and the system's outputs converge over time, the space of outputs that feel correct narrows not because a belief is being confirmed but because the reference frame itself has shifted. The user is not defending a position. The user is reasoning inside a context that has been co-constructed and normalised through interaction.

### 4.3 Calibration shift and generalisation

Users learn, correctly, that AI systems perform reliably on certain task types. They adjust their critical engagement accordingly. This is rational local adaptation. The security-relevant consequence is that the adjustment generalises beyond the domain where it is warranted. Reduced scrutiny in one area leaks into adjacent areas where the system's reliability has not been established. The generalisation is invisible because it presents as accumulated experience rather than as a change in epistemic standards.

### 4.4 Path dependence as accumulated outcome

Path dependence in the context of the adaptive loop is the cumulative result of these three mechanisms operating in parallel over time. It is not caused by early narrative exposure. It is produced by the structure of the interaction itself, and it intensifies with interaction volume regardless of what content is exchanged.

---

## 5. Why Standard Defences Are Insufficient

Epistemic defences premised on the lens model (identify the frame, introduce friction at the moment of installation, force falsifying contact) address the wrong point in the causal chain. They are effective against discrete narrative adoption. They do not interrupt a continuous process that operates below metacognitive resolution.

Critical thinking training and media literacy education build resistance at the level of belief evaluation. The adaptive loop does not operate at that level. It operates at the level of what questions feel worth asking and what outputs feel worth evaluating critically. By the time the user applies critical thinking, the reference frame within which that thinking occurs has already been shaped by the loop.

Single-session interventions (warnings, friction at specific decision points, explainability features) are insufficient for the same reason. They address moments. The loop is not a moment.

---

## 6. Defence-in-Depth Implications

Because the adaptive loop is continuous and operates across the full interaction, effective mitigation requires layered controls that are also continuous and operate at multiple points. The following control layers correspond to the mechanisms identified in section 4.

### Layer 1: Fluency interruption

Structured friction introduced at regular intervals, independent of task content, interrupts the automatic trust accumulation produced by fluency. This does not require the user to distrust the system. It requires the user to periodically re-establish the grounds for trust. Specific controls addressing this layer are documented in CV-03 and CV-05.

### Layer 2: Reference frame exposure

Metacognitive checkpoints that surface the interaction pattern itself as an object of scrutiny allow the user to observe shifts in their own framing that would otherwise remain invisible. This requires explicit prompting: unaided metacognition is insufficient because the loop suppresses the signals that would normally trigger self-monitoring. CV-01 and CV-06 address specific implementations.

### Layer 3: Calibration boundary maintenance

Explicit domain separation prevents calibration shifts from generalising. Users benefit from maintaining documented boundaries between domains where system reliability has been verified and domains where it has not. This is an organisational control as much as an individual one. CV-04 addresses calibration drift specifically.

### Layer 4: Longitudinal drift monitoring

Because the loop operates across sessions, single-session observation is insufficient to detect it. Drift monitoring requires comparison across interaction history: logging of reasoning provenance, periodic review of framing shifts, and structured self-assessment at intervals longer than a single session. This layer has no equivalent in existing COGSEC frameworks, which are not designed for continuous interaction threats.

---

## 7. Empirical Status

The mechanisms described in this document are individually supported by empirical research. Fluency effects on trust are well-established in cognitive psychology. Confirmation drift in human-AI interaction has been documented across multiple experimental paradigms. Calibration generalisation is an established finding in automation research.

The adaptive loop as a unified construct, combining these mechanisms in the specific context of sustained conversational AI interaction, is an emerging area of research. Studies using repeated-interaction paradigms rather than single-session evaluations are beginning to produce relevant findings, but the field does not yet have standardised measurement instruments for loop-level drift.

The empirical automation bias study associated with this framework (jsPsych v8, MindProbe) is designed in part to generate within-session data that can serve as a baseline for future longitudinal measurement. It does not directly measure the adaptive loop but establishes the methodological foundation for doing so.

---

## 8. Relationship to CV-01 through CV-07

Each document in the CV series addresses a specific cognitive vulnerability: a state or tendency that the adaptive loop produces or amplifies. CV-00 is the explanatory foundation for why those vulnerabilities arise in AI-interaction contexts specifically, as distinct from the broader cognitive science literature from which they are drawn.

CV documents should be read as describing effects. CV-00 describes the generating mechanism. Mitigations documented in individual CV entries are most effective when implemented as part of the layered defence-in-depth model described in section 6 of this document, rather than as standalone interventions targeting individual vulnerabilities.

---

*King Che Magnusson*
*OWASP HCI Cognitive Layer, CV-00 v1.0*
