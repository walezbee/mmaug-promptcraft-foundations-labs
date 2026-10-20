# MMAUG Prompt Craft Foundations - Beginner Labs

**Prompt Engineering · Context Engineering · AI Evaluation**  
A beginner-friendly, lab-based workshop using fictional training documents. No coding required for the core activities.

## Learning objectives

By the end, learners can:

1. Identify **Role, Task, Context, Format, and Example** in a system prompt and compare partial and complete instructions.
2. Provide a reference document as context and distinguish source-supported answers from unsupported assertions.
3. Test an assistant with questions **covered** and **not covered** by the reference.
4. Evaluate responses for accuracy, grounding, instruction adherence, format, and handling unknown information.
5. Improve a mini assistant and re-run the same test questions to verify the change.

## Repository map

| Path | Purpose |
|---|---|
| [`SETUP.md`](SETUP.md) | Prerequisites and setup (no-code first) |
| [`labs/01-nimbus-notes/`](labs/01-nimbus-notes/) | Five product-support exercises and FAQ |
| [`labs/02-brightpath-onboarding/`](labs/02-brightpath-onboarding/) | Five new-hire onboarding exercises and fact sheet |
| [`labs/03-capstone/`](labs/03-capstone/) | Build and evaluate a mini assistant, solo or in pairs |
| [`EVALUATION.md`](EVALUATION.md) | Rubric, critical hallucination rule, score calculation |
| [`templates/`](templates/) | Copyable prompt and CSV templates |
| [`CLEANUP.md`](CLEANUP.md) | Cost controls and cleanup |

## Quick start

1. Read [`SETUP.md`](SETUP.md) and select an available chat playground.
2. Open the [Nimbus Notes exercises](labs/01-nimbus-notes/README.md) and attach or paste its FAQ as context.
3. Run all five exercises in **fresh chats**, recording responses.
4. Repeat with [Brightpath Logistics](labs/02-brightpath-onboarding/README.md).
5. Evaluate with [`EVALUATION.md`](EVALUATION.md) and your own copy of [`templates/response-log.csv`](templates/response-log.csv).
6. Complete the [capstone](labs/03-capstone/README.md).

## Important training boundaries

- **Nimbus Notes and Brightpath Logistics are training scenarios.** Email addresses using `.example` are placeholders; do not send messages or enter real employee, customer, payroll, or identity information.
- The reference documents are the **sole authorized sources** of product or company facts for these labs. An undocumented feature or policy is **unknown**, not automatically unavailable.
- A blank *custom* system prompt does not mean a model has no other instructions.
- Scores are teaching aids, not certification of model safety or reliability.
- Public repository contents (including facilitator answers) are accessible to everyone. Never commit API keys, private company material, or participant responses containing personal information.

## Cloud usage

**Core labs require no deployment, code execution, or paid cloud resources.** Some AI playgrounds charge for inference or storage; review their pricing and quotas first. See [`CLEANUP.md`](CLEANUP.md).

## Attribution

Prepared for the MMAUG AI & DevOps Bootcamp from the supplied Nimbus Notes FAQ, Brightpath Logistics Fact Sheet, and Prompt Craft Foundations beginner lab scenarios. The training documents are included in editable Word and searchable Markdown form.
