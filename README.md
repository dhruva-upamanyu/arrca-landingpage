# arrca website

Marketing + docs site for **arrca** (arrca.ai), built with Astro + Tailwind.
This is a standalone repo; the Astro site is at the repo root. arrca is the
brand for root-cause-analysis tooling; the flagship tool featured here is
[otel-k8s-graph](https://github.com/arrca-ai/otel-k8s-graph).

## Develop

```bash
npm install
npm run dev
```

## Build

```bash
npm run build   # outputs to ./dist
```

## Deploy

Pushing to `main` triggers [`.github/workflows/deploy-site.yml`](.github/workflows/deploy-site.yml),
which builds the site and deploys it to GitHub Pages. The custom domain is set
via [`public/CNAME`](public/CNAME) (arrca.ai).

**One-time setup:**

1. In the GitHub repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
2. Point the `arrca.ai` DNS at GitHub Pages (apex `A`/`AAAA` records, or an
   `ALIAS`/`ANAME` to `<user>.github.io`).

## Structure

```
src/
  layouts/BaseLayout.astro   # head, nav, footer chrome
  components/                # Logo, Nav, Footer, Hero, Section,
                             # CodeBlock, PatternCard, ArchDiagram
  pages/
    index.astro              # landing page
    docs.astro               # install / configure / query docs
  styles/global.css          # Tailwind import + design tokens
public/
  favicon.svg
  CNAME
```
