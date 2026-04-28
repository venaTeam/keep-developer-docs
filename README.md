# Keep Developer Guide

The official developer documentation for the **Keep** alerting and on-call management platform.

This site is built with [Mintlify](https://mintlify.com/) and is the canonical reference for engineers working on Keep's backend microservices, frontend, and integrations.

## What's inside

- **Architecture** — repository layout, data flow, messaging layer (Kafka / Redis).
- **Services** — per-microservice deep dives: `keep-api-gateway`, `keep-event-handler`, `keep-workflows`, `keep-ui`.
- **Components** — alert manager, workflow engine, rules engine, providers.
- **Operations** — deployment, authentication (Keycloak), observability, sequence diagrams.

## Local preview

```bash
npm install
npm run dev
```

The site will be available at `http://localhost:3000`.

`npm run dev` is a thin alias for `mintlify dev` (see `package.json`). If you'd rather have Mintlify globally installed, `npm i -g mintlify && mintlify dev` works too.

## Editing

Each page is an `.mdx` file. Pages are grouped into folders that match the navigation in `mint.json`. To add a new page:

1. Create the file under the relevant folder (e.g. `services/new-service.mdx`).
2. Add the file path (without the `.mdx` extension) to the right `pages` array in `mint.json`.
3. Open a PR — preview deployments are produced automatically.

## Repository layout

This is the **standalone developer docs repository**. The Keep platform itself lives in several sibling repositories under the `keep` organization:

| Repository | Purpose |
| --- | --- |
| [`keep-api-gateway`](https://github.com/keephq/keep-api-gateway) | Lightweight ingress — auth, validation, produces events to the broker. |
| [`keep-event-handler`](https://github.com/keephq/keep-event-handler) | Standalone consumer — parses, deduplicates, persists, indexes alerts. |
| [`keep-workflows`](https://github.com/keephq/keep-workflows) | Workflow engine — schedules and runs YAML-defined automations. |
| [`keep`](https://github.com/keephq/keep) | Frontend (`keep-ui/`) and shared infra (Docker compose, examples). |

See [`architecture/repository-layout`](./architecture/repository-layout.mdx) for the full breakdown.

## License

Apache 2.0 — same as the rest of Keep.
