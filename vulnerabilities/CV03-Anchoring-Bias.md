# CV-03: Anchoring Bias
### Users over-weight the first piece of AI-provided information.

## 1. Definition
Anchoring occurs when users rely too heavily on initial LLM output
when making subsequent decisions, even when later information
contradicts or qualifies it.

## 2. Detection Signals
- User fails to revise initial estimate after receiving contradictory output
- Query sequence shows no reformulation after new evidence presented
- Decision outcome correlates with order of information, not quality


2.1 Documented Real-World Incidents

Legal — anchoring bias in LLM-based legal decision-making

The strongest source is a study published in Artificial Intelligence and Law (Springer, January 2026). The researchers replicated Teichman et al. (2023) across seven advanced LLMs, including GPT-4o and Claude Sonnet, and found that the models systematically exhibited anchoring bias recommending significantly longer sentences when exposed to irrelevant numerical anchors.Particularly relevant for your CV-03 scenario: knowledge enhancement actually worsened the anchoring bias more legal information in the prompt increased rather than decreased the effect.This means a lawyer relying on a well-calibrated, well-trained model may be more exposed, not less.

The classical human baseline for this is Englich, Mussweiler & Strack (2006) "Playing dice with criminal sentences" which showed that experienced judges anchored verdicts to random dice rolls. This study is cited directly in the LLM study above and provides the human baseline that CV-03 builds on.

Finance, anchoring bias in LLM investment analysis

A strong empirical source here is a ScienceDirect study (2024): researchers tested whether ChatGPT exhibits anchoring bias in financial forecasts, including extreme anchors such as an S&P 500 value of 59,175 and found that LLM responses are sensitive to biased hints, consistent with prior findings on humans in equity market forecasts, cryptocurrency, and credit card decisions.
ScienceDirect

An even sharper source for the exact scenario of an analyst failing to revise their assessment is "Your AI, Not Your View" (ACM Conference on AI in Finance, 2025): models exhibited a strong confirmation bias when confronted with counter-evidence, regardless of volume and intensity, they stubbornly refused to revise their judgments, adhering to evidence that confirmed their internal knowledge while disregarding counter-evidence.

This is CV-03 described at the model level 
But since the analyst receives and iterates with the model, this maps directly onto human behaviour. The methodologically most robust study on LLM anchoring bias generally is now "Anchoring Bias in Large Language Models: An Experimental Study" published in the Journal of Computational Social Science (Springer, December 2025): strong models consistently demonstrated vulnerability to the anchoring effect. They were highly susceptible to "expert" opinions presented in the prompt, and this behaviour could not be corrected even when the model was explicitly instructed to ignore them. Neither Chain-of-Thought, Thoughts of Principles, nor Reflection strategies were sufficient to reduce anchoring bias.
Springer

Clinical anchoring and automation bias in diagnostics

The most directly citable study is Jabbour et al., JAMA, December 2023 "Automation Bias and Assistive AI: Risk of Harm From AI-Driven Clinical Decision Support" (PMID 38112814). It is a clinical trial published in JAMA, giving it high authority. It focuses explicitly on how AI-driven clinical decision support creates automation bias and is widely cited in subsequent literature. A complementary RCT from Communications Medicine (Nature, 2025) offers a more nuanced picture: 50 US-licensed physicians reviewed standardised chest pain vignettes and answered clinical questions before and after receiving GPT-4 recommendations physicians were willing to modify their clinical decisions based on AI assistance, leading to improved accuracy scores.
Nature
This is an important counterbalance: the study shows the CV-01 pattern of uncritical acceptance is not inevitable, but it confirms that the behaviour is strong enough to produce measurable effects on clinical decisions.


## 3. Exploitation Scenarios
- Legal professional anchors on first contract interpretation
- Financial analyst anchors on initial LLM valuation estimate
- Clinician anchors on first differential diagnosis

## 4. Mitigations
### Model-Level
- Present multiple framings of the same answer simultaneously
- Flag when first output is a preliminary assessment only
### Interface-Level
- Randomise order of presented alternatives across sessions
- Require user to document reasoning before viewing AI output

## 5. OWASP Alignment
Amplifies: LLM09 Overreliance, LLM04 Model Denial of Service (via
anchored incorrect outputs that persist through workflow).
