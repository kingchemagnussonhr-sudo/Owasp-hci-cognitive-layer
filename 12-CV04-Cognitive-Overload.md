# CV-04: Cognitive Overload Exploitation
### Users miss critical information due to output volume or complexity.

## 1. Definition
Cognitive Overload occurs when LLM output exceeds the user's working
memory capacity, causing them to process selectively and miss
critical warnings, caveats, or contradictory information.

LLMs increase this risk due to:

- verbosity tendencies that optimise for apparent completeness
- human working-memory limits (~4–7 information units)
- interface designs that present long unstructured outputs

## 2. Detection Signals
The AI system can detect early indicators of cognitive overload:

- Output length significantly exceeds task complexity
- Critical information buried in mid-output position
- User interaction ends immediately after long output (no follow-up)
- Repeated requests for "short version" or "summary"

## 2.1 Documented Real-World Incidents

### Case 1: LLM output position bias (2023–2024)

Liu et al. (2023) identified a U-shaped performance curve across
GPT-3.5-Turbo, GPT-4, and Claude: performance degrades significantly
when relevant information is in the middle of long contexts.

A safety caveat in paragraph four of an eight-paragraph response is
the position least likely to be read or acted on.

Wang et al. (2023) and Zhang et al. (2023) confirmed the primacy
effect across ChatGPT, GPT-3.5, and GPT-4, extended to
Claude-instant-1.2 by Eicher and Irgolič (2024).

CV-04 pattern: Mid-output position suppresses human recall and action.

Source:  
Liu et al., *Lost in the Middle: How Language Models Use Long Contexts*,  
Transactions of the ACL, 2023  
DOI: https://doi.org/10.1162/tacl_a_00638

---

### Case 2: AI-assisted clinical decision support

Lyell and Coiera (2017) conducted a systematic review confirming
that automation bias in clinical decision support systems is
exacerbated by cognitive load in both single-tasking and
multitasking settings.

A CDSS output leading with a confident diagnosis and burying a
low-confidence warning three screens later will see the warning
missed at high rates under shift-end conditions.

CV-04 pattern: Output volume causes safety warnings to be missed
at the moment decisions are made.

Source:  
Lyell & Coiera, *Automation Bias and Verification Complexity*,  
JAMIA, 24(2), 2017  
DOI: https://doi.org/10.1093/jamia/ocw105

---

### Case 3: AI-generated compliance summaries

Louw et al. (2025) found a significant negative correlation between
frequent AI tool usage and critical thinking abilities
(β = −1.76, p < 0.001), mediated by cognitive offloading.

An analyst receiving a 600-word AI compliance summary will, under
time pressure, act on the opening paragraph. A material
qualification in paragraph five is missed at a rate determined by
working memory under load, not by analyst competence.

CV-04 pattern: Output volume used as proxy for thoroughness,
suppressing verification behaviour.

Source:  
Louw et al., *AI Tools in Society: Impacts on Cognitive Offloading
and the Future of Critical Thinking*,  
Social Sciences, 15(1), 2025  
DOI: https://doi.org/10.3390/socsci15010006

---

## 3. Exploitation Scenarios

Cognitive Overload can turn a minor model error into a major incident:

- User approving an unsafe recommendation because the warning appeared mid-output
- Analyst implementing incorrect compliance guidance after reading only the summary
- Operator executing AI-suggested actions without reaching the safety constraints

---

## 4. Mitigation Strategy Across Layers

### Model-Level Controls

- Progressive Disclosure: summary first, critical warnings next, detail on request
- Warning Redundancy: surface critical warnings at beginning AND end of output
- Cognitive Budgeting: adapt verbosity to task risk — safety-critical tasks receive minimal output with foregrounded warnings

### Interface-Level Controls

- Highlight caveats and uncertainty markers visually
- Limit default output length for high-stakes task categories
- Attention anchors: pin critical information to top and bottom of output

### Human-Level Safeguards

- Cognitive Resilience Training: teach users to pause before acting on long outputs
- Structured Review Protocols: mandatory scroll-to-end or summary confirmation for high-stakes tasks

---

## 5. Alignment With OWASP LLM Top 10

CV-04 amplifies the impact of:

- LLM02 Insecure Output Handling
- LLM06 Sensitive Information Disclosure
- LLM09 Overreliance

Cognitive Overload is the mechanism by which technically correct
but poorly structured output becomes operationally dangerous.
