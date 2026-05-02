# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install      # install dependencies (required before first run)
npm run dev      # start dev server at http://localhost:5173
npm run build    # production build
npm run preview  # preview production build
npm run lint     # run ESLint
```

There is no test suite configured.

## Architecture

This is a minimal React 19 + Vite app. All application logic lives in a single file: `src/App.jsx`.

**State** — `App` holds all state via `useState`:
- `transactions`: array of `{ id, description, amount, type, category, date }` — seeded with hardcoded data; no persistence
- Form fields: `description`, `amount`, `type`, `category`
- Filter fields: `filterType`, `filterCategory`

**Known bugs in the starter** — `amount` is stored as a string (not a number), so `totalIncome`, `totalExpenses`, and `balance` computed at render time produce incorrect results due to string concatenation instead of numeric addition. The "Freelance Work" entry is also incorrectly typed as `"expense"` instead of `"income"`.

**Styling** — flat CSS in `src/App.css` and `src/index.css`; no CSS framework.

**No routing, no backend, no persistence** — state resets on page reload.
