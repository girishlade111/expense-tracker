# Expense Tracker

A modern, client-side expense tracking web app built with Next.js. Add expenses, organize them by category, search and filter transactions, and visualize spending with an interactive dashboard — all in a clean, shadcn/ui-powered interface.

Originally generated with [v0.app](https://v0.app) and customized further.

## Features

- **Add expenses** — amount, description, category, and date via a dialog form
- **Category system** — Food, Transport, Shopping, Bills, Entertainment, Other, each with its own color and icon
- **Dashboard summary** — total spend, income/spend balance, and category breakdown at a glance
- **Search & filter** — instant search across expense descriptions, filter by category
- **Tabs & views** — switch between overview, transactions, and breakdown views
- **Responsive UI** — mobile-friendly layout with dark-mode support (next-themes)
- **Zero backend** — everything runs in the browser; no login, no database, no tracking

## Tech Stack

- **Framework:** Next.js 15 (App Router, static export)
- **Language:** TypeScript + React 19
- **UI:** shadcn/ui components, Radix UI primitives, Tailwind CSS
- **Icons:** Lucide React
- **Charts-ready:** Recharts included
- **Forms:** React Hook Form + Zod validation
- **Deploy:** GitHub Pages (static `output: 'export'` build)

## Quick Start

Prerequisites: Node.js 18+ and npm.

```bash
# Install dependencies
npm install

# Start the dev server
npm run dev
# → http://localhost:3000

# Production build (static export to ./out)
npm run build
```

## Project Structure

```
expense-tracker/
├── app/
│   ├── layout.tsx        # Root layout (fonts, theme provider)
│   ├── page.tsx          # Home page → renders ExpenseTracker
│   └── globals.css       # Tailwind + custom styles
├── components/
│   ├── theme-provider.tsx
│   └── ui/               # shadcn/ui primitives (button, card, dialog, input, ...)
├── lib/
│   └── utils.ts          # cn() class-merge helper
├── expense-tracker.tsx   # Main expense tracker component (dashboard UI)
├── next.config.mjs       # Static export config (output: 'export')
├── tailwind.config.js
└── public/               # Static assets
```

## Environment Variables

None. The app is fully client-side and needs no API keys or secrets.

## Deployment Notes

- The repo is configured for **static export** (`output: 'export'` in `next.config.mjs`) and deploys to **GitHub Pages** via the `gh-pages` branch.
- Because GitHub Pages serves the site from a subpath (`https://girishlade111.github.io/expense-tracker/`), `basePath: '/expense-tracker'` is set in `next.config.mjs`.
  - If you deploy this app to Vercel (root domain), **remove the `basePath` line** — absolute asset paths work correctly at the root, and the basePath would prefix all routes incorrectly.
- `next.config.mjs` ignores ESLint/TypeScript errors during builds (inherited from the v0 scaffold) — worth cleaning up in the long term.

---

Built by Girish Lade — https://ladestack.in
