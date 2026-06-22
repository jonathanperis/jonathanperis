# Astro 7 Pages Standard

> Static documentation baseline for Jonathan's Astro/GitHub Pages repos after the Astro 7 release.

## Repository-scope finding

This `jonathanperis` profile repository does not contain an Astro app or docs package to upgrade directly: there is no `package.json`, `astro.config.*`, `src/pages`, or `docs/` build tree in this repo. Its Astro-relevant responsibility is to document the shared standard used by the service and docs repos that publish Astro-generated GitHub Pages surfaces.

## What Astro 7 changes for our Pages docs

Astro 7 is a fit for the Markdown/static Pages documentation surfaces because its default improvements are build-time and developer-experience upgrades:

| Astro 7 feature | Fit for our static Pages repos | Adoption note |
|-----------------|---------------------------------|---------------|
| Rust `.astro` compiler | Yes | Faster builds and stricter template validation. Fix invalid/unclosed markup instead of relying on the older compiler's corrections. |
| Sätteri Markdown/MDX pipeline by default | Yes, when docs render Markdown/MDX | Prefer Astro 7 defaults. Remove old explicit `@astrojs/markdown-satteri` wiring unless a repo intentionally owns a custom processor path. |
| Queue-based rendering | Yes | Default rendering behavior; no config churn needed. |
| Vite 8 and Rolldown | Yes | Upgrade Astro/integrations and let the toolchain pick up the faster bundler path. Review only repos with custom Vite plugins/options. |
| AI/dev-tooling logging and background development improvements | Yes for maintainers/agents | Useful operationally, but not a reason to add public proof pages or runtime features. |

## Standard upgrade path for consumer repos

1. Inventory the repo first: `package.json`, `astro.config.*`, `src/pages/**`, Markdown/content roots, and Pages workflows.
2. Upgrade Astro and official integrations together, normally with `npx @astrojs/upgrade` or the repo's package-manager equivalent.
3. Keep GitHub Actions on a modern Node runtime: Node `>=22.12.0` is required, and Node 24 is the preferred Pages workflow default.
4. Remove Astro 6.4-era explicit Sätteri imports/config when they only duplicate Astro 7's defaults.
5. Preserve static GitHub Pages settings: `output: 'static'`, `site`, `base`, `outDir`, sitemap integration, and project-base-aware links.
6. Build with production settings and verify generated output, not just dependency resolution.

## Features to skip for static GitHub Pages

Do not add these just because they are in the Astro 7 announcement:

- `src/fetch.ts` advanced routing for static-only Pages repos without a request pipeline.
- Route caching or CDN cache providers unless the repo is moving to SSR/edge hosting.
- Netlify, Vercel, Cloudflare, or other adapters unless the deployment target changes.
- Public "proof" pages whose only purpose is demonstrating framework internals.

Those features should be tracked as future-hosting options, not mixed into routine static Pages upgrades.

## Verification gates

For every repo that actually owns an Astro docs package, the upgrade is not done until these pass:

```bash
node --version
npm --version
npm install
NODE_ENV=production npm run build
```

Adapt `npm` to the repo's chosen package manager when appropriate, but keep the shell `node` version at the Astro-required level rather than assuming a JavaScript action runtime changes it.

After the build:

- Smoke generated routes under the configured GitHub Pages base path.
- Verify every generated `/_astro/*.css` and `/_astro/*.js` reference exists in the output directory.
- Check representative Markdown-heavy routes for headings, tables, code blocks, raw HTML, and internal links.
- If Pagefind/search is present, compare page and word counts before and after the upgrade.
- Open a focused PR with the dependency/config changes and the verification output.
