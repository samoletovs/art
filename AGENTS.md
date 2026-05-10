# AGENTS.md — `art`

> Copilot / Claude / agents working in this repo: read this first.

## What this is

A small gallery of static HTML pages, hosted on GitHub Pages at `art.naurolabs.com`. Sister project to [`playground`](https://github.com/samoletovs/playground) (kids' HTML games). Both are deliberately **off the NauroLabs platform path** — no Azure SWA, no Functions, no auth, no bundler.

## Conventions

- **One HTML file per piece.** Self-contained: inline `<style>` and inline `<script>`. No `node_modules`, no build step.
- **File names:** `kebab-case.html` (e.g. `rooftop-rain.html`).
- **Asset folders** named after the piece (e.g. `rooftop-rain/cover.jpg`) — keep colocated.
- **External dependencies:** prefer system fonts and zero-dep CSS. If a piece needs a CDN library (e.g. `tone.js`, `p5.js`), pin the version in the `<script src>`.
- **Index page (`index.html`):** the gallery card grid. Add a new `<a class="piece">` card when you add a new file.

## Style direction

The gallery aesthetic is **gallery-like and warm** — cream paper background (`#fbf7f0`), charcoal ink, italic serif headings, generous whitespace, NauroLabs red (`#9E3039`) as a single restrained accent. This is intentionally the opposite of `playground`'s dark "arcade" palette. Keep individual pieces free to explore other aesthetics — but the **landing page** stays consistent so the gallery itself feels curated.

## What NOT to do

- **Don't add a build step.** If a piece is so complex it needs Webpack, it doesn't belong here — give it its own NauroLabs project.
- **Don't add server-side anything.** No serverless functions, no databases. If a piece needs persistence, use `localStorage` (it's a sketch, not an app).
- **Don't add tracking / analytics** without explicit user consent (GDPR + this is a personal gallery, not a product).
- **Don't change the domain or `CNAME`** without checking with Sam first — DNS lives in the central NauroLabs DNS config.
- **Don't push commits as someone other than `samoletovs`** — auto-merge workflow allowlist (mirrored from `playground`) only accepts PRs from Sam, Claude bot, or Copilot bot.

## Adding a piece (the canonical flow)

1. Save the new HTML file in the repo root.
2. Edit `index.html`:
   - On first piece: remove the `<div class="empty">…</div>` empty-state block.
   - Copy the commented example `<a class="piece">…</a>` and fill in `href`, `<div class="num">`, `<div class="title">`, `<div class="meta">`.
3. Test locally by opening `index.html` (or `python -m http.server 8000`).
4. Commit, push to `main`. GitHub Pages auto-publishes.

## When in doubt

This project's north star: **a non-developer can read `README.md`, copy an HTML file someone made for them, and have it live in 5 minutes.** If your change makes that harder, it's the wrong change.
