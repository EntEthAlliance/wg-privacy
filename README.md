# EEA Privacy Working Group Report

**State of Privacy on Ethereum for Enterprise** — Version 1 · April 2026

Cross-institutional report mapping enterprise privacy requirements to Ethereum privacy solutions, published by the Enterprise Ethereum Alliance Privacy Working Group.

## View

- **Production:** https://entethalliance.github.io/wg-privacy/privacy-report.html
- **Local:** open `privacy-report.html` in any browser — no build step, no dependencies.
- **Branch previews:** every branch is auto-deployed to `https://entethalliance.github.io/wg-privacy/staging/<branch-name>/privacy-report.html` (see [Deployment](#deployment) below).

## Contents

| File | Description |
|------|-------------|
| `privacy-report.html` | Full interactive report (single-file) |
| `index.html` | Redirect → privacy-report.html |
| `PRIVACY_REPORT_SOURCE.pdf` | Source PDF |
| `PRIVACY_REPORT_CONTENT.md` | Extracted report content (Markdown) |
| `logos/` | Partner logo assets |
| `*.png / *.jpg / *.svg` | Hero images, diagrams, and illustrations |

## Features

- Dark/light mode toggle
- Sticky sidebar navigation
- Expandable solution cards
- Filterable coverage matrix
- Print stylesheet
- Scroll animations

## Deployment

GitHub Pages is published automatically by [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) on every push.

| Trigger | Action | Published URL |
|---------|--------|---------------|
| Push to `main` | Deploy to production root | `https://entethalliance.github.io/wg-privacy/privacy-report.html` |
| Push to any other branch | Deploy to staging path | `https://entethalliance.github.io/wg-privacy/staging/<branch-name>/privacy-report.html` |

**How it works**
- Workflow runs on `push` to `**` (all branches) and uses `peaceiris/actions-gh-pages@v4`.
- The branch name decides the target: `main` writes to the gh-pages root; everything else writes to `staging/<branch-name>/`.
- `keep_files: true` preserves prior deploys, so multiple staging previews can coexist without wiping production.
- Source `gh-pages` branch holds the published artifacts; do not edit it directly.

**Editor workflow**
1. Open a feature branch (e.g. `fix/zksync-edits`).
2. Push — within ~1 minute the staging URL above is live for review.
3. Open a PR to `main`. After merge, the same workflow republishes production.

**CI status:** [Actions tab](https://github.com/EntEthAlliance/wg-privacy/actions/workflows/deploy.yml).

## Source

Content synced from [EntEthAlliance/eea-privacy-report](https://github.com/EntEthAlliance/eea-privacy-report).

## Contact

- Working Group: privacy-wg@entethalliance.org
- Press: press@entethalliance.org
