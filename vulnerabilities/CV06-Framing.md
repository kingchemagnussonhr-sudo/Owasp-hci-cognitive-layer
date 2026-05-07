# CV-06: Framing Effects
### How AI output is worded changes the decision, not just the perception.

## 1. Definition

Framing Effects occur when the linguistic presentation of AI output, including word choice, reference class, positive vs. negative framing, and action vs. omission framing, systematically changes user decisions independently of the underlying factual content.

This is distinct from CV-05 (Authority Bias) and CV-03 (Anchoring):
* CV-05 concerns WHO is saying it (perceived authority)
* CV-03 concerns WHAT was said first (initial value anchor)
* CV-06 concerns HOW it is said (linguistic frame of identical content)

LLMs introduce a new dimension: model outputs exhibit frame-sensitive variation analogous to framing effects observed in human decision-making. Studies show LLMs generate differently framed content than humans, and more framing, not less.

## 1.1 The Equivalence Problem

Classical framing research assumes mathematically or logically equivalent outcomes presented differently. In LLM-generated output, strict semantic equivalence is rarely verifiable: the model does not retrieve a fixed fact and reframe it, it generates a representation probabilistically. Two outputs on the same underlying topic may differ in framing, emphasis, and implicit valence simultaneously, making it difficult to isolate framing as the sole variable.

Representational asymmetry refers to systematic variation in salience, valence, emphasis, or interpretive accessibility despite stable underlying informational content.

This does not invalidate CV-06 as a vulnerability category. It means that framing effects in LLM contexts are harder to attribute cleanly than in classical experiments, and that auditing for frame sensitivity requires comparative prompt testing rather than logical equivalence checks.

## 2. Detection Signals

* Same underlying data produces different user decisions depending on whether AI output uses gain vs. loss framing
* Risk described as probability ("3% failure rate") vs. frequency ("3 in 100 systems fail") produces different responses to identical risk
* Action framing ("you should do X") vs. omission framing ("not doing X increases risk") produces different compliance rates

CV-06 is most clearly instantiated when output framing varies while underlying informational content remains stable. In cases where framing co-occurs with emotional priming, urgency signalling, or authority cues, CV-06 should be recorded as a contributing mechanism rather than the sole vulnerability.

## 2.1 Documented Real-World Incidents

### Case 1: LLMs exhibit higher frame sensitivity than humans in moral and risk decisions

A PNAS study (2025) tested framing effects across multiple LLMs on moral decision vignettes. All LLMs responded differently depending on how vignettes were framed, choosing the cost-benefit-rational option 53% of the time when framed as action, but 97% of the time when framed as omission. The difference in humans was 5%; in LLMs it was 45%. LLM outputs exhibit systematically higher frame sensitivity than human responses, a pattern the study attributes to RLHF fine-tuning rather than to deliberate representational choice.

*CV-06 pattern: Model-side frame sensitivity is larger than human equivalents and is introduced by RLHF fine-tuning.*

Source: Molinaro et al. (2025). Large language models show amplified cognitive biases in moral decision-making. PNAS, 122(26). DOI: 10.1073/pnas.2426675122

### Case 2: LLMs generate more framing than human authors

A comparative study of news summarisation across 27 LLM families found that LLMs generally frame information more than human authors, particularly on politically and socially charged topics. LLMs trained on internet data have internalised framing patterns from that data and reproduce them in outputs, including in contexts where the user expects neutral summary. While political and news framing differs mechanistically from classical decision framing, the findings support the broader claim that LLM outputs reproduce and amplify representational asymmetries present in training distributions.

*CV-06 pattern: LLM output introduces framing not present in source material, shaping user interpretation without explicit user awareness of the representational shift.*

Source: Pastorino et al. (2025). Frame In, Frame Out: Do LLMs Generate More Biased News Headlines than Humans? arXiv:2505.05406

### Case 3: Framing effects in cybersecurity risk communication

In security operations, AI-generated threat intelligence consistently adopts one representational frame over another based on training data patterns, not on deliberate calibration to the operational context. The same vulnerability can be framed as a present condition ("systems remain exposed without this patch") or as a potential outcome ("applying this patch reduces exposure"), producing different analyst prioritisation responses to identical underlying risk. This is a direct application of omission/action framing in a security context, grounded in Tversky and Kahneman (1981).

*CV-06 pattern: AI-generated threat framing drives analyst response independently of underlying risk level.*

Source: Tversky, A. & Kahneman, D. (1981). The framing of decisions and the psychology of choice. Science, 211(4481), 453-458. DOI: 10.1126/science.7455683

## 2.2 Framing Drift in Multi-Turn Interaction

Classical framing research treats framing as a property of a single message. In multi-turn LLM interaction, framing accumulates across turns: an initial representational choice constrains subsequent outputs, and the user's responses to those outputs introduce new framing that the model incorporates. The result is a dynamic in which framing effects compound rather than reset between exchanges. Framing drift is best understood as an emergent interaction-layer amplification of CV-06 rather than a core framing mechanism: it arises from the recursive structure of conversational AI systems and connects directly to CV-00 (The Adaptive Loop).

Empirical support for this mechanism comes from several directions. Laban et al. (2025) demonstrate that LLMs make early assumptions in underspecified conversations and rely on those assumptions when generating subsequent responses, producing what the authors term the "lost in conversation" phenomenon. This is framing drift at the structural level: initial framing forecloses later correction. Bedi et al. (2025) show that replacing ground truth answer options with "None of the other answers" causes accuracy to drop over 30%, indicating that LLMs respond to the representational structure of options rather than their propositional content. Chen et al. (2025) demonstrate that helpfulness encoding causes LLMs to comply with illogically framed medical requests despite possessing the knowledge to identify them as illogical, isolating compliance as a mechanism through which framing drift produces consequential errors.

In clinical and high-stakes decision support contexts, framing drift is a particular risk because underspecification is the default state of interaction: users lack the domain knowledge to specify queries precisely, which means initial model framing is rarely corrected by the user and instead propagates through the conversation.

As the user adapts their queries to prior AI output, the framing embedded in that output shapes the next query, creating a feedback structure in which neither the user nor the model has an independent representational baseline.

Sources: Laban et al. (2025), arXiv:2505.06120. Bedi et al. (2025), JAMA Network Open, 8(8):e2526021. Chen et al. (2025), npj Digital Medicine, 8(1):605. arXiv:2603.11394v2 (April 2026).

## 3. Exploitation Scenarios

Framing Effects can be deliberately weaponised, but the more prevalent risk is unintentional: optimization for helpfulness, engagement, or conversational politeness introduces framing asymmetries as a systemic artifact rather than an attacker's choice. RLHF fine-tuning, verbosity preferences, and compliance-oriented tuning all produce consistent framing patterns that steer user decisions without any deliberate intent.

Deliberate exploitation scenarios include:
* Attacker crafts prompts that cause AI threat intelligence tool to frame a critical vulnerability as low-priority through word choice
* AI compliance assistant frames regulatory requirement as optional ("may wish to consider") vs. mandatory ("must implement") based on training data patterns, not regulatory text
* AI medical assistant frames identical risk as "95% survival rate" vs. "5% mortality", producing different treatment decisions from same data

## 4. Mitigation Strategy Across Layers

### Model-Level Controls
* **Frame Symmetry Requirement:** for risk and probability statements, model must output both positive and negative frame ("X% success rate, Y% failure rate") not one or the other
* **Omission/Action Parity:** model must not systematically prefer action or omission framing, both should be presented for consequential decisions
* **Framing Audit:** outputs in high-stakes domains should be tested for frame sensitivity before deployment

### Interface-Level Controls
* **Dual Frame Display:** UI should display probability information in both frequency and percentage formats for risk-relevant outputs
* **Reframe Prompt:** prompt user to consider the same output under the opposite framing before acting

### Human-Level Safeguards
* **Framing Literacy Training:** teach users to identify gain/loss framing, action/omission framing, and reference class effects in AI output
* **Structured Reframing Protocol:** require decision-makers to restate AI-generated risk assessment in the opposite frame before acting

### Governance-Level Controls
* **Frame Sensitivity Testing:** include framing calibration checks as part of high-stakes deployment approval processes
* **Framing Policy Documentation:** document representational choices and their rationale for domain-specific deployments
* **Version Audit Logging:** log and monitor for framing drift introduced by fine-tuning updates or model version changes
* **Domain-Specific Framing Policies:** establish organisational standards for how risk, uncertainty, and recommendations are framed in AI output within regulated or high-stakes contexts

Excessive frame balancing may itself introduce cognitive overload or reduce decisional clarity. Mitigations therefore require contextual calibration rather than universal symmetry enforcement.

## 5. Alignment With OWASP LLM Top 10

CV-06 operates at the cognitive-interaction layer and interacts with several OWASP LLM Top 10 risk categories by providing the mechanism through which those risks produce incorrect user decisions.

CV-06 amplifies the impact of:
* LLM09 Overreliance
* LLM02 Insecure Output Handling
* LLM06 Sensitive Information Disclosure (indirect: framing of data exposure risk affects whether users treat it as urgent)

Framing Effects are the mechanism by which factually accurate AI output produces incorrect decisions, not because the facts are wrong, but because the presentation steers the user away from the appropriate response.
