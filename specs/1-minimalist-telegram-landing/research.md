# Research & Decisions

## Decisions

- Pricing placement: Main page block with anchor.
  - Rationale: Minimalism, immediate clarity without page change.
  - Alternatives: Separate page; external doc.

- Blog source: Static HTML pages.
  - Rationale: Matches stack (HTML/CSS/JS), total control over typography.
  - Alternatives: Markdown + generator; Headless CMS.

- Email capture: Footer, minimalist.
  - Rationale: Non-intrusive, respects primary CTA focus, still captures interest.
  - Alternatives: Header placement; no form in v1.

- Feature media: Micro-demos and/or screenshot carousel depending on context.
  - Rationale: Showcases value quickly while keeping page light; fallback to static when needed.
  - Alternatives: Only static images; no media.

- Analytics & consent: Google Analytics + consent banner.
  - Rationale: Familiar tooling; explicit consent for compliance.
  - Alternatives: Privacy-first analytics without cookies; no analytics in v1.

## Implementation Notes

- Respect reduced-motion: do not auto-play demos for users who prefer reduced motion.
- Keep media assets small (<300KB per clip/gif) and optimized.
- Use existing IDS tokens for color/spacing; avoid ad-hoc styles.
