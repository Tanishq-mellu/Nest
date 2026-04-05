# Frontend

The OWASP Nest frontend is a modern web application built with [Next.js](https://nextjs.org/).

## Tech Stack

| Component         | Technology                         |
| ----------------- | ---------------------------------- |
| **Framework**     | Next.js 16.x (React 19)            |
| **Language**      | TypeScript                         |
| **Styling**       | TailwindCSS 4.x                    |
| **UI Library**    | HeroUI                             |
| **Data Fetching** | Apollo Client (for GraphQL)        |
| **Mapping**       | Leaflet / React Leaflet            |
| **Testing**       | Jest (unit/a11y), Playwright (e2e) |

## Frontend Features

The OWASP Nest frontend provides an interactive interface for exploring the OWASP ecosystem and its contributors. Key capabilities include:

- **Project Discovery** – Browse OWASP projects and explore their details.
- **Contributor Profiles** – View contributor activity across OWASP repositories.
- **GitHub Integration** – Fetch contributor and repository data using GitHub APIs.
- **Interactive UI** – Modern responsive interface built with Next.js and TailwindCSS.
- **Community Visibility** – Helps highlight active contributors and project maintainers across the OWASP ecosystem.

The frontend communicates with the backend services through GraphQL APIs and renders contributor and project data in an easy-to-navigate interface.

## Directory Structure

The frontend code lives in this directory. Key directories include:

- `src/` - Application source code (pages, components, hooks).
- `public/` - Static assets.
- `__tests__/` - Automated tests.

## Running Locally

The project uses **Docker** for local development. From the project root:

```bash
# Start all services (frontend, backend, db, cache)
docker compose -f docker-compose/local/compose.yaml up
```

To run the frontend development server directly (requires dependencies installed):

```bash
cd frontend
pnpm install
pnpm run dev
```

## Key Scripts

Common `pnpm` scripts defined in `package.json`:

| Task                   | Command                    |
| ---------------------- | -------------------------- |
| Start dev server       | `pnpm run dev`             |
| Build for production   | `pnpm run build`           |
| Lint code              | `pnpm run lint`            |
| Format code            | `pnpm run format`          |
| Generate GraphQL types | `pnpm run graphql-codegen` |
| Run unit tests         | `pnpm run test:unit`       |
| Run e2e tests          | `pnpm run test:e2e`        |

See the `Makefile` for Docker-based convenience targets.

## GraphQL Codegen

TypeScript types for GraphQL operations are auto-generated from the backend schema.

- Configuration: `graphql-codegen.ts`
- Output: `src/types/__generated__/`

Run the codegen with:

```bash
# Requires the backend to be running
pnpm run graphql-codegen
```

## Dependencies

Dependencies are managed with [pnpm](https://pnpm.io/). The configuration is in `package.json`.

```bash
# Update dependencies
cd frontend && pnpm update
```
