# Career Materials Builder

A single-page app version of the *Career Materials Builder* prompt. It attaches
your career documents, runs the phase-by-phase interview, and calls Claude
directly from your browser — no server required.

It's one file: `index.html`. Open it locally, or host it for free on GitHub Pages.

## How it works

- The whole prompt (ground rules, phases 0–7, calibration examples) is baked in
  as the system prompt. You can see and edit it in the app under
  **Setup → Advanced → edit the underlying prompt**.
- You paste in your own Anthropic API key. It's kept in memory in your browser
  tab only, sent directly to `api.anthropic.com`, and never touches any other
  server — including no server of mine, since there isn't one.
- File uploads (PDF, DOCX, TXT/MD, images) are read client-side and sent as
  attachments on your next message.
- Web search is on by default so Phase 6 (pay/market data) and Phase 7
  (current resume standards) can pull real, current information.
- A small "spine" on the left guesses which phase you're in from the
  assistant's own checkpoints — it's a compass, not a tracker to rely on.
- **Export chat** downloads the whole conversation as Markdown, so you can
  re-upload it next session (the prompt's "Continuity" step).

## Get an API key

1. Go to [console.anthropic.com](https://console.anthropic.com/settings/keys)
   and sign in (or create an account).
2. Create a new API key.
3. Add a small amount of credit under **Billing** — this app is pay-as-you-go
   per Anthropic's standard API pricing, separate from any Claude.ai
   subscription. A full run through all phases with a few documents will
   likely cost low single-digit dollars; Phase 4 (master inventory) and
   Phase 6 (market research) are the priciest steps since they read/write the
   most.

## Run it locally

Just open `index.html` in a browser — double-click it, or:

```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html        # Windows
```

No build step, no `npm install`, no dependencies to install locally (Mammoth,
the DOCX reader, loads from a CDN).

## Put it on GitHub and host it for free

**No coding or command line needed — just GitHub's website:**

1. Create a free account at [github.com](https://github.com), if you don't
   have one.
2. Click the **+** in the top-right corner → **New repository**. Name it
   `career-materials-builder`, set it to **Public**, and click
   **Create repository**.
3. On the new, empty repo page, click **"uploading an existing file."** Drag
   in `index.html`, `README.md`, and `LICENSE`, then click **Commit changes**.
4. Go to **Settings → Pages** (left sidebar). Under "Source," choose
   **Deploy from a branch** → Branch: `main`, folder: `/ (root)` → **Save**.
   Wait a minute, refresh, and GitHub gives you a live URL like
   `https://<your-username>.github.io/career-materials-builder/`.
5. Open that URL, paste in your API key, and you're running.

**If you're comfortable with git instead**, the command-line equivalent of
steps 2–3:

```bash
git init
git add index.html README.md LICENSE
git commit -m "Career Materials Builder"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## A real security note (please read)

This app calls the Anthropic API **directly from the browser**, using a
header (`anthropic-dangerous-direct-browser-access`) that Anthropic added
specifically to support "bring your own key" tools like this one. That's a
legitimate, documented pattern — but it comes with a real tradeoff:

- **Anyone who has your key can use it.** Because the key lives in the page
  you're viewing, it's visible in your browser's network tab while you use
  the app. That's fine when only you are using it with your own key.
- **Don't publish your key**, hardcode it into `index.html`, or commit it to
  the repo. Always paste it in at runtime.
- **If you ever want other people to use this app**, don't have them paste in
  your key. At that point you'd want a small backend (e.g. a Node/Express
  server or a serverless function) that holds the key server-side and the
  browser talks to instead of Anthropic directly. Happy to build that version
  if this ever grows beyond personal use.

## Customizing

- **Change the process itself**: edit the text in **Setup → Advanced → edit
  the underlying prompt** right in the app (e.g. drop the market-pay research
  step, or dial bluntness up or down). Changes only apply for that browser
  session — edit `SYSTEM_PROMPT_DEFAULT` near the top of the `<script>` in
  `index.html` to make a change permanent.
- **Switch models**: the dropdown offers Claude Sonnet 5 (fast, cheap, the
  default) and Claude Opus 4.8 (slower and more expensive, occasionally worth
  it for the densest phases like the master inventory or gap check).
- **Design**: colors and type live in the `:root` CSS variables at the top of
  `index.html` if you want to reskin it.

## Continuing the LinkedIn Profile Builder (Part 2)

The original toolkit pairs this with a separate LinkedIn Profile Builder
prompt that reuses the same master inventory — it's included here as
`linkedin-profile-builder-prompt.md`. Same usage: copy it, paste it into
Claude, ChatGPT, or any AI chat tool with file upload and web search, and
attach your master inventory (and resume, if you have one) instead of
starting from scratch. It isn't built into `index.html` yet — if you want
that (a second tab in the same app), just ask.
