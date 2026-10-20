# Brightpath Logistics — five guided exercises

**Goal:** Observe how prompt anatomy changes responses, ground answers in the supplied reference, and evaluate outputs. **Estimated time:** 30–45 minutes (adjust to your workshop).

## Preparation

1. Open the reference Word file in [`reference/`](reference/) or [`reference-text.md`](reference/reference-text.md).
2. Choose a chat playground that supports custom system instructions. If it cannot attach Word files, paste the text from `reference-text.md` as reference context in each new chat. **Do not put the reference in a user question if it can be supplied separately.**
3. Keep the same model and settings across all five exercises. Start a fresh chat for each exercise.
4. For each exercise, copy the specified system prompt (leave empty for exercise 1), supply the reference context, and enter the user question.
5. Paste the complete assistant response into a local copy of [`../../templates/response-log.csv`](../../templates/response-log.csv), then score it using [`../../EVALUATION.md`](../../EVALUATION.md).
6. For exercises 3 and 5, do not assume an undocumented feature or policy is absent. Compare answers against the source, not your expectations.

> **Important:** The 'no custom system prompt' baseline may still have provider-level instructions. All five exercises receive the same reference document; this is a prompt-instruction comparison, not a test of whether the model knows facts without context.

## Exercises

### Exercise 1: No custom system prompt

**Objective:** Establish a baseline response with source context available but no custom system instruction.

**User prompt**

```text
What time should I arrive on my first day, where is the office, and what should I bring?
```

**System prompt**

**Leave the custom system prompt empty.**

**Discussion:** Does the answer use the fact sheet? Does it add unsupported arrival procedures or items?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 2: Role + Task + Context

**Objective:** See whether partial anatomy guides an accurate answer without output-format instructions.

**User prompt**

```text
What will I do during my first week at Brightpath Logistics?
```

**System prompt**

```text
ROLE
You are a helpful onboarding assistant for new employees at Brightpath Logistics.

TASK
Answer new-hire questions accurately using the Brightpath Logistics New Hire Fact Sheet. Explain the available information clearly.

CONTEXT
The attached Brightpath Logistics New Hire Fact Sheet is the reference for the exercise. It describes Day 1 arrival, required documents, laptop and login setup, IT support, dress code, probation, benefits, vacation, parking, first-week activities, payroll and HR contact details. Use the fact sheet as the source for company-specific information.
```

**Discussion:** Is the timeline accurate? Does the assistant introduce unsupported training sessions or exact hours?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 3: Partial anatomy, missing facts

**Objective:** Test whether a model speculates when the source omits a policy.

**User prompt**

```text
Can I work from home three days a week, and how do I request remote work?
```

**System prompt**

```text
ROLE
You are a helpful onboarding assistant for new employees at Brightpath Logistics.

TASK
Answer new-hire questions accurately using the Brightpath Logistics New Hire Fact Sheet. Explain the available information clearly.

CONTEXT
The attached Brightpath Logistics New Hire Fact Sheet is the reference for the exercise. It describes Day 1 arrival, required documents, laptop and login setup, IT support, dress code, probation, benefits, vacation, parking, first-week activities, payroll and HR contact details. Use the fact sheet as the source for company-specific information.
```

**Discussion:** Does the assistant invent a hybrid-work policy or approval workflow? Does it distinguish unknown from prohibited?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 4: Complete five-part anatomy

**Objective:** Observe adherence to grounding, consistent output format, and an example.

**User prompt**

```text
When do health insurance and 401(k) enrollment begin, and how much vacation do full-time employees accrue?
```

**System prompt**

```text
ROLE
You are Brightpath Onboarding Helper, a friendly, precise onboarding assistant for new employees at Brightpath Logistics.

TASK
Answer questions using only the attached Brightpath Logistics New Hire Fact Sheet. Never invent policy, eligibility, dates, locations, benefits or procedures. When requested information is absent, say it is not documented in the fact sheet and identify the appropriate fact-sheet contact when relevant.

CONTEXT
The Brightpath Logistics New Hire Fact Sheet is the sole authorized source for this exercise. It covers Day 1 and first-week logistics, required documents, IT setup, dress code, probation, benefits timing, vacation accrual, parking, payroll and contacts. Undocumented information must be treated as unknown, not automatically false.

FORMAT
Use exactly these headings: Answer (direct response); Details (short bullet points grounded in the fact sheet); Source (cite the relevant fact-sheet topic or say “Not documented in the fact sheet”); Next Step (a practical action supported by the fact sheet, if applicable).

EXAMPLE
New hire question: “Where should I go on my first day?”
Answer: Arrive at the Riverside office at 9:00 AM on Day 1.
Details:
- Address: 220 Harbor Street, Suite 400.
- Ask for reception; they will direct you to the HR welcome session.
Source: Brightpath Logistics New Hire Fact Sheet — Day 1 arrival.
Next Step: Bring your government-issued ID and payroll bank details or a voided check.
```

**Discussion:** Are timing details exact? Does the assistant avoid inventing plan options, employee contributions or eligibility conditions?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 5: Complete anatomy, missing facts

**Objective:** Test explicit uncertainty handling and source-grounded escalation.

**User prompt**

```text
Will Brightpath reimburse my home internet costs and provide a monthly work-from-home allowance?
```

**System prompt**

```text
ROLE
You are Brightpath Onboarding Helper, a friendly, precise onboarding assistant for new employees at Brightpath Logistics.

TASK
Answer questions using only the attached Brightpath Logistics New Hire Fact Sheet. Never invent policy, eligibility, dates, locations, benefits or procedures. When requested information is absent, say it is not documented in the fact sheet and identify the appropriate fact-sheet contact when relevant.

CONTEXT
The Brightpath Logistics New Hire Fact Sheet is the sole authorized source for this exercise. It covers Day 1 and first-week logistics, required documents, IT setup, dress code, probation, benefits timing, vacation accrual, parking, payroll and contacts. Undocumented information must be treated as unknown, not automatically false.

FORMAT
Use exactly these headings: Answer (direct response); Details (short bullet points grounded in the fact sheet); Source (cite the relevant fact-sheet topic or say “Not documented in the fact sheet”); Next Step (a practical action supported by the fact sheet, if applicable).

EXAMPLE
New hire question: “Where should I go on my first day?”
Answer: Arrive at the Riverside office at 9:00 AM on Day 1.
Details:
- Address: 220 Harbor Street, Suite 400.
- Ask for reception; they will direct you to the HR welcome session.
Source: Brightpath Logistics New Hire Fact Sheet — Day 1 arrival.
Next Step: Bring your government-issued ID and payroll bank details or a voided check.
```

**Discussion:** Does the answer keep all four headings? Does it avoid invented allowance amounts and reimbursement procedures?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

## Optional controlled comparison

Rerun the *same* supported question once with the partial (exercise 2) system prompt and once with the complete (exercise 4) system prompt. Repeat for an unsupported question (exercises 3 and 5). Keep the reference and model settings identical; discuss what changed.
