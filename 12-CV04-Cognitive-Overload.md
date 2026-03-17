Förlåt! Här kommer den:

```markdown
# CV-04: Cognitive Overload Exploitation
### Users miss critical information due to excessive output volume or complexity.

---

## 1. Definition

**Cognitive Overload Exploitation** occurs when an AI system produces output whose **length, density, or structural complexity exceeds the user's effective working-memory capacity**, leading to selective processing and omission of critical information.

Under such conditions, users tend to:

- Scan for surface-level answers, treating the first confident statement as the conclusion
- Ignore uncertainty markers and epistemic hedges embedded in mid-output positions
- Miss warnings, contradictions, or safety constraints that appear after opening claims

This vulnerability arises from the interaction between three structural factors:

- **LLM verbosity tendencies** — models optimise for apparent completeness, not cognitive accessibility
- **Human working-memory limits** — empirically bounded to approximately 4–7 information units (Miller, 1956)
- **Interface designs** that present long, unstructured outputs without progressive disclosure

> **Security framing:** CV-04 is not a UX problem. It is a structural attack surface in human-AI interaction. Output volume can be used — deliberately or incidentally — to bury critical information, suppress user verification behaviour, and cause decision errors that would not occur if the same content were presented concisely. Where CV-01 exploits trust in AI authority, CV-04 exploits the bounded capacity of human attention.

---

## 2. Detection Signals

### Output structure signals
- Output length significantly exceeds task complexity
- Dense paragraphs with multiple nested instructions or caveats
- Safety warnings embedded in the middle of long responses
- Critical caveats appearing after implementation instructions rather than before

### Behavioural signals
- Users execute recommended actions without referencing safety notes
- High rate of copy-paste execution of long AI outputs without review
- Rapid task completion immediately following long AI responses
- User sessions ending without follow-up after receiving large outputs

### Interaction signals (interface telemetry)
- Low scroll depth in long outputs
- Repeated user prompts requesting a "short version" or "summary"
- Follow-up errors that indicate the user missed a mid-output caveat

---

## 2.1 Documented Real-World Incidents

Although rarely labelled explicitly as cognitive overload exploitation, multiple empirical studies demonstrate how information volume and structural position in AI output degrades human decision quality and causes critical information to be missed.

### Case 1: The "lost in the middle" effect — LLM output position bias

When LLMs generate lengthy responses, critical caveats placed in the middle of the output are systematically missed — by both model and user. Liu et al. (2023) identified a distinctive U-shaped performance curve across GPT-3.5-Turbo, GPT-4, and Claude: performance is highest when relevant information occurs at the very beginning or end of an input context, and degrades significantly when models must access information from the middle of long contexts — even for models explicitly designed for long-context tasks. The attack surface follows directly: a safety caveat placed in paragraph four of an eight-paragraph response is the position least likely to be read, recalled, or acted on. Wang et al. (2023) and Zhang et al. (2023) confirmed the primacy effect across ChatGPT, GPT-3.5, and GPT-4, with findings extended to Claude-instant-1.2 — confirming the effect is not confined to any single model family.

**Impact**
- Compliance caveats, uncertainty flags, and contradictory evidence buried mid-output are functionally invisible
- Users act on confidently stated opening conclusions while missing qualifying information later in the response
- Model and user position biases compound: the model underweights mid-context information when generating; the user underweights it when reading

**Reference**
Liu et al. (2023). Lost in the Middle: How Language Models Use Long Contexts. *Transactions of the Association for Computational Linguistics*, 12. https://doi.org/10.1162/tacl_a_00638 | Guo & Vosoughi (2024). Serial Position Effects of Large Language Models. arXiv:2406.15981

---

### Case 2: Cognitive overload in AI-assisted clinical decision support

Healthcare professionals using AI clinical decision support systems (CDSS) under high cognitive load show systematically higher rates of missed contradictory signals. Lyell and Coiera (2017) conducted a systematic review confirming that automation bias in CDSS is exacerbated by cognitive load in both single-tasking and multitasking settings. A 2026 synthesis in *Artificial Intelligence Review* confirmed the mechanism: overload manifests as missed cues, slower control, and defaulting to habits — and inserting even a few unrelated sentences before a query reliably reduces reasoning accuracy, with common failures including primacy bias where early inputs are overweighted and buried instructions ignored. In clinical practice: a CDSS output that leads with a confident diagnosis and buries a low-confidence warning three screens later will see the warning missed at high rates under shift-end or emergency conditions.

**Impact**
- Safety-critical warnings in CDSS output missed under cognitive load conditions
- Shift-end and multitasking contexts — when overload is highest — are also when AI-assisted decisions are most consequential
- Confidence of the opening recommendation anchors the clinical decision even when contradictory evidence appears later in the output

**Reference**
Lyell & Coiera (2017). Automation Bias and Verification Complexity. *Journal of the American Medical Informatics Association*, 24(2), 423–431. https://doi.org/10.1093/jamia/ocw105 | *Artificial Intelligence Review* (2026). https://doi.org/10.1007/s10462-026-11510-z

---

### Case 3: AI-generated compliance summaries — volume as a vector

In regulatory and legal contexts, LLMs produce outputs of significant length and surface coherence. Analysts and compliance officers acting under time pressure exhibit the CV-04 pattern acutely: they read the opening conclusion, skim the body, and miss material qualifications. Louw et al. (2025) found a significant negative correlation between frequent AI tool usage and critical thinking abilities (β = −1.76, p < 0.001), mediated by increased cognitive offloading. A structured survey of 500 adults confirmed that long-term AI exposure was strongly associated with information overload, mental exhaustion, and diminished attentional capacity — meaning the vulnerability compounds with repeated use. In compliance contexts: an analyst receiving a 600-word AI summary will, under time pressure, act on the opening paragraph. If the material qualification appears in paragraph five, it will be missed at a rate determined by working memory under load, not by the analyst's competence.

**Impact**
- Material compliance qualifications buried in mid-output go unread and unacted upon
- Regulatory exposure from decisions made on incomplete reading of AI-generated summaries
- Output volume is used as a proxy for thoroughness, suppressing further verification behaviour

**Reference**
Louw et al. (2025). AI Tools in Society: Impacts on Cognitive Offloading and the Future of Critical Thinking. *Social Sciences*, 15(1), 6. https://doi.org/10.3390/socsci15010006

---

## 3. Exploit Scenario

| Step | Description |
|------|-------------|
| Step 1 | A compliance analyst asks an LLM to summarise new financial regulation requirements. |
| Step 2 | The model generates a 700-word response, opening with a confident two-sentence summary of the main obligations. |
| Step 3 | In paragraph five, the model notes: "Note: these obligations do not apply to entities below the EUR 10M revenue threshold." This caveat is accurate and critical. |
| Step 4 | The analyst, under time pressure, reads the opening summary and acts on it — implementing controls that are both unnecessary and operationally disruptive. |
| Step 5 | When challenged, the analyst references the AI output. The caveat was present; it was simply positioned where human attention does not reach under normal cognitive load conditions. |

> **Compound risk with CV-01 and CV-03:** When CV-04 fires alongside CV-01 (automation bias) and CV-03 (anchoring bias), the failure mode is self-reinforcing. The user accepts the opening output without scrutiny (CV-01), anchors all subsequent reasoning to it (CV-03), and has cognitively missed the qualification that would have prompted reconsideration (CV-04). No individual bias alone produces the outcome; the combination does.

---

## 4. Mitigations

### Model-Level

**Progressive disclosure**
Force output structure: critical warning first, then summary, then detail on request.

| Position | Section | Requirement |
|----------|---------|-------------|
| 1 | Critical warning | Any safety constraint or disqualifying condition — stated first, prominently |
| 2 | Executive summary | 2–3 sentences maximum |
| 3 | Recommended actions | Structured steps, clearly bounded |
| 4 | Detailed explanation | Available on request — not default |
| 5 | Warning repeat | Restate the caveat from position 1 verbatim |

**Warning redundancy**
Critical safety warnings must appear at the beginning AND end of output — never only in the middle.

**Cognitive budgeting**

| Task category | Risk level | Default output format | Warning placement |
|--------------|-----------|----------------------|------------------|
| Informational | Low | Full explanation | End of output |
| Operational | Medium | Structured steps + summary | Before and after steps |
| Safety-critical | High | Minimal steps only | Top of output, repeated |
| High-stakes decision | Critical | Summary + warnings only | Top + visual callout |

### Interface-Level

- **Visual salience** — highlight warnings, uncertainty markers, and contradictions with colour, icons, or callout blocks
- **Output chunking** — break long responses into labelled sections with a navigable summary at the top
- **Attention anchors** — pin critical safety information to the top; repeat in a fixed footer or sidebar

### Human-Level

- **Cognitive resilience training** — teach users to apply a deliberate pause before acting on long AI outputs, especially under time pressure

---

## 5. OWASP Alignment

CV-04 amplifies the impact of three OWASP LLM vulnerabilities by removing the human verification behaviour that would otherwise compensate for them:

- **LLM02 Insecure Output Handling** — Users may implement unsafe instructions because safety warnings were cognitively missed due to output volume or burial position.
- **LLM09 Overreliance** — Long, fluent explanations increase perceived authority of the model while simultaneously reducing critical evaluation.
- **LLM06 Sensitive Information Disclosure** — Users may miss notices that output contains sensitive or regulated data when those notices are buried in lengthy responses.

---

## References

| Author(s) | Citation | DOI |
|-----------|----------|-----|
| Liu et al. | Lost in the Middle: How Language Models Use Long Contexts. *TACL*, 12 (2023) | doi.org/10.1162/tacl_a_00638 |
| Guo & Vosoughi | Serial Position Effects of Large Language Models. arXiv:2406.15981 (2024) | arxiv.org/abs/2406.15981 |
| Lyell & Coiera | Automation Bias and Verification Complexity. *JAMIA*, 24(2) (2017) | doi.org/10.1093/jamia/ocw105 |
| Springer AI Review | Overloaded minds and machines: cognitive load framework for human-AI symbiosis (2026) | doi.org/10.1007/s10462-026-11510-z |
| Louw et al. | AI Tools in Society: Impacts on Cognitive Offloading. *Social Sciences*, 15(1) (2025) | doi.org/10.3390/socsci15010006 |
| Miller, G.A. | The magical number seven, plus or minus two. *Psychological Review*, 63(2) (1956) | doi.org/10.1037/h0043158 |
| Wang et al. | Large Language Models Are Not Robust Multiple Choice Selectors. arXiv:2309.03882 (2023) | arxiv.org/abs/2309.03882 |
| Parasuraman & Riley | Humans and Automation: Use, Misuse, Disuse, Abuse. *Human Factors*, 39(2) (1997) | doi.org/10.1177/001872089704900303 |
```
