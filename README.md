# eas-blog

Monorepo for [eas.web.id](https://eas.web.id): Astro frontend + Strapi CMS.

This is a **source** monorepo. The two apps do not share a host.

| App | Path | Source | Runtime |
| --- | --- | --- | --- |
| Web | `apps/web` | [easterneas/eas-site](https://github.com/easterneas/eas-site) `@eas/blog` | Astro 5 → Cloudflare Pages |
| CMS | `apps/cms` | [easterneas/site](https://github.com/easterneas/site) `@master` (`eas-hcms`) | Strapi 5 + Postgres |

Do not import `site` branch `deploy`. That is a stale Strapi 4 snapshot.

## Setup

Needs Node 20 (see `.nvmrc`).

```bash
bun install
```

## Scripts

```bash
bun run dev:web   # Astro, usually :4321
bun run dev:cms   # Strapi, usually :1337
bun run build:web
bun run build:cms
```

Copy each app's `.env.example` before running.

- Web: `PUBLIC_API_URL`, `API_TOKEN`, `PUBLIC_SITE_URL`, `PUBLIC_SITE_NAME`
- CMS: Strapi secrets from `apps/cms/.env.example`

The old repos stay as-is until this tree is the source of truth.
