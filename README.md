# Medicilio Design System

A library of HTML primitives for fast, on-brand documents and tools.

**Live:** https://fastperrons2.github.io/design-system/

---

## What this is

A set of reusable HTML components, patterns, and standalone apps that produce **branded, professional output for Medicilio** without rebuilding styling from scratch every time.

Used primarily by Claude (Mattia's digital cofounder) when generating HTML deliverables: status reports, plans, post-mortems, decision tools, dashboards. Brand-consistent by construction.

---

## Brand

| Token        | Value     | Usage                          |
|--------------|-----------|--------------------------------|
| Primary      | `#00305b` | Headings, brand identity       |
| Secondary    | `#1a8096` | Supporting accents             |
| Accent       | `#00ffd5` | Highlights, signature strip    |
| Body font    | Titillium Web | All text, all weights      |

The signature gradient strip (primary → secondary → accent) at the top of every header is the recurring visual mark.

---

## Structure

```
design-system/
├── tokens.css          Foundation: colors, type scale, spacing, motion
├── components.css      All component styles
├── index.html          Showroom (live catalog)
├── patterns/
│   └── report-layout.html   Recurring assemblies
└── apps/
    └── triage-board.html    Standalone interactive tools
```

Three levels of granularity:

- **Atoms** — base building blocks (header, stat card, table, timeline, pill, collapsible, comparison columns, section header).
- **Patterns** — pre-assembled layouts for recurring document types (weekly status, post-mortem, etc.).
- **Apps** — standalone interactive tools that close the loop (drag-drop UI → exportable text/markdown).

---

## How Claude uses this

When generating an HTML output for Mattia, Claude:

1. Imports `tokens.css` + `components.css` (or inlines them for standalone files).
2. Picks atoms from the showroom rather than reinventing styling.
3. Assembles patterns when the document type matches a known recurrence.
4. Links to apps when interactivity replaces static text.

A metadata index of components — *when to use each one* — lives in Claude's memory file `08 Templates`.

---

## Adding components

The library is intentionally curated, not exhaustive. New components are added when:

- A real Medicilio output needs something the library doesn't have yet, **and**
- The same need is likely to recur.

Each new component lands in `components.css` (with the `.med-*` BEM convention) and gets a demo + code in `index.html`.

---

## Versioning

Informal. Tag the README's status when something material changes.

**Current:** v0.2 — Foundation tokens + 8 atoms + 1 pattern + 1 app.
