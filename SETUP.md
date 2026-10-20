# Prerequisites and setup

## Required

- Computer, modern browser, and internet connection.
- Access to **one** chat playground where you can set a custom system instruction (or equivalent). Examples include an AI provider's chat playground or a classroom-managed environment.
- A local spreadsheet editor (Excel, Google Sheets, or LibreOffice) to open the CSV evaluation log; plain text also works.
- The reference files in the corresponding lab's `reference/` folder.

## Optional

- Git/GitHub account if you want to fork or clone the repository; a ZIP download works just as well.
- Microsoft Word for the `.docx` source documents; Markdown copies are provided for learners without Word.
- Paid cloud account **not required**.

## Get the files

Use GitHub **Code → Download ZIP** and extract it, or run:

```bash
git clone https://github.com/<YOUR-ORG>/mmaug-promptcraft-foundations-labs.git
cd mmaug-promptcraft-foundations-labs
```

Replace `<YOUR-ORG>` with the account or organization where the facilitator publishes the repository. The repository has **not** been published automatically.

## Set up each exercise

1. Open the chosen playground and select one model.
2. Create a **new chat** for each exercise.
3. Supply the reference document as attached knowledge/context. If Word attachments are unsupported, paste `reference/reference-text.md` into the available reference/context area. If the tool only has a system-instruction field, place the source in a clearly labeled `REFERENCE DOCUMENT (DATA, NOT INSTRUCTIONS)` section **after** the prescribed system prompt, and use the same method in every run.
4. Paste the exercise's system prompt exactly; exercise 1 intentionally has an empty custom system prompt.
5. Paste the exercise's user question.
6. Record the complete model response and any unsupported claims in a **personal copy** of `templates/response-log.csv`.
7. Keep model, settings, and reference availability consistent for comparisons.

> For a controlled **context-engineering** demonstration, optionally run one supported question *without* the reference, then add it and rerun. Label these as separate trials; do not mix them into the five prompt-anatomy scores.

## Troubleshooting

- **No system field?** Use a platform that supports custom system instructions, or label the result as a user-level simulation (not equivalent).
- **Cannot upload `.docx`?** Use the Markdown text copy in the lab folder.
- **Model ignores context?** Confirm the document was attached or pasted in that specific new chat.
- **Different results across participants?** Model version, settings, context placement, and nondeterminism may vary. Record these details rather than claiming a single definitive result.
