---
name: source-to-skill
description: >
  Convert the user's own notes, transcripts, decks, or research folders into an
  agent skill (SKILL.md + on-demand source files). Use when asked to turn a
  document, meeting, or folder into a skill. Do not distill commercial books
  for public GitHub. Do not invent frameworks that are not in the source.
---

# Source to Skill

## Rights check (first)

Ask: do you have the right to turn this into a skill? Personal notes, your decks, meeting transcripts you own → proceed. A scanned commercial book for a public repo → refuse and suggest private local use only, or quote fair-use fragments with citation.

## Pipeline

1. **Read** the path (file, folder, glob). If empty, stop.
2. **Split** into source units (sections, meetings, slides). Cap each `sources/sNN-*.md` around 800–1,200 tokens.
3. **Extract only what is in the text:**
   - Named frameworks and decision rules
   - Anti-patterns the author already stated
   - Terms for the glossary with a back-reference
4. **Write** the folder:

```
~/.claude/skills/<slug>/
  SKILL.md
  sources/
  glossary.md
  patterns.md
  cheatsheet.md
  GAPS.md
```

5. **GAPS.md** lists anything the user asked for that the source does not support. Use `[NEED: …]`. Never fill gaps with a famous framework from training data.

## SKILL.md rules

- Front-load 3–7 mental models from the source, with a short quote or paraphrase + source id (`s03`).
- Chapter/source index so the agent can load one file: `/slug s03` or `/slug <topic>`.
- **When not to use this skill** — required section. If the source never says it, write “Unknown — not in source” rather than inventing.

## Patterns.md format

For each technique:

- When to use
- How (steps in the source)
- When not (if absent: `[NEED]`)

## Fail closed

| Fail | Why |
|---|---|
| Adding Porter / Jobs-to-be-done / RICE because “PMs use those” | Not in source |
| One giant SKILL.md over 6k tokens | Defeats on-demand loading |
| No GAPS.md | Hides missing evidence |

## After convert

Tell the user the slug, how to invoke it, and the count of `[NEED]` items. Offer to run Voice Gate on `SKILL.md` if that skill is installed.
