# CV-01: Automation Bias Exploitation
### Human overreliance on AI outputs without sufficient verification.

## 1. Definition
Automation Bias occurs when users accept AI responses too quickly, too confidently, or without adequate scrutiny, assuming the system is correct because it is automated.

LLMs increase this risk due to:
- fluent language,
- rapid response time,
- authoritative tone,
- perceived expertise.

## 2. Signals and Detection Patterns
The AI system can detect early indicators of automation bias:

- **Low Token-to-Claim Ratio**  
  Long or fast output with few actual facts or unique claims.

- **Overly fluent or confident tone**  
  High language coherence with insufficient epistemic content.

- **Rapid user acceptance behaviour**  
  Minimal interaction before taking action on the output.

- **Cognitive Overload Conditions**  
  User behaviour indicating fatigue, stress, or multitasking.

## 3. Exploitation Scenarios
Automation Bias can turn a minor model error into a major incident:

- User approving an incorrect compliance answer.  
- Analyst copying hallucinated content into a report.  
- Operator executing an AI-suggested action without review.

## 4. Mitigation Strategy Across Layers

### **Model-Level Controls**
- **Latency-Compensated Generation (LCG)**  
  Introduces adaptive delay for high-risk answers to prevent reflex acceptance.

- **Structured Uncertainty Expression**  
  Model outputs must include confidence signals or optionality where appropriate.

- **Counterfactual Injection**  
  The model produces at least one alternative hypothesis during ambiguous queries.

### **Interface-Level Controls**
- **Information Density Barometer**  
  Detects low-density outputs and warns that the user should verify.

- **Review Gate for High-Risk Outputs**  
  UI requires user confirmation or a secondary check.

- **Slowed Interaction for Critical Tasks**  
  Introduces friction intentionally.

### **Human-Level Safeguards**
- **Metacognitive Resilience Training**  
  Teaching users when and how to question AI outputs.

- **Structured Decision Protocols**  
  Mandatory review steps for policy, compliance, or high-impact tasks.

## 5. Alignment With OWASP LLM Top 10
CV-01 amplifies the impact of:

- **LLM02 Insecure Output Handling**  
- **LLM06 Sensitive Data Exposure**  
- **LLM08 Excessive Agency**  
- **LLM09 Overreliance**

Automation Bias is often the *last mile failure* that turns technical flaws into real incidents.


