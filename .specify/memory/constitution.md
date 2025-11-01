# IDS Design System Constitution

## Core Principles

### I. Tokens As Single Source of Truth (NON-NEGOTIABLE)
All colors MUST be referenced via `:root` CSS variables (RGB tokens). Spacing and line-height MUST be driven by `--ids__density`. Corner radii MUST use `--ids__radius`. Hardcoded color literals or ad‑hoc spacing/radius values are forbidden in component CSS.

### II. Minimal, Explicit Interactions
Links are visibly underlined by default. Hover/focus states change only color/underline/background using tokens. Glows, blurs, filters, and heavy shadows are prohibited unless explicitly whitelisted for a component.

### III. Typographic & Layout Discipline
Typography MUST use `.ids h1..h6` scales with optional `.XS/.S` modifiers. Vertical rhythm and section spacing MUST use `ids__space` utilities. Content width MUST be constrained by `ids__wrapper` variants (L/XL) — avoid bespoke container widths.

### IV. Consistent Semantics & Naming
Components follow BEM (`block__element--modifier`). Global utilities are prefixed `ids__`. Styles SHOULD be scoped under `.ids` or component blocks to avoid leakage. Prefer class selectors; avoid IDs in CSS.

### V. Accessibility & Responsiveness
All interactive controls MUST provide `:focus-visible` outlines with token colors. Semantic HTML elements and correct roles are required. The 767px breakpoint governs header/menu/burger behavior and wrapper padding; components MUST define behavior at ≤767px.

### VI. Performance Budgets
Non-critical scripts MUST be deferred. Media assets SHOULD be lightweight (target <300KB per micro‑demo). Avoid expensive visual effects. Pages SHOULD meet: LCP < 2.0s (3G‑like), CLS < 0.1, TBT < 200ms.

## Additional Constraints

- Blog pages MUST inherit the same tokens, link styles, and typographic rhythm as the landing.
- Header/menu logic MUST be class‑driven (no inline style hacks except documented body scroll lock).
- Hover effects for the brand/logo, menus, and links MUST not use transitions beyond instantaneous color changes unless IDS explicitly allows.
- Theming (if added) MUST be implemented by overriding tokens only; component CSS remains token‑driven.

## Workflow & Quality Gates

- New components MUST live in their own CSS files; shared primitives remain in `ids.css`/`layout.css`.
- Any new interactive element MUST define hover and focus-visible styles using tokens before merge.
- Readability gates: verify blog and landing share tokens and utilities; no hardcoded colors.
- Accessibility gates: keyboard navigation and focus visibility for all interactive controls.
- Performance gates: image/media optimization and Lighthouse audit recorded for LCP/CLS/TBT.

## Governance

- This Constitution supersedes other practices. Conflicts MUST be resolved by adjusting specs/tasks/plans; do not dilute principles.
- Amendments: require rationale and version bump per semantic rules: MAJOR (breaking principle change), MINOR (new principle/section), PATCH (clarification).
- Compliance: Code review MUST verify token usage, accessibility, responsiveness at 767px, and performance gates. Exceptions MUST be documented.

**Version**: 1.0.0 | **Ratified**: 2025-11-01 | **Last Amended**: 2025-11-01
