# Copilot Instructions

## Tech Stack

Personal website built with **plain HTML and modern CSS** — no frameworks, no
build tools, no dependencies. Hosted on **GitHub Pages** with automated
deployment via GitHub Actions.

## Architecture

- **`index.html`** — Single-page site with all CSS inlined via `<style>`.
  Contains the bio content, header, footer with social links, and JSON-LD
  structured data.
- **`404.html`** — Custom error page served by GitHub Pages for missing routes.
- **`favicon.ico`** — Site favicon.
- **`.nojekyll`** — Disables Jekyll processing on GitHub Pages.
- **`.github/workflows/deploy.yml`** — GitHub Actions workflow that deploys the
  repo root to GitHub Pages on push to `main` or manual `workflow_dispatch`.

## CSS Conventions

All styling is inlined in each HTML file. The CSS uses **modern features only**
(no legacy fallbacks):

- **`@layer`** for style organization (`reset`, `base`, `layout`, `components`)
- **Native CSS nesting** (no preprocessor)
- **Logical properties** (`margin-inline`, `padding-block`, `inline-size`, etc.)
- **`light-dark()`** with `color-scheme: light dark` for automatic dark mode
- **`clamp()`** for fluid responsive typography
- **`dvh`** viewport units
- **CSS custom properties** for theming

## HTML Conventions

- Semantic elements throughout: `<header>`, `<main>`, `<footer>`, `<nav>`
- `<meta name="color-scheme" content="light dark">` for native OS color scheme
- `fetchpriority` hints on resources
- `aria-label` on icon-only links
- JSON-LD structured data (`Person` schema)

## Deployment

Deployment is fully automated. Pushing to `main` triggers the GitHub Actions
workflow which uploads the repo root and deploys to GitHub Pages. No build step
is required.

## Git

- Push directly to `main` (single-developer project).
- Commit messages follow
  [Conventional Commits](https://www.conventionalcommits.org/) with a structured
  body:

```
type: short summary

Why:
- Reason for the change

What:
- Concrete change 1
- Concrete change 2
```

- Common types: `feat`, `fix`, `ci`, `docs`, `chore`.
- The subject line must be lowercase, imperative, and under 72 characters.
- The `Why` section explains motivation. The `What` section lists the changes
  made.
