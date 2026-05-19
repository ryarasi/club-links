# The Startup Club — startupclub.live

Source for [startupclub.live](https://startupclub.live), the home of The Startup Club — a community for India's founders, investors, mentors, and ecosystem enablers.

Daily content across innovation, fundraising, product/GTM, founder craft, and ecosystem and policy. Follow on [LinkedIn](https://www.linkedin.com/company/the-startup-club-india), [X](https://x.com/startupclublive), and [Instagram](https://www.instagram.com/startupclub.live/).

## Stack

- **[Astro 5](https://astro.build)** — static site generator, single-page anchored layout (Home / About / Join / Blog / Follow) plus a per-post blog route at `/blog/<slug>/`.
- **[Tailwind CSS 4](https://tailwindcss.com)** — utility styling, design tokens in `src/styles/global.css`.
- **[@astrojs/sitemap](https://docs.astro.build/en/guides/integrations-guide/sitemap/)** — auto-generated `sitemap-index.xml`.
- Content collection (`src/content/blog/*.md`) for blog posts.
- Deployed on **Cloudflare Pages** from the `TheStartupClub` branch of this repo.

## Develop

```bash
pnpm install   # or: npm install
pnpm dev       # http://localhost:4321
pnpm build     # outputs ./dist
pnpm preview
```

## Deploy

Pushes to the `TheStartupClub` branch trigger the Cloudflare Pages build for the TSC project. Pages project name: `the-startup-club` (to be created on first deploy).

## Branches

This repo hosts sibling sites on separate branches:

- `TheDebateClub` — The Debate Club at thedebateclub.info
- `TheStartupClub` — this site at startupclub.live

## Editing content

- Hero / About / Powered-by-Clikkin / Follow copy lives directly in `src/sections/*.astro`.
- New blog posts: drop a Markdown file into `src/content/blog/`, frontmatter `title`, `date`, `excerpt`, `tags`, optional `draft: true`.
- SEO + structured data (Organization + WebSite + FAQPage + BlogPosting JSON-LD): `src/components/StructuredData.astro` and `src/layouts/BaseLayout.astro`.
- LLM-friendly summary: `public/llms.txt`.
