# ljtill.github.io

Personal website — plain HTML and modern CSS, deployed to GitHub Pages.

## Development

Edit `site/index.html` directly. Public files live in `site/`, with shared
assets in `site/assets/`. No build step, no dependencies.

## Deployment

Push to `main` → GitHub Actions deploys `site/` automatically via
`.github/workflows/deploy.yml`.