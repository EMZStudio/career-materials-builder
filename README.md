# Career Materials Builder

A two-part toolkit — **1) a resume/source-of-truth builder** and
**2) a LinkedIn profile builder** — built around one rule: it won't state
anything it can't verify. No invented metrics, no inflated titles. Just an
honest, step-by-step interview that turns your real career history into
material you can actually trust.

**New to AI tools?** This works with "AI chat" websites — a page you type
into and get a written answer back, the same way you'd text a very
knowledgeable person. [Claude](https://claude.ai) (made by Anthropic) and
[ChatGPT](https://chatgpt.com) are the two best-known ones, and both are free
to try. You don't need to install anything to use the prompts below.

## The two prompts

| | What it builds | File |
|---|---|---|
| **Part 1** | Your resume + a reusable "source of truth" document | [`career-materials-builder-prompt.md`](./career-materials-builder-prompt.md) |
| **Part 2** | Your LinkedIn profile, using the same source of truth | [`linkedin-profile-builder-prompt.md`](./linkedin-profile-builder-prompt.md) |

Run Part 1 first, then Part 2 — or use either on its own.

## Getting started (the setup below takes 2 minutes — the process itself doesn't)

1. Click one of the two files above.
2. Copy everything under the line that says "paste everything below this."
3. Paste it into Claude, ChatGPT, or any AI chat tool.
4. Attach whatever career material you have — old resumes, LinkedIn export,
   performance reviews, messy notes. Nothing needs to be sorted first.
5. Answer honestly. It interviews you step by step from there.

That last step is the real work, and it's meant to take real time — one
sitting or several, however long an honest interview about your career
actually takes. Anything that promises to do this in 2 minutes is skipping
the part that makes it worth doing.

One more honest thing: this only works as well as you're willing to be with
it. A vague or padded answer gets you a vague, padded resume back. A
specific, honest one — including the parts you'd rather not lead with — gets
you something you can actually defend in an interview.

## The live app (optional, Claude-powered)

👉 **[Open the app](#)** *(add your GitHub Pages link here once it's live)*

Same Part 1 process, but as a real app: reads PDF/DOCX files directly, pulls
live market data, and tracks which step you're on. Runs entirely in your
browser. Needs a free [Anthropic API key](https://console.anthropic.com/settings/keys)
to run — this is just a personal code that lets the app talk to Claude on
your behalf, similar to a password. You paste in your own; it's never seen
by anyone but Anthropic.

## What's in this repo

- `index.html` — the live app
- `career-materials-builder-prompt.md` — Part 1, plain text
- `linkedin-profile-builder-prompt.md` — Part 2, plain text
- `LICENSE` — MIT, free to use, copy, and adapt

## Want your own copy? (not needed just to use the link above)

This is only for someone who wants to fork this repo and host their own
version — if you just want to use the app, click the link above instead.

1. In your fork, go to **Settings → Pages**.
2. Source: **Deploy from a branch** → Branch: `main`, folder: `/ (root)` → **Save**.
3. Wait a minute, refresh — your link is
   `https://<your-username>.github.io/career-materials-builder/`.

## Privacy note

The app talks to Anthropic directly from your browser using your own key —
nothing passes through a server of mine, because there isn't one. Don't
share a link with your key already filled in; everyone brings their own.

## Why this exists

Every AI resume tool I tried had the same problem: it wanted to impress, not
verify. It'll happily round up a title or invent a metric if you let it. So
I built one with the opposite rule — say only what's true, flag what isn't,
and let the honest version turn out stronger anyway. The boring, careful
process turns out to produce a resume you can actually defend across the
table from someone asking follow-up questions.

## About

Made by EMZStudio. MIT licensed — adapt it, rename it, make it yours.
