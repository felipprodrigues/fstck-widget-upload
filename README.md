# Upload Widget Platform

## About
Upload Widget Platform is a full-stack image upload system composed of a React-based widget, a Node.js API with PostgreSQL and Cloudflare R2, and a CI pipeline that validates changes with automated tests. The frontend focuses on a smooth upload experience, while the backend provides validated, scalable storage and export workflows.

## UI Preview
![Upload widget preview 1](https://github.com/user-attachments/assets/e245d8fa-31ca-4dac-a76a-bee59a304239)
![Upload widget preview 2](https://github.com/user-attachments/assets/f5c0cbdf-cd05-44fd-bce0-ee8c9869b462)
![Upload widget preview 3](https://github.com/user-attachments/assets/3c804900-55b6-4290-8b4b-6376006cd514)
![Upload widget preview 4](https://github.com/user-attachments/assets/616fd739-112f-42de-84b7-1439ee606226)

## Repository Structure
- web/ - React + Vite upload widget UI
- server/ - Fastify API, PostgreSQL, Cloudflare R2 integration
- ci/ - GitHub Actions workflow and test configuration

## Frontend (web)
The web app provides the upload widget UI with compression, resizing, retry, and download flows. It is built with React, Vite, TailwindCSS, Zustand, and Radix UI.

Prerequisites:
- Node.js 20.18.2
- pnpm

Common commands:
- `pnpm install`
- `pnpm run dev`
- `pnpm run build`
- `pnpm run preview`

See full details in [web/README.md](web/README.md).

## Backend (server)
The API handles uploads, listing, and CSV exports, using Fastify, Drizzle ORM, PostgreSQL, and Cloudflare R2. It supports local development with Docker Compose.

Prerequisites:
- Node.js 20.18.2
- pnpm
- Docker and Docker Compose (optional)

Common commands:
- `pnpm install`
- `pnpm run dev`
- `pnpm run test`

Environment variables (example):
```ini
PORT=3333
NODE_ENV=development
DATABASE_URL="postgresql://docker:docker@localhost:5432/upload"
CLOUDFLARE_ACCOUNT_ID=""
CLOUDFLARE_ACCESS_KEY_ID=""
CLOUDFLARE_SECRET_ACCESS_KEY=""
CLOUDFLARE_BUCKET=""
CLOUDFLARE_PUBLIC_URL="https://pub-secret"
```

See full details in [server/README.md](server/README.md).

## CI (ci)
The CI workflow runs on pull requests and executes tests using a Postgres service and pnpm. It installs dependencies with a frozen lockfile and runs the test suite.

See more details in [ci/.README](ci/.README).

## Development Notes
- Use `nvm use` to load the required Node.js version from `.nvmrc`.
- Run the frontend from `web/` and the backend from `server/` in separate terminals.
