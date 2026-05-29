# imogging.com — automated-edit guardrails

This repository **is** the live website https://imogging.com. It is served by
GitHub Pages from the `master` branch. Any push to `master` publishes to the live
domain within about a minute. There is no staging environment — edits go straight
to production. Treat every change as live.

You are usually invoked here by a GitHub issue that mentions `@claude` with a
plain-English change request (often filed automatically by the Base44 agent).
Make the requested change to the site and nothing else.

## Hard rules — never violate

1. **Edit `index.html` only.** The entire site is one file. Do not add build
   tools, frameworks, bundlers, package.json, or split the page into multiple
   files. Keep it a single static HTML file that deploys instantly.
2. **Never touch `CNAME`.** It must always contain exactly `imogging.com`.
   Deleting or changing it breaks the custom domain.
3. **Never delete `.github/workflows/claude.yml`** or this `CLAUDE.md`.
4. Make the smallest change that satisfies the request. Do not "improve" or
   redesign unrelated parts of the page.

## Preserve these at all times

- **Matrix-green "telemetry" aesthetic** — the dark background, green text, and
  monospace/terminal feel. Do not introduce light themes, stock-photo vibes, or
  generic corporate styling.
- **Lowercase brand voice** — short lines, specific, calm, no hype. No corporate
  tone. No emojis. (See `04_voice_and_copy.md` in the owner's project notes for
  the full voice; when in doubt, match the copy already on the page.)
- **The primary CTA** — the Calendly link
  `https://calendly.com/imogging/founding-spot` ("book your 15-minute call").
  Keep it working and prominent unless the request is explicitly to change it.
- **The medical disclaimer** in the footer:
  "iMogging is coaching, not medical care. nothing here is medical advice.
  consult your physician before changing your training, nutrition, supplement,
  or any protocol." Keep it present and legible.
- **The page title** `iMogging — biological operating system` unless asked to
  change it.

## How your work gets published

After you edit `index.html` and commit to your working branch, the `claude`
workflow fast-forwards `master` to your branch and GitHub Pages publishes it.
You do **not** need to merge anything yourself — just make a clean commit on the
branch the action gives you. The workflow will comment the commit SHA back on the
issue and confirm the site is live.

If a request would violate any hard rule above (e.g. "delete the disclaimer",
"rebuild this in React", "remove the Calendly link"), do not do it — instead
comment on the issue explaining what you can do within these constraints.
