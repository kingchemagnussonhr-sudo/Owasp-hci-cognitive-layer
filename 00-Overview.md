# OWASP Cognitive Vulnerability Companion Framework
### Human–Centered Security Layer for LLM Applications

## 1. Purpose of This Framework
Large Language Models introduce a class of risks that do not arise solely from the model or the system architecture. Many failures originate in *human–AI interaction*, where predictable cognitive patterns amplify technical vulnerabilities.

This companion framework defines a Human–Centered Security Layer that complements the **OWASP Top 10 for LLM Applications**. It formalizes two foundational cognitive vulnerabilities:

- **CV-01 Automation Bias Exploitation**
- **CV-02 Confirmation Bias Exploitation**

These vulnerabilities explain why users may overtrust, misinterpret, or misapply LLM outputs, even when technical controls are in place.

## 2. Why Cognitive Vulnerabilities Matter
LLM failures often occur not because the model is malicious, but because:

- users assume expertise ("the AI probably knows"),  
- users accept outputs too quickly,  
- users align emotionally with the model’s tone,  
- UI design encourages frictionless acceptance,  
- cognitive overload reduces critical evaluation.

Cognitive vulnerabilities sit at the intersection of:

- psychology,  
- HCI and UX design,  
- security engineering,  
- AI behaviour under uncertainty.

This framework introduces structured controls that strengthen security across **model**, **interface**, and **human** layers.

## 3. Scope of the Companion Framework
This framework does *not* replace the OWASP LLM Top 10.  
Instead, it extends it by:

- identifying cognitive risks that amplify technical vulnerabilities,  
- defining detection signals for LLM-driven cognitive drift,  
- providing mitigation strategies across all system layers,  
- formalizing a vocabulary for human–AI failure modes.  

The initial scope includes CV-01 and CV-02.  
Further vulnerabilities will be developed collaboratively by the OWASP community.

## 4. Intended Audience
This framework is designed for:

- security architects  
- LLM developers  
- AI safety researchers  
- UX/HCI designers  
- risk managers  
- organizations deploying AI into workflows  

## 5. Alignment With OWASP Principles
The project follows OWASP values:

- **Open participation**  
- **Transparency**  
- **Community governance**  
- **Evidence-based iteration**

This document is part of an ongoing collaborative process to strengthen LLM security by incorporating the human cognitive layer into risk modeling.

