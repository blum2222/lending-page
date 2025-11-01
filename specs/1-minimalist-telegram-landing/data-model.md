# Data Model

> Static site v1: No server-side persistence. Entities describe content structure used in HTML templates.

## Entities

### Post
- id: slug (string)
- title: string
- date: ISO date (YYYY-MM-DD)
- excerpt: short string (<=200 chars)
- content: HTML (semantic headings, figures, code blocks)
- cover: image URL (optional)
- tags: [string] (optional)

Constraints:
- Unique slug per post.
- Use semantic headings (h1 once, then h2/h3).
- Images optimized (webp preferred).

### FeatureCard
- key: enum (forwarding | summarization | grouping)
- title: string
- description: string (<=240 chars)
- media: { type: "webm"|"gif"|"image", src: URL, alt: string }

Constraints:
- Media size <300KB where feasible.
- Respect reduced motion preference (don’t auto-play if prefers-reduced-motion).

### MenuItem
- label: string
- href: string (anchor or path)
- order: number

Constraints:
- Header shows primary items (Главная, Цены, Блог).
- Mobile menu mirrors header structure.
