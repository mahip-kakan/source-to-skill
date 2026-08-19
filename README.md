# Source to Skill

Turn **your** work product into an agent skill: transcripts, memos, decks, research dumps, interview notes.

Not a book piracy tool. Do not publish distilled commercial books. The same *shape* as a high-quality book→skill converter (index + on-demand chapters) — the **input is work you own or have rights to**.

```
/source-to-skill path/to/notes.md my-method
```

You get a skill folder the agent can load without stuffing the whole corpus into one prompt.

## What it writes

| File | Job |
|---|---|
| `SKILL.md` | Mental models, decision rules, anti-patterns, chapter index (~4k tokens cap) |
| `sources/s01-*.md` | One source (or section) per file, loaded on demand |
| `glossary.md` | Terms with back-references |
| `patterns.md` | Techniques: when to use, how, when not |
| `cheatsheet.md` | Decision tables |
| `GAPS.md` | `[NEED: …]` — claims that were not in the source |

If a rule is not in the source, it does not go in the skill. Hallucinated frameworks are a fail.

## Install

```bash
git clone https://github.com/mahip-kakan/source-to-skill.git
cp -R source-to-skill/skills/source-to-skill ~/.claude/skills/source-to-skill
```

Then point it at a file, folder, or glob you have the right to use.

## Why not “book to skill”

[virgiliojr94/book-to-skill](https://github.com/virgiliojr94/book-to-skill) (~23k stars) proved the architecture: structure, not a summary; chapters on demand. Publishing someone else’s book as a public skill is a copyright problem. This repo is for **methods you produced** — consulting notes, product briefs, red-teams, research.

## Inspired by

- On-demand skill layout: book-to-skill (mechanism only; files here are original)
- Sources → notes as a research object: [lfnovo/open-notebook](https://github.com/lfnovo/open-notebook) (~37k) — we export a **skill**, not a chat UI

See `CREDITS.md`.

## License

MIT. Built by Mahip Kakan.
