# Contributing to ValnScanner

Thank you for your interest in contributing to ValnScanner! This guide explains how to set the project up, check your changes, and open issues and pull requests.

## Ground rules

- Only scan systems you own or have explicit, written authorisation to test. ValnScanner is a defensive security tool: never use it against targets without permission.
- Never commit secrets, credentials, tokens, or real scan results from systems you do not own. Use placeholder values in examples.
- Keep pull requests focused on one change at a time.

## Prerequisites

- Node.js 24
- pnpm (the project uses pnpm workspaces)
- PostgreSQL (for the API server's database)
- Git

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/MrVempiree/ValnScanner.git
cd ValnScanner
```

### 2. Install dependencies

```bash
pnpm install
```

### 3. Configure the environment

Create a `.env` file with a `DATABASE_URL` that points at your local PostgreSQL database, for example:

```env
DATABASE_URL=postgres://USER:PASSWORD@localhost:5432/valnscanner
```

Use local, throwaway credentials only, and never commit a real `.env` file.

### 4. Verify your setup

```bash
pnpm run typecheck
pnpm run build
```

Both commands must pass before you open a pull request.

### 5. Run the API server in development

```bash
pnpm --filter @workspace/api-server run dev
```

The workspace layout is `apps/api-server` (Express 5 API), `apps/client` (web interface), and `packages/` (shared TypeScript code).

## Running tests

ValnScanner does not have an automated test suite yet - adding one is on the project roadmap. Until a test runner is in place, verify every change with:

```bash
pnpm run typecheck
pnpm run build
```

and describe the manual checks you performed (commands run and their result) in your pull request. If you add a feature, please add tests for it where a test harness exists, or note in the PR that test coverage is still pending.

## Coding style

- Write TypeScript and follow the style already used in the file you are changing: two-space indentation, strict typing, and no unused imports or variables.
- Prefer small, readable functions and explicit types over clever one-liners.
- Keep the API, client, and shared packages separated: do not import server-only code (for example database access) from the client.
- Do not add a new dependency without explaining why in the pull request. Prefer the standard library and the dependencies already in the workspace.
- Update the README or other docs when a change affects setup, configuration, or behaviour.

## How to open an issue

1. Search existing issues first - your problem or idea may already be reported.
2. Use a clear title that says what is wrong or what you want.
3. For bugs, include: what you did, what you expected, what happened instead, the commands and their output, and your environment (Node.js and pnpm versions, operating system, database setup).
4. For feature requests, explain the use case and how it fits ValnScanner's defensive, authorised-testing purpose.
5. Never include secrets, credentials, or findings from unauthorised scans in an issue.

## How to open a pull request

1. Fork the repository and create a branch from `main` for your change, for example `fix/typo-in-readme` or `feat/add-test-harness`.
2. Make your change, then run `pnpm run typecheck` and `pnpm run build` and fix any errors.
3. Commit with a clear message that explains the change, for example `fix: correct the API port in the README`.
4. Push your branch and open a pull request against `main`. Describe what the change does, why it is needed, how you verified it, and link any related issue.
5. Keep the pull request focused: one change per pull request makes review faster.
6. A maintainer will review your pull request. Please respond to review comments and update the branch as needed.

## Reporting security issues

If you find a security vulnerability in ValnScanner itself, do not open a public issue. Contact the maintainer privately so it can be fixed before details are published.

Thank you for helping improve ValnScanner!
