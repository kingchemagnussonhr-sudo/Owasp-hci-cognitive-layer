# CV-05 — Algorithmic Authority Bias

**Status:** Proposed | Pending empirical consolidation
**Version:** 0.1
**Author:** King Che Magnusson
**Date:** April 2026

---

## Definition

The tendency to defer to AI system outputs not because the system is perceived as accurate or objective, but because the institution deploying the system carries legitimate authority. The algorithm inherits the authority of its deployer.

---

## Theoretical Basis

CV-05 is a specialisation of authority bias in the algorithmic context. It is analytically distinct from CV-03 (Automation Bias), which describes deference based on perceived objectivity of automation itself. In CV-05, the deference mechanism is institutional: the operator or affected individual complies because the system represents the organisation, not because they trust the technology.

The Milgram obedience experiments (1963, 1974) demonstrate that humans comply with harmful instructions when issued by a perceived authority — and that compliance decreases substantially when the authority figure is absent or the institutional setting is removed. When Milgram relocated the experiment from Yale University to an unmarked office, obedience dropped from 65% to 47%. The institutional context, not the instruction itself, was driving compliance.

The hypothesis is that AI systems deployed by authoritative institutions activate the same mechanism: the system's output carries implicit institutional endorsement. Questioning the output means questioning the institution.

**Distinction from CV-03 Automation Bias:**

| | CV-03 Automation Bias | CV-05 Algorithmic Authority Bias |
|---|---|---|
| Deference mechanism | Perceived objectivity of automation | Institutional authority of deployer |
| Trigger | The system seems accurate | The system represents a legitimate authority |
| Breaks down when | System makes visible errors | Institutional legitimacy is challenged |
| Governance response | Training, override metrics | Redress mechanisms, affected person information |

---

## Mechanism in AI Context

An AI system deployed by a government agency, law enforcement body, or large institution benefits from authority transfer: the institution's legitimacy flows to the system's outputs. The result is that:

- Operators find it cognitively and socially costly to override system outputs, because override implies questioning an institutional decision
- Affected individuals accept outcomes attributed to "the system" with less resistance than equivalent decisions attributed to an individual officer or caseworker
- The system functions as an authority laundering mechanism: decisions that would be contestable if made by a named human become less contestable when attributed to an algorithm

A system that produces outputs a human caseworker could not defend individually becomes defensible when attributed to institutional process.

---

## Risk Context

Highest in public sector deployments where affected individuals have limited power to contest outcomes:

- Social welfare and benefits determination
- Law enforcement risk scoring and predictive policing
- Immigration and asylum processing
- Criminal sentencing and parole
- Employment screening in regulated sectors

The risk compounds when the system's reasoning is not visible: opacity reinforces the authority effect by making the output appear to transcend individual judgment (see also CV-04 Cognitive Overload).

---

## Empirical Status

This CV is proposed based on theoretical extrapolation from established authority bias research. Direct empirical measurement of algorithmic authority bias as distinct from automation bias is emerging but not yet consolidated.

**Supporting evidence:**

The concept of "algority" — the propensity to confer epistemic authority on algorithms — was recently operationalised in a psychometric study of 610 participants, finding significant correlations between trust in automation, perceptions of automated performance, and deference to AI in high-stakes scenarios including criminal justice and job-matching. Moral attitudes moderated deference in ethically sensitive contexts.

Source: Perceiving AI as an Epistemic Authority or Algority: A User Study on the Human Attribution of Authority to AI (2026)
URL: https://www.mdpi.com/2504-4990/8/2/36

Milgram's original authority experiments establish the baseline mechanism:
Milgram, S. (1963). Behavioral study of obedience. Journal of Abnormal and Social Psychology, 67(4), 371-378.
DOI: 10.1037/h0040525

Milgram, S. (1974). Obedience to authority: An experimental view. New York: Harper and Row.

On the distinction between institutional trust and system trust, and the role of authority signals in AI trust formation:
Between transparency and trust: identifying key factors in AI system perception (2025)
URL: https://www.tandfonline.com/doi/full/10.1080/0144929X.2025.2533358

On algorithmic truth and epistemic deference to AI systems:
Automating epistemology: how AI reconfigures truth, authority, and verification (2025)
URL: https://link.springer.com/article/10.1007/s00146-025-02560-y

**What is missing:** Controlled studies that isolate institutional authority as a variable independent of automation bias. This is the primary empirical gap. The CV is proposed for inclusion pending such research.

---

## Governance Mitigations

- Explicit communication to affected individuals that AI output is one input, not an institutional determination
- Accessible and meaningful challenge and redress mechanisms that do not require the individual to challenge the institution as a whole
- Operator training distinguishing between institutional authority and system reliability
- Override metrics: tracking how often operators override AI outputs and whether override rates differ by operator seniority or proximity to institutional hierarchy
- FRIA must address authority transfer risk specifically in public sector deployments

---

## Regulatory Anchors

| Regulation | Article | Relevance |
|---|---|---|
| EU AI Act | Art. 13 | Transparency to affected persons — information must be sufficient to enable meaningful challenge |
| EU AI Act | Art. 14 | Human oversight — operators must be able to exercise genuine, not nominal, oversight |
| EU AI Act | Art. 26 | Deployer obligations — responsibility for deployment context including authority effects |
| GDPR | Art. 22 | Right to human review of automated decisions — precondition for meaningful redress |

---

## Notes for Future Research

The following empirical questions would strengthen or challenge this CV:

1. Does deference to AI outputs increase when the deploying institution has higher perceived legitimacy, controlling for perceived system accuracy?
2. Do affected individuals contest AI-attributed decisions less than equivalent decisions attributed to a named human, in equivalent institutional contexts?
3. Does operator override rate vary by institutional seniority in ways that cannot be explained by expertise differences?

---

*Part of the [OWASP HCI Cognitive Layer](https://github.com/kingchemagnussonhr-sudo/Owasp-hci-cognitive-layer)*
*Author: King Che Magnusson | April 2026*
