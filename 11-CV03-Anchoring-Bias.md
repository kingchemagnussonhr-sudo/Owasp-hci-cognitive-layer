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
