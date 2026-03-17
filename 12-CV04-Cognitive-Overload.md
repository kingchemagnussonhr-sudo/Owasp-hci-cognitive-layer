# CV-04: Cognitive Overload Exploitation
### Users miss critical information due to output volume or complexity.

## 1. Definition
Cognitive Overload occurs when LLM output exceeds the user's working
memory capacity, causing them to process selectively and miss
critical warnings, caveats, or contradictory information.

## 2. Detection Signals
- Output length significantly exceeds task complexity
- Critical information is buried in mid-output position
- User interaction ends immediately after long output (no follow-up)

## 3. Mitigations
### Model-Level
- Enforce progressive disclosure: summary first, detail on request
- Surface critical warnings at beginning AND end of output
### Interface-Level
- Highlight caveats and uncertainty markers visually
- Limit default output length for high-stakes task categories

## 5. OWASP Alignment
Amplifies: LLM02 Insecure Output Handling, LLM09 Overreliance.
