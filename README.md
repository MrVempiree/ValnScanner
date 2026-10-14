# 🔎 ValnScanner

> A work-in-progress security-scanning project built with TypeScript, React, Node.js, and a pnpm workspace.

![Status](https://img.shields.io/badge/status-learning%20%2F%20prototype-blue)
![Stack](https://img.shields.io/badge/TypeScript-React%20%7C%20Node.js-informational)

## 🚀 Overview

ValnScanner is a learning-stage project intended to provide a foundation for security-scanning workflows.

The repository contains a TypeScript monorepo, an Express API service, shared API/database packages, and a web interface.

**Project status:** Prototype. Verify implemented features, supported commands, and security controls before relying on it or presenting it as production-ready.

## 🛠️ Technology Stack

- TypeScript
- React
- Node.js
- Express 5
- pnpm workspaces
- PostgreSQL
- Drizzle ORM
- Zod-based API validation and code generation

## 📂 Project Structure

- `artifacts/api-server/` — Express API service
- `artifacts/mockup-sandbox/` — UI/mockup workspace
- `lib/api-client-react/` — API client helpers
- `lib/api-spec/` — OpenAPI specification and code generation
- `lib/api-zod/` — Generated schemas and types
- `lib/db/` — Database package and schema
- `scripts/` — Repository scripts

## ⚙️ Installation

### Requirements

- Node.js 24
- pnpm
- PostgreSQL
- A configured `DATABASE_URL`

### Clone the repository

```bash
git clone https://github.com/MrVempiree/ValnScanner.git
cd ValnScanner
pnpm install
```

### Configure the environment

Set your local database connection string using your environment configuration.

Example format:

```env
DATABASE_URL=postgres://USER:PASSWORD@HOST:5432/DATABASE
```

Use your actual local development credentials. Never commit passwords or secrets to GitHub.

### Type checking

```bash
pnpm run typecheck
```

### Build

```bash
pnpm run build
```

### Start the API in development

```bash
pnpm --filter @workspace/api-server run dev
```

The repository configuration identifies port `5000` for API development. Check the package scripts and environment settings if the service does not start.

## 🔐 Responsible Security Testing

If this project includes scanning functionality, use it only on systems you own or have explicit authorization to test.

- Test inside local labs or approved scopes.
- Never collect real users' credentials, cookies, or personal data.
- Review authentication and authorization before deployment.
- Restrict scanner targets where remote scanning is supported.
- Review CORS, rate limits, and logging.
- Do not expose development services publicly without a security review.

## 🗺️ Roadmap

- [ ] Replace remaining documentation placeholders
- [ ] Document verified features
- [ ] Add application screenshots
- [ ] Improve setup and troubleshooting instructions
- [ ] Add automated tests
- [ ] Add CI checks for type checking and builds
- [ ] Review API authentication and input validation
- [ ] Review CORS configuration
- [ ] Implement safe target restrictions where applicable
- [ ] Document responsible vulnerability reporting

## 🤝 Contributing

Bug reports and pull requests are welcome.

Please include reproducible steps, expected behavior, actual behavior, and environment details.

Never include secrets, personal data, or information from unauthorized targets.

## 👨‍💻 Maintainer

**Lavish Gangwar**

GitHub: [@MrVempiree](https://github.com/MrVempiree)

## ⚠️ Disclaimer

ValnScanner is a learning-stage project. Do not assume it is production-ready or that its results are comprehensive.

Use it responsibly and comply with applicable laws and authorization requirements.
