# Repository Guidelines

## Project Structure & Module Organization
- `app/` is the Next.js App Router (routes like `app/page.tsx`, feature areas such as `app/builder`, and API routes under `app/api/`).
- UI building blocks live in `components/`, state in `atoms/`, and reusable hooks in `hooks/`.
- Shared logic is in `lib/` and `utils/`, and shared types are in `types/`.
- Styles and assets: `app/globals.css`, `styles/`, `tailwind.config.ts`, and `public/`.
- `packages/` is reserved for internal packages if/when added.

## Build, Test, and Development Commands
- `pnpm dev` (or `npm run dev`): start the dev server with Turbopack at `http://localhost:3000`.
- `pnpm build`: create a production build; `pnpm start`: serve the build.
- `pnpm lint`: run Next.js ESLint rules.
- Tests: `npm run test:api` and `npm run test:code` run Node scripts expected under `tests/`. `test:all` currently references a `test:integration` script that is not defined, so run the individual scripts or add it if needed.

## Coding Style & Naming Conventions
- TypeScript + React with strict type checking (`tsconfig.json`).
- ESLint extends `next/core-web-vitals` and `next/typescript`; some rules are relaxed (e.g., `no-explicit-any` and `no-unused-vars` are off).
- Follow the existing file style (2-space indentation; quotes and semicolons follow local file patterns). Avoid formatting-only churn.
- Use the root alias `@/` for imports when appropriate.

## Testing Guidelines
- Tests are plain Node scripts; place new tests in `tests/` as `*.test.js` and wire scripts in `package.json`.
- Focus on API endpoints and code-execution flows; keep tests fast and deterministic.

## Commit & Pull Request Guidelines
- Recent commits use short, descriptive phrases (often lowercase). Prefer concise, imperative messages (e.g., "add provider manager").
- PRs should include a brief description, testing steps, and screenshots for UI changes.

## Environment & Configuration
- Create `.env.local` with required keys (e.g., `FIRECRAWL_API_KEY`, provider keys like `OPENAI_API_KEY`, and sandbox settings). See `README.md` for the full list and examples.
