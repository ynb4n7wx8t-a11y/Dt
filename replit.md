# Workspace

## Overview

DataxX — a route planning, calendar, and operations management PWA for delivery services. Ported from https://github.com/ynb4n7wx8t-a11y/Ddata.git into the Replit pnpm monorepo.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React 19 + Vite + Tailwind CSS v4 + Radix UI + Leaflet/React-Leaflet + LightGallery + PrimeReact
- **API framework**: Express 5 (shared `@workspace/api-server`)
- **Database**: Replit PostgreSQL accessed via `pg.Pool` from `@workspace/db`
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle for the API server), Vite for the client

## Artifacts

- `artifacts/ddata` — DataxX React app (mounted at `/`)
- `artifacts/api-server` — Express API mounted at `/api`, exposes route, calendar, deliveries, notes, plano, rooster, route-notes, and proxy-image endpoints used by the DataxX app
- `artifacts/mockup-sandbox` — design canvas (unused by DataxX)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally
- `pnpm --filter @workspace/ddata run dev` — run DataxX client locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
