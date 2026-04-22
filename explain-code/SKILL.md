---
name: explain-code
description: Explain code as a scannable blog post
disable-model-invocation: true
---

# Explain Code

Write a short, scannable explanation of the code the user scoped. Favor plain-English prose and small, high-signal code snippets. Explain the idea, not the whole file.

## Core contract

These are the non-negotiable rules. If a later section seems to conflict, follow this section.

- Match the user's scope. If they scoped a file, range, diff, or question, explain that and nothing broader.
- Use this shape in order: `#` title, `📋 TLDR`, then one or more `##` sections.
- Each `##` section covers one idea and must include at least one fenced code block.
- Keep prose simple and short. One main idea per sentence.
- Keep snippets small. Show the minimum code needed to support the section's point.
- Be technically honest. Simplify or shorten code when it helps, but do not misrepresent behavior.
- Do not invent intent that is not supported by the code or the prompt.

## Output shape

### `#` Title

- One line.
- Name the topic in plain terms.

### `📋 TLDR`

- 2-3 short sentences.
- State the gist for someone who did not write the code.
- No `##` headings here.
- No bullet list unless the user asked for bullets.
- Optional: one small `mermaid` block only if the main story is easier to see as flow or handoff.

### `##` Sections

Each section uses this shape:

1. A plain-English `##` title with at least one emoji.
2. A one- or two-sentence lead-in.
3. A fenced code block.
4. Optional: one or two short sentences after the code.

Use several small sections instead of one large section. If you number section titles, keep the numbering style consistent across the whole answer.

## Writing rules

These rules apply to the `📋 TLDR`, section lead-ins, and any short text after code blocks.

- Use short, common words where possible.
- Put the simple story first, then details.
- Avoid dense sentences that mix code names, behavior, and metaphor.
- Avoid private shorthand or unexplained jargon.
- Let headings and snippets do most of the work; keep surrounding prose light.

## Snippet rules

Each code fence should work like a guided sketch, not a file dump.

- Default to about 10 non-blank lines or fewer. Single digits are often better.
- Every line should support the current section's point.
- Remove unrelated imports, branches, props, styling noise, and helper code.
- Use `...`, `// ...`, renamed placeholders, or simplified identifiers when they make the idea easier to see.
- Add sparse comments only where they direct the eye to the important shift or decision.
- Do not repeat the lead-in sentence as a code comment.

If a point feels too small for its own snippet, merge it into a neighboring section rather than creating a prose-only section.

## Simplification policy

The prose explains the idea in human terms. The code proves that idea with the smallest honest example.

- Prefer real names when they matter for orientation or the user asked for fidelity.
- Prefer simplified names or pseudocode when verbatim code would add noise.
- Verbatim excerpts are the exception, not the default.
- Faithfulness to behavior matters more than copying exact source text.

## Scope defaults

- Explain the exact scope the user gave you.
- If the user gave no scope and you can infer local context, default to the unstaged diff.
- Skip empty sections instead of forcing a checklist.

## Guardrails

- Do not include long literals, secrets, or opaque blobs when a placeholder teaches the same point.
- Do not use diagrams other than the optional `mermaid` block in the `📋 TLDR`.
- Do not let the explanation turn into a line-by-line transcript unless the user explicitly asked for that.
