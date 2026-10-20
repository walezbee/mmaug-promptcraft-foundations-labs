# Optional LLM-as-judge prompt

Use a **new chat** for the judge. Supply the same reference document plus the question and assistant answer; do not let the judge answer the original question instead of evaluating it.

```text
ROLE: You are an evaluator, not the customer-support assistant.
TASK: Compare the assistant answer against the reference document and the applicable system prompt. Use only the reference to verify organization-specific claims.
INPUTS:
- Reference: [PASTE DOCUMENT]
- Applicable system prompt: [PASTE SYSTEM PROMPT OR SAY NONE]
- User question: [PASTE QUESTION]
- Assistant response: [PASTE VERBATIM ANSWER]
FORMAT:
Return Factual accuracy, Source grounding, Instruction adherence, Format adherence, Unknown handling (each 0/1/2 or N/A); Critical Hallucination (Yes/No); exact unsupported claim if Yes; one-sentence evidence-based explanation. Do not invent facts missing from the reference.
```

Manually verify every judge result, particularly any critical hallucination flag.
