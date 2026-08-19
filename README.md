# Source to Skill

Point the agent at notes you already have. It turns them into a skill it can load later — without stuffing the whole pile into one prompt.

Use it on transcripts, memos, decks, research dumps, interview notes. Use it on work you own.

## How you use it

**1. Put the source in front of the agent**

A file, a folder, or a glob. Example:

```
/source-to-skill ./notes/q3-discovery.md discovery-method
```

**2. What you get back**

A skill folder, usually at `~/.claude/skills/discovery-method/`:

| File | What you do with it |
|---|---|
| `SKILL.md` | The method — models, rules, when *not* to use it |
| `sources/` | One section per file; the agent opens only what it needs |
| `glossary.md` | Terms with pointers back to the source |
| `patterns.md` | Techniques, including when not to use them |
| `cheatsheet.md` | Fast decision tables |
| `GAPS.md` | Questions the source never answered |

If a rule was not in the source, it is not in the skill. Gaps are listed, not filled with a famous framework.

**3. Work with the new skill**

```
/discovery-method
/discovery-method s03
/discovery-method when not to interview
```

The agent reads the index, then one source file — not the entire dump.

**4. Rights**

Personal notes, your decks, meetings you own: go. Do not ask it to publish someone else’s book as a public skill.

**5. Where it lives**

Open this repo in Claude Code, Cursor, or Cowork so `/source-to-skill` is available, then run it on a path in your workspace.
