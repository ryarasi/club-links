# The Debate Club — thedebateclub.info

Source for [thedebateclub.info](https://thedebateclub.info), the home of The Debate Club community.

A community for civil public discourse. Live online voice debates every Saturday at 11am IST.

## Stack

- **[Astro 5](https://astro.build)** — static site generator, single-page anchored layout (Home / About / Blog / Contact) plus a per-post blog route at `/blog/<slug>/`.
- **[Tailwind CSS 4](https://tailwindcss.com)** — utility styling, design tokens in `src/styles/global.css`.
- **[@astrojs/sitemap](https://docs.astro.build/en/guides/integrations-guide/sitemap/)** — auto-generated `sitemap-index.xml`.
- Content collection (`src/content/blog/*.md`) for blog posts.
- Deployed on **Cloudflare Pages** via GitHub Actions (`.github/workflows/deploy.yml`).

## Develop

```bash
pnpm install
pnpm dev          # http://localhost:4321
pnpm build        # outputs ./dist
pnpm preview
```

## Deploy

Pushes to the `TheDebateClub` branch trigger a Cloudflare Pages build via the workflow. Project name on Cloudflare: `thedebateclub`.

Required GitHub repo secrets:

- `CLOUDFLARE_API_TOKEN` — token with Pages:Edit permission
- `CLOUDFLARE_ACCOUNT_ID`

## Branches

This repo (a multi-club collection) hosts several sibling sites on separate branches:

- `main` — base/landing
- `TheDebateClub` — this site
- `TheStartupClub`, `TheInfluencersClub` — other clubs

Each branch is its own Pages project; only `TheDebateClub` is wired through this workflow.

## Editing content

- Hero / About / Contact copy lives directly in `src/sections/*.astro`.
- New blog posts: drop a Markdown file into `src/content/blog/`, frontmatter `title`, `date`, `excerpt`, `tags`, optional `draft: true`.
- SEO + structured data (Organization + Event + FAQPage + BlogPosting JSON-LD): `src/components/StructuredData.astro` and `src/layouts/BaseLayout.astro`.
- LLM-friendly summary: `public/llms.txt`.
