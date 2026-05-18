# trainar-developers

The gated partner portal at developers.trainar.ai.

For partners building shipped integrations, Marketplace bundles, Nango connectors, platform-level skills, and curators publishing on the TrainAR Marketplace.

## Develop

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

Outputs static site to `dist/`. Deployed via Netlify on push to `main`.

## Architecture

- **Astro 6** + **Tailwind v4** + same Design System as `trainar-docs`.
- **Static** — no runtime data fetch (the form POSTs directly to a Supabase edge function).
- **Form submissions** POST to `submit-developer-access-request` edge fn on prod Supabase, which inserts into `developer_access_requests` table + notifies via email.

## Sprint roadmap

- **58.5a (current)** — public landing + request-access form
- **58.5b (next)** — Dashboard side: RLS gate on developer docs, super-admin approval UI for requests, scoped super-tenant token issuance
- **58.5c** — actual gated content authored: Super-Tenant API, Marketplace bundle authoring guide, Nango connector contribution, curator economic model, platform-skill spec
