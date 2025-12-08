# Cognitive Vulnerability Incident Template

## 1. Incident Overview
- **Date:** [YYYY-MM or "Estimated Q2 2024"]
- **Domain:** [Healthcare / Finance / Legal / Customer Support / Education / etc.]
- **LLM System:** [GPT-4 / Claude / Internal Model / Fine-tuned model / Unknown]
- **Context:** [Chat interface / Agentic workflow / API integration / Decision support]
- **Anonymization:** [Company removed / Roles generalized / Sensitive details omitted]

---

## 2. Suspected Cognitive Vulnerability
Select all that appear relevant:

- [ ] **CV-01 Automation Bias** (overreliance on AI output)
- [ ] **CV-02 Confirmation Bias** (LLM reinforces prior beliefs)
- [ ] **Possible new CV** (describe pattern):

---

## 3. What Happened (Narrative)
Describe the sequence of events:

- What did the *user* do, expect, or assume?  
- What did the *AI* output, omit, or phrase misleadingly?  
- What decision was influenced by the AI response?

[Free text]

---

## 4. Cognitive Contribution Analysis
Explain *why cognition mattered*:

- Which cognitive pattern(s) influenced the user?
- Why was the user vulnerable in that moment (overload, stress, time pressure, ambiguity)?
- How did the model’s output reinforce or exploit that pattern?

[Free text]

---

## 5. Technical Factors (Optional)
Was there also a technical vulnerability?

- OWASP LLM Top-10 categories involved:
  - [ ] LLM01 Prompt Injection
  - [ ] LLM02 Insecure Output Handling
  - [ ] LLM03 Training Data Issues
  - [ ] LLM08 Excessive Agency
  - [ ] LLM09 Overreliance
  - [ ] Other: ____________________

[Describe technical interactions, if known]

---

## 6. Outcome
- **Severity:** [Critical / High / Medium / Low]
- **Impact Type:**  
  - [ ] Financial loss  
  - [ ] Reputational damage  
  - [ ] Privacy breach  
  - [ ] Safety risk  
  - [ ] Operational disruption  
  - [ ] Policy/Compliance error  
- **Detection:**  
  - [ ] Prevented before harm  
  - [ ] Detected after incident  
  - [ ] Only discovered during review  
  - [ ] Never detected (hypothetical reconstruction)

---

## 7. Potential Mitigations (Hypothesis Stage)
What might have prevented this?

Consider:
- Model-level mitigations  
- Interface-level friction or warnings  
- Human-level safeguards  

[Free text]

---

## 8. Evidence Type
- [ ] First-hand observation  
- [ ] Reported by colleague  
- [ ] Derived from an incident report  
- [ ] Hypothetical scenario based on recurrent real-world patterns  
- [ ] Mixed evidence  

---

## 9. Additional Notes (Optional)
Anything that doesn't fit elsewhere.

[Free text]
