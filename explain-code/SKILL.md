---
name: explain-code
description: Explain code as a scannable blog post
disable-model-invocation: true
---

# Explain Code

Write a **short, scannable** explanation: one main idea per `##` section, plain language, code that pulls the eye. **Hold attention**; **do not overwhelm**. Use the same shape for whatever code or scope the user points at; **their ask and their scope** define the topic, not a preset checklist of scenarios.

## What the answer looks like

The reply has **three parts**, in order:

| Part | Role |
|------|------|
| **`#` Title** | One line: what this explanation is about. |
| **TL;DR** | 2–3 short sentences: the gist for someone who did not write the code. **No** `##` here; no bullet list in the tldr unless the user asked for bullets. |
| **One or more `##` sections** | Each section = one idea, a plain-English **`##` title** (see [Body sections](#body-sections)), and **always** at least one **fenced code** block. |

Everything below explains *how* to write those three parts.

## Title

- **One line.**
- Names the topic in plain terms.

## TL;DR

- **2–3 short sentences.**
- **Plain language** — see [Plain language](#plain-language) (same bar as section lead-ins: one idea per sentence, no “gumbo”).
- A teammate should get the point in **one read**.

**Same story, two densities** (favor the second):

- *Too dense:* “This diff stretches the scene to 1200 frames, loads two syntax-highlighted TSX snippets (before/after a router change), and plays a timed fade/morph/hold inside the same card as the rest of the shot, while `useDelayRender` blocks the first paint until `highlight` finishes for deterministic frames.”
- *Clearer:* “The clip is longer so the code section has room to breathe. The screen shows old and new Next.js router code, with a smooth morph between them. Remotion waits until syntax highlighting is ready so exports do not flash empty frames.”

## Body sections

Each `##` is **one block** in a blog: title → short intro → code → optional short tail.

1. **`##` title** — Plain English: what this part is *about*. Short and scannable; not a dump of symbols and file names unless the user wants that formality. If you use numbering, **stay consistent** within one answer (e.g. `## 1. The morph sequence` or `## The morph sequence` without numbers—pick one pattern and keep it). Prefer **several small** sections over one long one. **Do not** decorate the top-level `#` title or the TL;DR block with ornamental symbols.
2. **Lead-in** — **One or two** simple sentences. Same [Plain language](#plain-language) rules as the tldr.
3. **At least one fenced code block** — With **line comments** that mark what matters (*what* / *why* at the right lines). Do **not** let comments repeat the lead-in verbatim. You may use `...` or `// ...` when truncation is obvious.
4. **After the code (optional)** — At most **one or two** short plain sentences. If this paragraph is as heavy as the code, shorten it.

### Snippet required for every `##`

- **No prose-only `##` sections.** Every section must end with the reader having seen real code in a fence.
- If an idea is hard to “attach” to code, show the **smallest honest excerpt** anyway—whatever minimal lines the scope actually contains.
- If two small ideas are each too thin for a fence **alone**, **merge** them into one `##` and use **one** snippet (with comments for two sub-parts) so you still have code on screen.

**Cover the scope** with as many `##` blocks as needed. Skip empty blocks. When you merge small points, the merged `##` must still have **at least** one snippet.

## Plain language

Applies to the **tldr**, **lead-ins**, and **post-code** lines.

- **One main idea per sentence.** More sentences beat more commas in one sentence.
- **Short, common words** where you can. Use jargon only when the code or topic forces it; introduce it **once**.
- **Simple story first**, detail second: what this is for → what it does in broad terms → only then the sharp edge (API names, frame timing, etc.).
- **No “explanation gumbo”** — avoid one sentence that chains many tools, paths, and behaviors with dashes and nested parentheses.
- **Clarity over cleverness**; **simple over comprehensive** in prose. Be precise in code; prose should be easy to read aloud.
- **Scannable:** headings and snippets carry most of the load; keep surrounding prose short.

## Code snippets (how to pick and annotate)

- Keep snippets **short**; include only the lines needed to follow the point.
- Comments in the fence should **direct attention** (what to notice next), not restate a whole paragraph.
- In the comment, make clear **what the code does** in context and **why this bit matters** for the current section.

## Scope

- Explain what the user scoped (file, range, diff, question).
- If they gave no scope, default to the **unstaged diff** when you can infer it from context.

## Guardrails

- **Do not invent intent** that is not supported by the code or the user’s prompt.
- **Tone** — like a good technical post: direct and clear, not a tutorial essay and not a disconnected tweet thread.
