# Response evaluation scorecard

Score **each response** using the source document and the system instructions applicable to that exercise.

| Criterion | 0 | 1 | 2 |
|---|---|---|---|
| Factual accuracy | Incorrect or misleading | Partly correct | Correct according to source |
| Source grounding | Unsupported product/company claims | Some claims ungrounded | Claims supported or explicitly unknown |
| Instruction adherence | Ignores applicable instructions | Partially follows | Follows applicable instructions |
| Format adherence | Ignores specified format | Partially follows | Follows format fully |
| Unknown handling | Invents facts or asserts undocumented claims | Acknowledges gaps inconsistently | Clearly acknowledges missing information |

**N/A:** If no output format was specified (exercises 1–3), mark Format **N/A**. If the question is fully answerable and unknown handling is not exercised, Unknown handling can be **N/A**. Do not award points for criteria that cannot be observed.

## Score calculation

- `Points earned = sum of scored criteria`.
- `Possible points = 2 × number of applicable criteria`.
- `Percentage = 100 × earned / possible` (if no criteria apply, mark **Not scored**).
- **Pass:** ≥80% **and** Critical Hallucination = No.
- **Needs improvement:** ≥50% and <80%, Critical Hallucination = No.
- **Fail:** <50%, **or Critical Hallucination = Yes**, regardless of percentage.

## Critical Hallucination Flag (Yes/No)

Mark **Yes** if the model presents a *materially unsupported product or company-specific claim* as a verified fact. Examples:

- Claims Nimbus Notes integrates with Slack and provides made-up configuration steps.
- Claims Brightpath permits three remote-work days per week without evidence.
- Invents an insurance premium, refund exception, allowance, or price not stated in the source.

Record the exact claim and the relevant reference section. An honest statement that the fact sheet **does not document** something is **not** a hallucination.

## Participant workflow

1. Copy the assistant's answer verbatim into your response log.
2. Compare each factual statement to the FAQ or fact sheet.
3. Score the five criteria (0, 1, 2, or N/A).
4. Mark Critical Hallucination Yes/No and explain any Yes.
5. Calculate percentage and result using the rules above.
6. Propose one improvement, rerun the **same question**, and compare the result.

**Optional LLM-as-judge:** Use a fresh chat with the reference, question, assistant response, and rubric. Ask it to return scores and evidence; then verify its judgments manually. See [`templates/judge-prompt.md`](templates/judge-prompt.md). Never treat a judge model's score as automatically correct.
