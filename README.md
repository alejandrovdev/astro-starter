# Astro Starter

A production-ready Astro starter template with React, Tailwind CSS v4, shadcn/ui, dark mode, SEO, and a full development toolchain.

## Tech Stack

- **[Astro](https://astro.build)** v6 — Static site generation with island architecture
- **[React](https://react.dev)** v19 — Interactive components via Astro islands
- **[Tailwind CSS](https://tailwindcss.com)** v4 — Utility-first styling with OKLCH color space
- **[shadcn/ui](https://ui.shadcn.com)** — Accessible component library (Radix UI + CVA)
- **[TypeScript](https://www.typescriptlang.org)** v5 — Strict mode enabled

## Features

- **Dark mode** — System preference detection + manual toggle with localStorage persistence. No flash of wrong theme thanks to an inline script in the layout
- **SEO** — Auto-generated sitemap, dynamic robots.txt, and meta tags
- **Component library** — shadcn/ui with Button (6 variants, 6 sizes) and DropdownMenu components ready to use
- **Code quality** — ESLint, Prettier (with Tailwind class sorting + import organizing), TypeScript checking
- **Git hooks** — Husky + lint-staged for pre-commit linting, commitlint for conventional commits
- **CI/CD** — GitHub Actions pipeline with lint, format, build, and commit message validation

## Getting Started

### Prerequisites

- Node.js >= 22.12.0 (see `.nvmrc`)
- pnpm 10+

### Setup

```bash
pnpm install
cp .env.example .env  # Configure SITE_URL for sitemap generation
pnpm dev              # http://localhost:4321
```

## Project Structure

```
src/
├── components/
│   ├── mode-toggle.tsx          # Theme switcher (light/dark/system)
│   └── ui/
│       ├── button.tsx           # shadcn Button with CVA variants
│       └── dropdown-menu.tsx    # shadcn DropdownMenu (Radix UI)
├── layouts/
│   └── main.astro               # Root layout with dark mode script
├── lib/
│   └── utils.ts                 # cn() utility (clsx + tailwind-merge)
├── pages/
│   ├── index.astro              # Home page
│   └── robots.txt.ts            # Dynamic robots.txt generation
└── styles/
    └── global.css               # Tailwind v4 theme variables (OKLCH)
```

## Commands

| Command           | Action                                    |
| :---------------- | :---------------------------------------- |
| `pnpm dev`        | Start dev server at `localhost:4321`      |
| `pnpm build`      | Build production site to `./dist/`        |
| `pnpm preview`    | Preview production build locally          |
| `pnpm lint`       | Run ESLint                                |
| `pnpm lint:fix`   | Auto-fix lint errors                      |
| `pnpm format`     | Check formatting with Prettier            |
| `pnpm format:fix` | Auto-format with Prettier                 |
| `pnpm typecheck`  | Run TypeScript checking via `astro check` |

## Adding shadcn/ui Components

```bash
pnpm dlx shadcn@latest add <component-name>
```

Components are installed to `src/components/ui/` and configured via `components.json`.
