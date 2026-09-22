# Terraform Sandwich

Slide deck for the **Terraform Sandwich** talk — a multi-stage Terraform pattern for CI/CD when resources depend on a running application.

Built with Vite + [reveal.js](https://revealjs.com/).

**Live deck:** [https://jrabbott.github.io/talk-terraform-sandwich/](https://jrabbott.github.io/talk-terraform-sandwich/)

## Requirements & run locally

- **Node.js 22+** (see `.nvmrc`)

```bash
npm ci
npm run dev
```

Open the URL Vite prints (usually `http://localhost:5173/talk-terraform-sandwich/`).

## Present

1. Start with `npm run dev` (or open the live Pages URL).
2. Click the slides, then use arrow keys / space to navigate.
3. Press `F` for fullscreen, `S` for speaker notes, `Esc` for overview.
4. Slide numbers and URL hashes are enabled so you can deep-link to a slide.

## Deck outline

1. Title — Terraform Sandwich
2. Terraform primer (what / how / why)
3. Ordering tension (“when love and hate collide”)
4. Sandwich definition — run Terraform more than once around a release
5. Azure Event Grid example — problem, split apply, pipeline
6. When to use it
7. Thanks

## License

MIT — see [LICENSE](LICENSE).
