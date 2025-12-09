# Core Concepts: Cognitive Vulnerabilities in Human–AI Interaction

## 1. What Is a Cognitive Vulnerability?
A cognitive vulnerability is a predictable pattern in human reasoning or perception that can cause users to misinterpret, overtrust, or misuse LLM outputs.  
Cognitive vulnerabilities interact with technical risks and often determine whether an LLM-related incident actually occurs.

They are not model bugs.  
They are *human–AI interaction failure modes*.

## 2. Why LLM Security Requires a Cognitive Layer
Traditional security models assume:
- the system behaves deterministically,
- the user interprets outputs rationally,
- errors come from faulty code or malicious input.

LLMs break these assumptions.

Even when the model behaves correctly, users may:
- overtrust responses due to automation bias,
- accept emotionally aligned answers due to confirmation drift,
- misunderstand vague explanations,
- fail to detect missing information,
- misjudge the risk during cognitive overload.

Cognitive vulnerabilities therefore act as **multipliers** for technical flaws.

## 3. Interaction Between Cognitive and Technical Risks
Many OWASP LLM Top-10 risks escalate due to cognitive mechanisms:

| Technical Risk | Amplified By Cognitive Vulnerability |
|----------------|--------------------------------------|
| LLM01 Prompt Injection | Overtrust, Anchoring, Missing critical evaluation |
| LLM02 Output Handling | Automation Bias, Confirmation Bias |
| LLM05 Training Data Poisoning | Consensus Illusion, Narrative Drift |
| LLM08 Excessive Agency | Dependency Bias, Optimism Bias |
| LLM09 Overreliance | All core cognitive vulnerabilities |

This framework provides a structured vocabulary to discuss and mitigate such interactions.

## 4. Principles Guiding This Framework
1. **Human behaviour must be treated as part of the security model.**  
2. **Mitigations must operate across three layers:**  
   - the model,  
   - the user interface,  
   - the human cognitive environment.  
3. **Security must introduce friction where cognition fails.**  
4. **Checks must reduce overconfidence and bias amplification.**  
5. **Controls must be explainable and measurable.**

## 5. The Three-Layer Cognitive Security Model
Cognitive vulnerabilities are mitigated through a layered defence:

### **Layer 1: Model-Level Cognitive Integrity**
Controls that govern how the model expresses uncertainty, generates alternatives, or avoids overly confident tones.

### **Layer 2: Interface-Level Bias Countermeasures**
UI and interaction design that prevents reflex acceptance, emotional drift, or anchoring.

### **Layer 3: Human-Level Safeguards**
Training, workflows, and organizational design that reduce cognitive overload and improve decision quality.

## 6. Foundational Vulnerabilities in This Version
This initial release formalizes:

- **CV-01: Automation Bias Exploitation**  
- **CV-02: Confirmation Bias Exploitation**

These form the base structure for a future **Cognitive Vulnerabilities Top 10**, to be developed by the OWASP community.

