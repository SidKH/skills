---
name: explain-code
description: Explain code as a scannable blog post
disable-model-invocation: true
---

# Explain Code

Write a **short, scannable** explanation: one main idea per `##` section, plain language in the prose, code that pulls the eye. **Hold attention**; **do not overwhelm**. Use the same shape for whatever code or scope the user points at; **their ask and their scope** define the topic, not a preset checklist of scenarios.

## What the answer looks like

The reply has **three parts**, in order:

| Part | Role |
|------|------|
| **`#` Title** | One line: what this explanation is about. |
| **📋 TLDR** | 2–3 short sentences: the gist for someone who did not write the code. **No** `##` here; no bullet list in the tldr unless the user asked for bullets. |
| **One or more `##` sections** | Each section = one idea that can stand on its own, a plain-English **`##` title** with **at least one emoji** (see [Body sections](#body-sections)), and **always** at least one **fenced code** block. |

Everything below explains *how* to write those three parts.

## Title

- **One line.**
- Names the topic in plain terms.

## 📋 TLDR

- **2–3 short sentences.**
- **Plain language** — see [Plain language](#plain-language) (same bar as section lead-ins: one idea per sentence, no “gumbo”).
- A teammate should get the point in **one read**.

**Same story, two densities** (favor the second):

- *Too dense:* “This change expands the flow, wires several helpers together, and defers rendering until preprocessing finishes so output stays deterministic.”
- *Clearer:* “This change makes the flow longer so each step has room to read. The code waits for preprocessing before it renders. That prevents partial output from flashing on screen.”

## Body sections

Each `##` is **one block** in a blog: title → short intro → code → optional short tail. A reader should be able to jump into any single section and still follow it.

1. **`##` title** — Plain English: what this part is *about*, **and include at least one emoji in every `##` title** (for example, `## 🔁 How the retry path works`). The emoji should fit the section’s topic; one per title is enough. Short and scannable; not a dump of symbols and file names unless the user wants that formality. If you use numbering, **stay consistent** within one answer (e.g. `## 1. 🔧 How the retry path works` or `## 🔧 How the retry path works` without numbers—pick one pattern and keep it). Prefer **several small** sections over one long one. **Do not** decorate the top-level `#` title or the **📋 TLDR** block with ornamental symbols—emojis are **only** for `##` body section titles.
2. **Lead-in** — **One or two** simple sentences. Same [Plain language](#plain-language) rules as the tldr. The reader should understand the point of the section **before** reading the code. Avoid symbol names unless they are needed for orientation.
3. **At least one fenced code block** — With **line comments** that mark what matters (*what* / *why* at the right lines). Keep the real code and real symbol names, but make the comments easy to scan in plain English. Do **not** let comments repeat the lead-in verbatim. You may use `...` or `// ...` when truncation is obvious.
4. **After the code (optional)** — At most **one or two** short plain sentences. Use this to restate the takeaway or connect the snippet back to the section title. Do not spend this space introducing a new implementation detail.

### Snippet required for every `##`

- **No prose-only `##` sections.** Every section must end with the reader having seen real code in a fence.
- If an idea is hard to “attach” to code, show the **smallest honest excerpt** anyway—whatever minimal lines the scope actually contains.
- If two small ideas are each too thin for a fence **alone**, **merge** them into one `##` and use **one** snippet (with comments for two sub-parts) so you still have code on screen.

**Cover the scope** with as many `##` blocks as needed. Skip empty blocks. When you merge small points, the merged `##` must still have **at least** one snippet.

## Plain language

Applies to the **tldr**, **lead-ins**, and **post-code** lines. It does **not** mean the code itself must be rewritten in simple terms; the prose should translate the code, not flatten it.

- **One main idea per sentence.** More sentences beat more commas in one sentence.
- **Short, common words** where you can. Use jargon only when the code or topic forces it; introduce it **once**.
- **Simple story first**, detail second: what this is for → what it does in broad terms → only then the sharp edge (API names, timing, lifecycle details, etc.).
- **No “explanation gumbo”** — avoid one sentence that chains many tools, paths, and behaviors with dashes and nested parentheses.
- **No compressed shorthand** in prose. Avoid phrases that read like private notes, slogans, or internal labels unless the user already asked for that style.
- **Avoid mixed-mode sentences.** Do not combine metaphor, code names, and behavioral detail in the same sentence when a simpler sentence would do.
- **Clarity over cleverness**; **simple over comprehensive** in prose. The prose should be easy to read aloud to a teammate.
- **Scannable:** headings and snippets carry most of the load; keep surrounding prose short.

## Prose vs. code

- **Prose** should explain the idea in plain English.
- **Code** should stay technically honest: keep real names, real syntax, and the smallest useful excerpt.
- **Comments inside the code fence** should bridge the two: point at the exact lines that matter and translate them into everyday language.
- Prefer prose that says what the section is about in human terms, then use the code and comments to show where that idea lives.

## Code snippets (how to pick and annotate)

- Keep snippets **short**; include only the lines needed to follow the point.
- Comments in the fence should **direct attention** (what to notice next), not restate a whole paragraph.
- In the comment, make clear **what the code does** in context and **why this bit matters** for the current section.
- Put comments at the lines where the important shift happens, not only at the top of the snippet.
- Write comments like quick guide rails for the eye, not like API reference notes.
- If the code is dense, prefer a slightly smaller excerpt with clearer comments over a larger excerpt with sparse comments.

## Scope

- Explain what the user scoped (file, range, diff, question).
- If they gave no scope, default to the **unstaged diff** when you can infer it from context.

## Guardrails

- **Do not invent intent** that is not supported by the code or the user’s prompt.
- **Tone** — like a good technical post: direct and clear, not a tutorial essay and not a disconnected tweet thread.
