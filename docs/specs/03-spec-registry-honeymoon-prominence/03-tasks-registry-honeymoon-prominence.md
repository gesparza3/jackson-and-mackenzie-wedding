## Relevant Files

- `src/components/Registry.astro` - Contains registry list, card layout, and styling; sole file requiring modification for order and prominence.
- `src/styles/global.css` - Design tokens (sage, charcoal, cream) and `prefers-reduced-motion` pattern; reference for styling and accessibility.

### Notes

- No unit tests exist for Registry component; use `npm run build` and local preview for verification.
- Follow existing Astro + Tailwind patterns in `Registry.astro`.

## Tasks

### [x] 1.0 Reorder registry options and apply subtle prominence to Honeymoon Fund

#### 1.0 Proof Artifact(s)

- Screenshot: Registry section on desktop (lg breakpoint) showing Honeymoon Fund first with subtle emphasis, followed by Crate & Barrel, Target, Household Fund demonstrates ordering and prominence.
- Screenshot: Registry section on mobile showing Honeymoon Fund first in the stack with same emphasis treatment demonstrates responsive behavior.

#### 1.0 Tasks

- [x] 1.1 Reorder the `registries` array in `Registry.astro` so Honeymoon Fund is first, then Crate & Barrel, Target, Household Fund.
- [x] 1.2 Update the card map to detect the first item (e.g., `index === 0` or `registry.name === "Honeymoon Fund"`) and apply conditional emphasis classes.
- [x] 1.3 Apply subtle emphasis to the Honeymoon Fund card: thicker border (e.g., `border-2`), `border-[var(--color-sage-dark)]`, and optionally a soft background tint (e.g., `bg-[var(--color-sage-light)]/10`) using design tokens from `global.css`.
- [x] 1.4 Run `npm run build` and local preview; capture screenshots of the Registry section on desktop (lg breakpoint) and mobile.

### [x] 2.0 Visual consistency and accessibility

#### 2.0 Tasks

- [x] 2.1 Verify the Honeymoon Fund card inherits focus styles from `global.css` (`a:focus-visible`); confirm it is keyboard-navigable (Tab to focus, Enter to activate).
- [x] 2.2 If hover scale or transition is added to the Honeymoon Fund card, add Tailwind `motion-reduce:transform-none` and `motion-reduce:transition-none` so it respects `prefers-reduced-motion`.
- [x] 2.3 Confirm emphasis uses border and/or background (not color alone) so it is perceivable without relying solely on color.
