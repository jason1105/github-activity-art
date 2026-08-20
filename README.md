# GitHub Activity Art

Generative visual art created automatically from your GitHub contribution data, published as a GitHub Pages site.

## What it does

Every month on the 1st, a GitHub Actions workflow:

1. Fetches your contribution calendar via the GitHub GraphQL API
2. Generates three unique SVG artworks from the data
3. Computes stats (total commits, longest streak, busiest day)
4. Commits everything back to the repo
5. Your GitHub Pages site updates automatically

## Artworks

| Artwork | Description |
|---|---|
| **Skyline** | Weekly commit totals become a city skyline — taller spires mean more commits. Gradient sky, crescent moon, reflected in water below. |
| **Soundwave** | Daily contributions smoothed into a symmetric audio waveform. The spectrum colours progress from cyan through violet to amber across the year. |
| **Constellation** | Each contribution day is a star. Busier days glow brighter. Nearby bright stars are connected by lines, forming constellation patterns across deep space. |

## Setup

1. Fork or use this repository as a template.
2. Enable **GitHub Pages** in Settings → Pages → Source: `main` branch, `/ (root)`.
3. The workflow uses the built-in `GITHUB_TOKEN` — no extra secrets needed.
4. Trigger the first run manually: Actions → Generate GitHub Activity Art → Run workflow.

After that it runs automatically on the 1st of every month.

## Local preview

Open `index.html` directly in a browser. The SVGs are pre-generated samples; run the workflow (or the Python script locally) to generate art from your own data.

## Tech stack

- **GitHub Actions** — scheduling and automation
- **Python** — GraphQL data fetch + pure-SVG art generation (no external image libraries)
- **SVG** — `<path>`, `<rect>`, `<circle>`, gradients, filters
- **GitHub Pages** — zero-config static hosting

## License

MIT
