# Going online — giving your agents a browser

Most of what your agents need is public, and they can read public pages without any setup. This
file is for the other case: **pages you can only see when you are logged in.** Your call
recordings, your account dashboards, a members-only resource you pay for.

## What this gives you

With a browser installed, your agents can open a page *as you*, read what is there, and file it
into the vault. That is how `fathom-meeting-triage` collects your calls without you exporting
anything by hand, and it is how you would collect anything else that sits behind a login.

## Setup, once

From inside this folder, make a private Python folder called `.venv` and install the browser into it:

```
python3 -m venv .venv
source .venv/bin/activate && python -m pip install playwright
source .venv/bin/activate && python -m playwright install chromium
```

Playwright is free, made by Microsoft, and drives a real browser rather than pretending to be
one. Around 200MB, five minutes.

## Then log in yourself, once

Open the browser Playwright installed, from inside this folder, with the address of the service
at the end. For Fathom, that is:

```
source .venv/bin/activate && python -m playwright open --user-data-dir=.browser-profile https://fathom.video
```

Then **log in by hand.** The login is kept in the `.browser-profile` folder, and your agents
open the browser on that folder from then on.

**Your agent never sees your password.** It never types one, never stores one, and never asks for
one. If you are ever prompted to give a password to an agent, something is wrong — stop.

When a session expires, you log in again yourself. An agent that says "I can't get in, the
session has expired" is behaving correctly. One that tries to work around a login is not.

## What to point it at

Good uses, in rough order of value:

| Use | Why it earns its place |
|---|---|
| **Your call recordings** | The highest-value material you own, and the least likely to be written down |
| **A course or membership you pay for** | You already bought it. Getting it into your own vault is how you actually use it |
| **Your own dashboards** | Numbers you check weekly, pulled in rather than screenshotted |
| **Research behind a paywall you subscribe to** | Same principle: you have access, you are just moving it somewhere you can search |

## Where to stop

Some plain limits, and they are practical rather than moral.

**Read, do not act.** Have it collect and file. Do not have it click anything that sends, posts, buys,
apply or message on your behalf. The moment automation acts outwardly, a mistake is public and
you cannot take it back.

**Your account, your consequences.** Automating a platform may be against the terms you agreed
to, and the enforcement is usually the account rather than a warning. That is a judgement for you
to make service by service, and the risk is yours. Nothing in this vault decides it for you.

**One job at a time, at human pace.** Anything that hammers a site quickly looks like exactly
what it is. Slow is fine — these jobs run while you are doing something else.

**Never point it at somebody else's account.** Obvious, and worth writing down.

## If you do not want any of this

You lose nothing important. Every agent in this vault works on material you give it directly:
export the transcript yourself, save the PDF, paste the text. The browser is a convenience that
removes a manual step, not a requirement. Plenty of people run the whole system without it.
