# CLAUDE.md

Guide for Claude Code working in this repository. Keep it short and current: if you learn
something non-obvious about this project, add it here.

## What this is

Finovate.AI ("Intelligent Finance"): a marketing/showcase website for AI finance automation:
invoice processing, AR management, ledger reconciliation, and a RAG assistant. Built with
**Astro 4**, deployed on Vercel at https://finovate-ecru.vercel.app.

Note: `README.md` is still the default Astro starter text and does not describe this project.

## Commands (Node ≥ 18.17)

```bash
npm install
npm run dev          # http://localhost:4321
npm run build        # must succeed before committing (Vercel runs this; output in dist/)
npx astro check      # type-check .astro files
```

## Layout

```
src/
  layouts/Layout.astro      <html> shell, meta description, imports styles/global.css
  pages/                    one file per route: index, about, invoice-processing, ar-management,
                            rag-assistant, architecture, contact
  components/               Navbar, Footer, Button, Card, GlowBackground (Welcome.astro is unused starter code)
  styles/global.css         design tokens in :root (brand blue #0066FF, orange #FF4D00, dark glass cards), Inter font
public/                     favicon
Template/                   reference screenshots of the intended design (not served)
```

## Rules that matter

- Every page uses `Layout` + `Navbar` + `Footer` (+ `GlowBackground`); a new page goes in `src/pages/` and must be linked from `Navbar`.
- Use the CSS variables in `global.css` instead of hard-coded colours, radii or transitions.
- Dark theme only; check layouts at phone width (~375px).
- The contact form (`pages/contact.astro`) has no backend yet; don't claim it sends anything.
- Static site: no server-side code unless an Astro adapter is added deliberately.
