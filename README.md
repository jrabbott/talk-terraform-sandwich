# Terraform Sandwich

Slide deck for the **Terraform Sandwich** talk — a multi-stage Terraform pattern for CI/CD when resources depend on a running application.

Built with Vite + [reveal.js](https://revealjs.com/).

**Live deck (after Pages is enabled):** [https://jrabbott.github.io/talk-terraform-sandwich/](https://jrabbott.github.io/talk-terraform-sandwich/)

## Requirements

- **Node.js 22+** (see `.nvmrc`). Prefer `npm ci` so the lockfile is respected.

## Run locally

```bash
npm ci
npm run dev
```

Open the URL Vite prints (usually `http://localhost:5173/talk-terraform-sandwich/`).

To check the production build:

```bash
npm run build
npm run preview
```

Dependency audit (also runs in CI):

```bash
npm run audit
```

## Present

1. Start with `npm run dev` (or open the live Pages URL).
2. Click the slides, then use arrow keys / space to navigate.
3. Press `F` for fullscreen, `S` for speaker notes, `Esc` for overview.
4. Slide numbers and URL hashes are enabled so you can deep-link to a slide.
5. Fragments advance with the same keys.

Speaker notes in `<aside class="notes">` are author-controlled HTML rendered by reveal.js in the speaker view. Treat them as trusted content only—do not paste untrusted markup into notes.

## Talk outline

1. Title — Terraform Sandwich
2. Terraform primer (what / how / why)
3. Ordering tension (“when love and hate collide”)
4. Sandwich definition — run Terraform more than once around a release
5. Azure Event Grid example — problem, split apply, pipeline
6. When to use it
7. Thanks

## Theming

Aligned with the [slides-as-code](https://github.com/jrabbott/slides-as-code) template: Atkinson Hyperlegible, one solid paper surface, quiet motion, calm 1–2 column layouts.

Brand tokens live at the top of `src/style.css`:

```css
:root {
  --ink: #121820;
  --muted: #2c3544;
  --surface: #f2eee6;
  --accent: #0c6b52;
  --accent-soft: #c5e4d8;
  --on-accent: #f2eee6;
  --closing: #121820;
}
```

Diagrams are original SVGs under `public/assets/` using the same palette.

## CI and publish

Shared quality gate lives in `.github/actions/build` (`npm ci`, audit, Vite build with repo-derived `BASE_PATH`, `dist/` smoke check).

- **CI** (`.github/workflows/ci.yml`) runs that action on pull requests.
- **CD** (`.github/workflows/cd.yml`) runs the same action on pushes to `main` (or `workflow_dispatch`), uploads `dist/`, and deploys to GitHub Pages.

Dependabot watches npm and GitHub Actions weekly.

Override the Pages base locally when needed:

```bash
BASE_PATH=/talk-terraform-sandwich/ npm run build
```
