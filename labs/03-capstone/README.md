# Capstone — build and evaluate a mini assistant

**Work in pairs or solo. Suggested duration: 45 minutes.** Combine prompt engineering, context engineering, and evaluation in one small project. No coding or cloud deployment required.

## Objective

Create a simple assistant grounded in a short reference, test it with five questions (including at least one not covered by the reference), evaluate its answers, and improve one weakness.

## Step-by-step

1. **Choose one use case:** a study buddy for a course topic, FAQ assistant for a small business, or onboarding helper for new hires. Use fictional or publicly shareable content only.
2. **Write your reference:** 10–20 lines of facts in `templates/context-template.md`. State the scope and at least one intentionally undocumented topic. Do not add facts you cannot verify.
3. **Build the system prompt:** Copy [`../../templates/system-prompt-template.md`](../../templates/system-prompt-template.md) and complete Role, Task, Context, Format, and Example.
4. **Create five golden questions:** At least four source-answerable questions and **at least one** deliberately unanswerable question. Record expected answers and source sections in a private/local copy of [`../../templates/golden-questions.csv`](../../templates/golden-questions.csv).
5. **Run the assistant:** Attach/paste the reference, add the system prompt, ask each question in a fresh chat, and save the full answers.
6. **Evaluate:** Score using [`../../EVALUATION.md`](../../EVALUATION.md). Flag any material unsupported claims.
7. **Improve one weak point:** Edit either the system prompt or reference. Record what changed and why.
8. **Rerun the exact same five questions** with the same model and settings. Compare scores before and after.
9. **Share back:** Present the assistant purpose, one tricky test case, one improvement, and what changed in the results.

## Deliverables

- A short reference (10–20 lines)
- A five-part system prompt
- Five golden questions and expected answers
- Five recorded responses, scores, and critical hallucination flags
- One improvement and before/after comparison

## Success criteria

An assistant that answers supported questions from its reference, clearly says when a question is outside its reference, and produces evaluable output. **A polished answer is not necessarily a correct answer.**

## Starter material

- [`templates/context-template.md`](templates/context-template.md)
- [`../../templates/system-prompt-template.md`](../../templates/system-prompt-template.md)
- [`../../templates/golden-questions.csv`](../../templates/golden-questions.csv)
- [`../../templates/response-log.csv`](../../templates/response-log.csv)
