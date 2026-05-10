# art

A small gallery of HTML pages, hosted on `art.naurolabs.com`.

Each piece is a single HTML file — no build step, no framework, no backend. Push to `main` and it's live within a minute.

## How to add a new piece

1. Save the page as a `.html` file in this folder (e.g. `rooftop-rain.html`)
2. Open `index.html` and either:
   - Remove the "No pieces yet" empty-state block once the first piece exists, **or**
   - Copy the example `<a class="piece">` block (it's commented in the file) and edit:
     - `href="rooftop-rain.html"` — the filename you just added
     - `<div class="title">…</div>` — what you want shown on the card
     - `<div class="meta">…</div>` — year + short description
3. Commit and push. GitHub Pages publishes automatically.

```powershell
git add .
git commit -m "add: rooftop rain"
git push
```

## How to view it locally before publishing

Just open `index.html` in any browser — there's no server needed. Or, if a piece links to other files relatively and you want it to behave like the live site, run a tiny static server:

```powershell
# from this folder
python -m http.server 8000
# then open http://localhost:8000
```

## Hosting

- **Repo:** [`samoletovs/art`](https://github.com/samoletovs/art)
- **Live URL:** [`https://art.naurolabs.com`](https://art.naurolabs.com)
- **Hosting:** GitHub Pages, custom domain via the `CNAME` file
- **Cost:** free
- **Auth / accounts:** none — pages are public to anyone with the URL

## Conventions

- One file per piece. No bundlers, no node_modules, no JSX.
- Inline CSS (or `<style>` tags) so each piece is self-contained and travels well.
- File names: `kebab-case.html` (lowercase, dashes between words).
- Keep external dependencies minimal — fonts via `system-ui` / `serif` stack are best.
- If a piece has assets (images, audio), put them in a folder named after the piece, e.g. `rooftop-rain/cover.jpg`.

## Inspired by

The companion repo [`samoletovs/playground`](https://github.com/samoletovs/playground) uses the same pattern for the kids' games at `playground.naurolabs.com`. Both are intentionally "off the platform path" (no Azure, no SWA, no Functions) — for static hand-written pages, GitHub Pages is the simplest thing that could possibly work.

---

built by nauroLabs
