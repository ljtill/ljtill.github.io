# Copilot Instructions

## Tech Stack

Personal website built with **plain HTML and modern CSS** — no frameworks, no
build tools, no dependencies. Hosted on **GitHub Pages** with automated
deployment via GitHub Actions.

## Architecture

Single-page site. All CSS is inlined via `<style>` in each HTML file — there are
no external stylesheets. Both `index.html` and `404.html` share the same design
language (reset layer, color tokens, font stack, `light-dark()` theming) and must
stay visually consistent when either is changed.

The `index.html` includes JSON-LD structured data (`Person` schema) that must be
kept in sync with the bio content.

## CSS Conventions

Modern features only — no legacy fallbacks, no vendor prefixes:

- **`@layer`** ordering: `reset`, `base`, `layout`, `components`
- **Native CSS nesting** (`& selector`)
- **Logical properties** (`margin-inline`, `padding-block`, `inline-size`) — never
  physical equivalents
- **`light-dark()`** with `color-scheme: light dark` for automatic dark mode
- **`clamp()`** for fluid responsive typography
- **`dvh`** viewport units
- **CSS custom properties** on `:root` for all design tokens (colours, spacing,
  type scale)

## HTML Conventions

- Semantic elements: `<header>`, `<main>`, `<footer>`, `<nav>`
- `<meta name="color-scheme" content="light dark">` on every page
- `fetchpriority` hints on resources
- `aria-label` on icon-only links

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
