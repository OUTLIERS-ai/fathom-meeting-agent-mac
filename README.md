**This is the Mac version.** On Windows, use [fathom-meeting-agent](https://github.com/OUTLIERS-ai/fathom-meeting-agent).

# The Fathom meeting agent

It logs into Fathom, finds every call you have not processed yet, pulls the transcript in, and
writes a clean record of what happened — decisions made, what was promised and by when, every
person named and linked. You do nothing.

A call is forgotten in a fortnight. A filed call is searchable for years.

---

## Before you start — 3 honest gates

**1. You need Claude Code, and a Claude Pro or Max plan.** This is an agent Claude runs, not a
program you double-click. Claude Code is at claude.ai/code. There is no free path to this one.

**2. You need Fathom.** The agent is built around one service on purpose, because the login page
and the page layout are different everywhere. On Otter, Granola, tl;dv or Zoom's own recordings,
the Fathom half will not work — but `the-scribe`, included here, does the same filing job from a
transcript you export by hand. Section 4 below.

**3. It writes into a folder of notes.** If you already keep notes in Markdown — Obsidian, or
just a folder of text files — point it at that. If you do not, this repo is a bare one that works
on its own, and section 5 covers building a fuller one.

---

## 1 · Install it

**Step 1 — download this folder.**

```
git clone https://github.com/OUTLIERS-ai/fathom-meeting-agent-mac.git
```

No git? Download the zip from the same address and unzip it.

**Step 2 — install the browser.** The agent reads Fathom the way you do, through a real browser,
because Fathom has no free way in. Go into the folder you downloaded in Step 1 (it is called
`fathom-meeting-agent-mac-main` if you used the zip), make a private Python folder called `.venv`
in it, and install the browser into that folder:

```
cd fathom-meeting-agent-mac
python3 -m venv .venv
source .venv/bin/activate && python -m pip install playwright
source .venv/bin/activate && python -m playwright install chromium
```

About 200MB, about 5 minutes. Playwright is free and made by Microsoft. The agent knows to look
for it in `.venv`.

**Step 3 — log into Fathom yourself, by hand. Once.** This is the step everyone misses.

In the same Terminal window, still in that folder, open the browser Playwright just installed, at
Fathom's address:

```
source .venv/bin/activate && python -m playwright open --user-data-dir=.browser-profile https://fathom.video
```

Log in as you normally would. Take as long as you need — nothing is counting down, and nothing
will give up on you while you go and find your password. Close the browser when you are in.
The login is kept in the `.browser-profile` folder inside the download, and the agent opens the
browser on that folder from then on.

**Your agent never sees your password.** It never types one, never stores one, and never asks for
one. If anything ever asks you to give a password to an agent, stop — something is wrong.

**Step 4 — open Claude Code inside this folder** and say:

> check Fathom

That is the whole ritual. Afterwards, any of these work: *any new calls?* · *process my meetings*
· *triage my recordings*.

---

## 2 · What you get back

One file per call in `Meetings/`, named by date and who was on it. Each one opens with a plain
account of the call before the full transcript:

- **What this meeting was** — 1 line
- **What happened** — the facts, in order
- **Decisions made** — only what was actually decided. If nothing was, it says so
- **What was promised, by whom, and by when** — the most valuable section on the page
- **People mentioned** — every name, linked
- **Anything unresolved** — the questions left hanging

Everyone on the call gets a note in `People/` with the meeting added to their history. Over a year
that becomes what you actually wanted: open a person, see every call you have ever had with
them, and what each of you said you would do.

---

## 3 · What it will not do

Worth stating, because the restraint is the point.

**It describes, it does not interpret.** It writes what happened, not what it means. No read on
how the call went, no guess at whether the deal closes, no advice. You read the facts in 6 months
and form your own view.

**It never invents to fill a gap.** Transcripts are frequently wrong — speakers mislabelled, words
mangled, whole passages garbled. Where the transcript is unclear it says so and quotes the mess.
It will not smooth a broken passage into a clean sentence nobody said, because that is exactly how
a promise nobody made ends up in someone's permanent record.

**Anything commercial goes in word for word.** Prices, dates, terms and anything resembling an
agreement are quoted exactly, never paraphrased.

**It files and links. That is all.** It never replies to anyone, never sends anything, and never
acts on a commitment it found.

---

## 4 · Not on Fathom

`the-scribe` is included and does the same filing job from text. Export the transcript from
wherever you record, open Claude Code in this folder, and paste it in, or say *write up my call
with [name]*. Same record, same links, one manual step.

The Fathom half of this repo is the only part tied to one service. If you record somewhere else
and want that step automatic too, the job is the same shape pointed at a different login.

---

## 5 · No notes system yet

This repo works on its own — `Meetings/` and `People/` are here and the agent fills them.

Why it is worth having one at all, in plain terms: every call, client, decision and promise sits
in one folder of plain text files on your own computer, which Claude can read and reason over. It
remembers between conversations. Nothing lives only in your head or your inbox. You own it, with
no subscription, no platform, and no export problem later.

Build your own and the addresses in the guide will get you started. Or take the one Ashley runs
his own business out of, already built, with this agent and the rest of them already in it and
already pointed at the right folders. That one goes to people in the Outliers Guild, who also get
shown how it is run across a working week, which is the half that never survives being written
down.

---

## 6 · Where to stop

Practical limits, not moral ones. `BROWSER.md` has the longer version.

**Read, do not act.** Have it collect and file. Do not extend it to click anything that sends,
posts, buys or messages for you. The moment automation acts outwardly, a mistake is public and you
cannot take it back.

**Your account, your consequences.** Automating a service may be against the terms you agreed to,
and enforcement is usually the account rather than a warning. That is your judgement to make, and
the risk is yours.

**Never point it at somebody else's account.** Obvious, and worth writing down.

---

*Ashley Dean Smith · Outliers*

This repo is made automatically from fathom-meeting-agent@ee226f8. To report a problem or suggest a change, use that repo, not this one.
