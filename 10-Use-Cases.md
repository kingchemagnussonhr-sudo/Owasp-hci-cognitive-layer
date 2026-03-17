
## Empirical Evidence Base

The following studies provide empirical support for the cognitive 
vulnerabilities described in this framework. Each entry maps to 
one or more CV entries and sector use cases.

---

### CV-01 — Automation Bias

#### Healthcare / Radiology

**Dratsch et al. (2023)**  
Automation bias in mammography: The impact of artificial 
intelligence BI-RADS suggestions on reader performance.  
*Radiology*

27 radiologists read 50 mammograms with AI-assisted decision 
support. When the AI suggested an incorrect BI-RADS category, 
accuracy among inexperienced radiologists fell from 80% to below 
20%. Experienced radiologists (15+ years) fell from 82% to 45.5%.

Finding relevant to CV-01: High-confidence AI output suppressed 
independent verification even among experienced clinicians.

DOI: 10.1148/radiol.222176  
URL: https://pubs.rsna.org/doi/10.1148/radiol.222176

---

**Kücking et al. (2024)**  
Automation Bias in AI-Decision Support: Results from an 
Empirical Study.  
*Studies in Health Technology and Informatics*

Quantitative intervention study with 210 healthcare professionals 
(nurses and physicians) across German hospitals. Non-specialists 
showed highest susceptibility to automation bias, as measured by 
agreement rate with incorrect AI recommendations.

Finding relevant to CV-01: Those with least domain expertise — 
and therefore most dependent on AI support — were most 
vulnerable to uncritical acceptance of incorrect outputs.

DOI: 10.3233/SHTI240871  
URL: https://pubmed.ncbi.nlm.nih.gov/39234734/

---

### CV-02 — Confirmation Bias

#### Legal / Compliance

**Dahl et al. (2024)**  
Large Legal Fictions: Profiling Legal Hallucinations in 
Large Language Models.  
*Journal of Legal Analysis, Oxford University Press*

Systematic empirical evaluation of LLM performance on legal 
tasks. Documents susceptibility to contrafactual bias: LLMs 
frequently provide confident, seemingly legitimate answers to 
legal questions whose premises are false by construction.

Finding relevant to CV-02: Users anchored in an incorrect legal 
premise received confirmation rather than correction, with the 
model generating fluent but false legal reasoning.

DOI: 10.1093/jla/laae003  
URL: https://academic.oup.com/jla/article/16/1/64/7699227

---

### CV-01 + CV-02 — Combined vulnerability

#### Public Administration

**Alon-Barkat & Busuioc (2023)**  
Human–AI Interactions in Public Sector Decision Making: 
"Automation Bias" and "Selective Adherence" to Algorithmic Advice.  
*Journal of Public Administration Research and Theory*

Three experimental studies in the Netherlands (N=2,854), 
including a sample of civil servants. Documents selective 
adherence: decision-makers adopt algorithmic recommendations 
more readily when outputs align with pre-existing group 
stereotypes. The Dutch childcare benefits scandal is used as 
a real-world illustration.

Finding relevant to CV-01 + CV-02: Cognitive vulnerability 
in public sector AI is not primarily automation bias in its 
classic form, but selective confirmation — the algorithm 
amplifies existing human bias rather than introducing new error.

DOI: 10.1093/jopart/muac007  
URL: https://academic.oup.com/jpart/article/33/1/153/6524536

---

### To add a new entry

Copy the block below and fill in:

**Author(s) (year)**  
Full title.  
*Journal or venue*

One paragraph describing study design and sample.

Finding relevant to CV-[XX]: One sentence on what this 
study shows about the specific vulnerability.

DOI: [doi]  
URL: [url]
```

---

