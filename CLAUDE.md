@AGENTS.md

# Nathan Jolley — Portfolio

Personal portfolio site. Currently a blank starter; this file will grow as the site does.

- Live: https://nathan-jolley.vercel.app
- Repo: https://github.com/Clewball/nathan-jolley
- Vercel project: `nathan-jolley` (team: clewball's projects)

## Stack

- Next.js 16 (App Router) + React 19
- TypeScript (strict)
- Tailwind CSS v4 (configured in `src/app/globals.css` via `@theme`; there is no `tailwind.config` file)
- ESLint (`eslint-config-next`)
- npm
- Hosted on Vercel; pushes to `main` deploy to production, and PRs get preview deployments

## Commands

```bash
npm run dev        # local dev server at http://localhost:3000
npm run build      # production build (run before pushing)
npm run lint       # ESLint
npm run typecheck  # TypeScript, no emit
```

## Project structure

```
src/
  app/                 # Routes (App Router). layout.tsx, page.tsx, globals.css
  components/
    ui/                # Small reusable primitives (Button, Card, ...)
    layout/            # Site chrome (Header, Footer, Nav)
    sections/          # Page sections (Hero, Projects, About, Contact)
  data/                # Portfolio content as typed data (projects, experience, links)
  lib/                 # Helpers and config (site.ts holds site name/metadata)
  types/               # Shared TypeScript types
public/
  images/              # Static images (headshot, project screenshots)
```

Import from `src` with the `@/` alias (e.g. `import { siteConfig } from "@/lib/site"`).

## Conventions

- Default to Server Components; add `"use client"` only when a component needs state, effects, or browser APIs.
- Style with Tailwind utility classes. Put design tokens (colors, fonts) in `@theme` in `globals.css`.
- Keep content (project lists, bios, links) in `src/data/`, not hard-coded in components.
- One component per file, PascalCase filenames (`ProjectCard.tsx`).
- Run `npm run lint`, `npm run typecheck`, and `npm run build` before committing.

## To decide later

- Visual design and color palette
- Pages and sections (single page or multiple routes?)
- Custom domain
- Analytics, contact form, blog/MDX
