# 03-spec-registry-honeymoon-prominence.md

## Introduction/Overview

The Registry section currently displays four gift options (Target, Crate & Barrel, Honeymoon Fund, Household Fund) in equal-sized cards with no visual hierarchy. The couple wishes to prioritize the Honeymoon Fund by placing it first and giving it subtle visual prominence, so guests are more likely to notice and consider contributing to their honeymoon experience.

## Goals

- Re-order registry options so Honeymoon Fund appears first.
- Apply subtle visual emphasis to the Honeymoon Fund card (stronger border, accent color, or slight scale) while keeping the same card size.
- Preserve responsive behavior: same treatment on mobile (first in stack).
- Maintain design consistency with existing sage/cream/charcoal theme.

## User Stories

- **As a wedding guest**, I want the Honeymoon Fund to be easy to find and visually highlighted so that I can quickly consider contributing to the couple's honeymoon.
- **As the couple**, we want our honeymoon fund to be the primary registry option so that guests are encouraged to support our travel experience.

## Demoable Units of Work

### Unit 1: Registry Order and Honeymoon Fund Prominence

**Purpose:** Ensure Honeymoon Fund is first and has subtle visual emphasis; remaining registries follow in the specified order.

**Functional Requirements:**

- The system shall display Honeymoon Fund as the first registry option in the Registry section.
- The system shall display the remaining registries in this order: Crate & Barrel, Target, Household Fund.
- The system shall apply subtle visual emphasis to the Honeymoon Fund card (e.g., stronger border, accent color, or slight scale) while keeping the same card dimensions as other registry cards.
- The system shall use design tokens from `global.css` (sage, charcoal, cream) for any accent or emphasis styling.
- The user shall see the Honeymoon Fund card first on both desktop and mobile layouts.

**Proof Artifacts:**

- Screenshot: Registry section on desktop (lg breakpoint) showing Honeymoon Fund first with subtle emphasis, followed by Crate & Barrel, Target, Household Fund demonstrates ordering and prominence.
- Screenshot: Registry section on mobile showing Honeymoon Fund first in the stack with same emphasis treatment demonstrates responsive behavior.

### Unit 2: Visual Consistency and Accessibility

**Purpose:** Ensure the prominence treatment fits the site aesthetic and remains accessible.

**Functional Requirements:**

- The system shall maintain focus styles and keyboard navigation for the Honeymoon Fund card consistent with other registry cards.
- The system shall not rely solely on color to convey emphasis (e.g., combine border/scale with color).
- The system shall respect `prefers-reduced-motion` if any scale or animation is used.

**Proof Artifacts:**

- Visual inspection: Honeymoon Fund card has visible focus ring and is keyboard-navigable demonstrates accessibility.
- Screenshot: Registry section with reduced-motion preference (or no animation) shows emphasis via border/accent without problematic motion demonstrates reduced-motion compliance.

## Non-Goals (Out of Scope)

1. **Changing registry URLs or content** — No updates to links, names, or descriptions.
2. **Adding new registries or removing existing ones** — All four registries remain.
3. **Major layout changes** — No featured full-width card or multi-column span; card sizes stay equal.
4. **Registry section intro copy** — The "Your presence at our wedding..." text is unchanged.

## Design Considerations

- Use `--color-sage-dark` or `--color-sage` for accent border or subtle background tint on the Honeymoon Fund card.
- Consider a slightly thicker border (e.g., 2px vs 1px) or a soft sage background tint to create emphasis without changing card size.
- Optional: subtle `group-hover:scale-105` (or similar) for the Honeymoon Fund card only, with `prefers-reduced-motion` disabling it.
- Match existing card structure: rounded-2xl, shadow-sm, same padding and typography.

## Repository Standards

- Follow established patterns in `Registry.astro` (Astro component, Tailwind classes).
- Use design tokens from `src/styles/global.css` (`--color-sage`, `--color-sage-light`, `--color-sage-dark`, `--color-charcoal`, `--color-gray`, `--color-cream`).
- Maintain semantic HTML and accessibility patterns per `src/AGENTS.md`.
- Respect `prefers-reduced-motion` for any animations per `global.css`.

## Technical Considerations

- Single file change: `src/components/Registry.astro`.
- Reorder the `registries` array so Honeymoon Fund is first, then Crate & Barrel, Target, Household Fund.
- Add conditional styling for the first (Honeymoon Fund) card: e.g., `class:list` or a `featured`/`isFirst` flag to apply emphasis classes.
- No new dependencies or data files required.

## Security Considerations

No specific security considerations identified. Registry links remain external; no sensitive data is introduced.

## Success Metrics

1. **Order**: Honeymoon Fund is the first registry option displayed.
2. **Prominence**: Honeymoon Fund card has visibly distinct styling (border, accent, or scale) compared to other cards.
3. **Consistency**: Styling uses design tokens and matches site aesthetic.
4. **Responsiveness**: Same treatment on mobile (first in stack).

## Open Questions

No open questions at this time.
