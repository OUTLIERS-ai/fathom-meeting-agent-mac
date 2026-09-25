# Operating rules — Claude reads this, you do not

> **For future Claude:** this is a single-purpose repo containing the Fathom meeting agent and the
> Scribe. Its whole job is getting spoken material into written, linked, searchable notes. If this
> folder has been dropped on top of a larger vault that has its own `_CLAUDE.md`, that one wins —
> follow the house style already in the folder and ignore the conventions below.

## How every note is written

- **Frontmatter on every file:** `date: YYYY-MM-DD`, `type:`, kebab-case `tags:`, `ai-first: true`
- **Types used here:** `meeting` · `person`
- **A "for future Claude" preamble** — 2 or 3 plain sentences at the top, so anyone opening the
  note alone can judge its relevance in 10 seconds
- **Wikilink every person, company and project** with `[[double brackets]]`, even where the file
  does not exist yet. The links are what make a year of calls navigable
- **Plain Markdown only.** No HTML, no clever formatting

## File names

- Meetings: `Meetings/YYYY-MM-DD — Who.md` — e.g. `Meetings/2026-09-18 — Kim Bradley.md`
- Several people on one call: the clearest short label, not a list of 6 names
- People: `People/Full Name.md`

Both agents in this repo use the same 2 patterns. If you change one, change the other.

## Hard rules

1. **Never overwrite an existing meeting record.** Append. A re-run must never cost someone a note
2. **Never invent to fill a gap.** An unclear transcript gets said out loud and quoted as-is
3. **Describe, never interpret.** Facts, not a read on how it went
4. **Quote anything commercial word for word** — prices, dates, terms, commitments
5. **File and link only.** Never reply, never send, never act on a commitment found in a call
6. **One failure never stops the run.** Say which recording failed and why, carry on with the rest

## Folders

| Folder | What goes in it |
|---|---|
| `Meetings/` | One file per call — the plain account, then the full transcript |
| `People/` | One file per person, with their meeting history |

Create either if it is missing. Nothing else in this repo is written to.
