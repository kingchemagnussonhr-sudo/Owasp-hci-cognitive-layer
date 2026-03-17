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

Case 1: Legal: contract interpretation
Ankarbias i LLM-baserat juridiskt beslutsfattande
Den starkaste källan är en studie publicerad i Artificial Intelligence and Law (Springer, januari 2026). Forskarna replikerade Teichman et al. (2023) på sju avancerade LLM:er, däribland GPT-4o och Claude Sonnet, och fann att modellerna systematiskt visade ankarbiasrekommenderade signifikant längre straff när de exponerades för irrelevanta numeriska ankare. Springer Det som är extra relevant för ditt CV-03-scenario: kunskapsförstärkning förvärrade faktiskt ankarbiasen — mer juridisk information i prompten ökade snarare än minskade effekten. Springer Det betyder att en jurist som litar på en välkalibrerad, vältränad modell kan vara mer utsatt, inte mindre.
Den klassiska mänskliga grunden för detta är Englich, Mussweiler & Strack (2006) — "Playing dice with criminal sentences" — som visade att erfarna domare ankrade domslut på slumpmässiga tärningskast. Denna studie citeras direkt i LLM-studien ovan och ger den mänskliga baslinje som CV-03 bygger på.



Case 2: AI-assisted medical diagnosis (2023 meta-analysis)

Clinicians using AI diagnostic support accepted incorrect diagnoses at significantly higher rates when AI confidence scores were displayed as percentages rather than ranges. CV-01 pattern: High-confidence output suppresses independent evaluation. Source: Goddard et al., NPJ Digital Medicine, 2023.


Case 3: Finans — ankarbias i LLM-investeringsanalys
Här finns en stark empirisk källa från ScienceDirect (2024): En studie testade om ChatGPT uppvisar ankarbias i finansiella prognoser, inklusive extrema ankare som ett S&P 500-värde på 59 175 — och fann att LLM-svar är känsliga för biasade ledtrådar, i linje med tidigare fynd på människor inom aktiemarknadsprognoser, kryptovaluta och kreditbeslut. ScienceDirect
En ännu skarpare källa för det exakta scenariot med analytikern som inte reviderar sin bedömning är studien "Your AI, Not Your View" (ACM Conference on AI in Finance, 2025): Modeller uppvisade en tydlig konfirmationsbias — när de konfronterades med motbevis, oavsett volym och styrka, vägrade de envist att revidera sina bedömningar, och höll fast vid bevis som bekräftade deras interna kunskaper medan de ignorerade motbevis. arXiv Detta är CV-03 beskriven på modellnivå — men eftersom analytikern tar emot och itererar med modellen, speglas detta direkt i det mänskliga beteendet.


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
