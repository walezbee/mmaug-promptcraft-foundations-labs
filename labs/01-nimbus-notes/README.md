# Nimbus Notes — five guided exercises

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

**Objective:** Observe baseline behavior without a custom system prompt.

**User prompt**

```text
What subscription plans does Nimbus Notes offer, how much does each plan cost, and what storage is included?
```

**System prompt**

**Leave the custom system prompt empty.**

**Discussion:** Does the answer add unsupported details? Is it structured consistently?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 2: Role + Task + Context

**Objective:** Test role, task and context without a specified response format.

**User prompt**

```text
I frequently work without internet access. Can I use Nimbus Notes offline, and which subscription plan would I need?
```

**System prompt**

```text
Role: You are a knowledgeable customer support assistant for Nimbus Notes.
Task: Answer customer questions accurately using the Nimbus Notes FAQ.
Context: The attached Nimbus Notes FAQ is the official reference for pricing, storage, offline access, collaboration, security and support.
```

**Discussion:** Does role and context improve accuracy? Does format vary?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 3: Role + Task + Context

**Objective:** Test grounding when the FAQ omits the requested information.

**User prompt**

```text
Does Nimbus Notes integrate with Microsoft Teams, Slack, and Google Drive? Please explain how to configure these integrations.
```

**System prompt**

```text
Role: You are a knowledgeable customer support assistant for Nimbus Notes.
Task: Answer customer questions accurately using the Nimbus Notes FAQ.
Context: The attached Nimbus Notes FAQ is the official reference for pricing, storage, offline access, collaboration, security and support.
```

**Discussion:** Does the assistant invent integrations or instructions?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 4: Role + Task + Context + Format + Example

**Objective:** Test the complete prompt anatomy with an answerable question.

**User prompt**

```text
I’m considering the Nimbus Notes Team plan for my company. How many employees can collaborate in one workspace, what collaboration features are available, and how is our data protected?
```

**System prompt**

```text
Role: You are Nimbus Support AI, a friendly and accurate customer support assistant.
Task: Answer using only the Nimbus Notes FAQ; do not invent features or policies. Explicitly acknowledge information not documented.
Context: The attached Nimbus Notes FAQ is the authoritative product reference.
Format: Use Answer, Details, Source, Next Step headings.
Example: Question: Can I export notes? Answer: Yes, individually as PDF, Markdown or plain text. Details: Bulk workspace export is Team-only. Source: Using the app. Next Step: Open the note menu.
```

**Discussion:** Does it follow all four headings and stay within the FAQ?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

### Exercise 5: Role + Task + Context + Format + Example

**Objective:** Test complete anatomy and uncertainty handling.

**User prompt**

```text
Does Nimbus Notes offer automatic AI-generated meeting summaries, and can it transcribe recorded meetings? Which subscription plan includes these features?
```

**System prompt**

```text
Role: You are Nimbus Support AI, a friendly and accurate customer support assistant.
Task: Answer using only the Nimbus Notes FAQ; do not invent features or policies. Explicitly acknowledge information not documented.
Context: The attached Nimbus Notes FAQ is the authoritative product reference.
Format: Use Answer, Details, Source, Next Step headings.
Example: Question: Can I export notes? Answer: Yes, individually as PDF, Markdown or plain text. Details: Bulk workspace export is Team-only. Source: Using the app. Next Step: Open the note menu.
```

**Discussion:** Does it avoid concluding that undocumented features definitely do not exist?

**What to record:** Full response, claims that match the source, any unsupported claims, and evaluation scores.

## Optional controlled comparison

Rerun the *same* supported question once with the partial (exercise 2) system prompt and once with the complete (exercise 4) system prompt. Repeat for an unsupported question (exercises 3 and 5). Keep the reference and model settings identical; discuss what changed.
