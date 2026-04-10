# Core Craft Principles

These apply regardless of design direction. This is the quality floor.

---

## Surface & Token Architecture

Professional interfaces don't pick colors randomly — they build systems.

### The Primitive Foundation

Every color in your interface should trace back to a small set of primitives:

- **Foreground** — text colors (primary, secondary, muted)
- **Background** — surface colors (base, elevated, overlay)
- **Border** — edge colors (default, subtle, strong)
- **Brand** — your primary accent
- **Semantic** — functional colors (destructive, warning, success)

Don't invent new colors. Map everything to these primitives.

### Surface Elevation Hierarchy

Surfaces stack. A dropdown sits above a card which sits above the page. Build a numbered system:

```
Level 0: Base background (the app canvas)
Level 1: Cards, panels (same visual plane as base)
Level 2: Dropdowns, popovers (floating above)
Level 3: Nested dropdowns, stacked overlays
Level 4: Highest elevation (rare)
```

In dark mode, higher elevation = slightly lighter. In light mode, higher elevation = slightly lighter or uses shadow.

### The Subtlety Principle

Study Vercel, Supabase, Linear — their surfaces are **barely different** but still distinguishable. Their borders are **light but not invisible**.

**For surfaces:** The difference between elevation levels should be subtle — a few percentage points of lightness. In dark mode, surface-100 might be 7% lighter than base, surface-200 might be 9%, surface-300 might be 12%. You can barely see it, but you feel it.

**For borders:** Use low opacity (0.05-0.12 alpha for dark mode, slightly higher for light). The border should disappear when you're not looking for it, but be findable when you need structure.

**The test:** Squint at your interface. You should still perceive hierarchy. No single border or surface should jump out. If borders are the first thing you notice, they're too strong. If you can't find where regions end, they're too subtle.

**Common AI mistakes to avoid:**
- Borders that are too visible (1px solid gray instead of subtle rgba)
- Surface jumps that are too dramatic
- Using different hues for different surfaces
- Harsh dividers where subtle borders would do

### Text Hierarchy via Tokens

Build four levels:

- **Primary** — default text, highest contrast
- **Secondary** — supporting text, slightly muted
- **Tertiary** — metadata, timestamps, less important
- **Muted** — disabled, placeholder, lowest contrast

### Border Progression

Build a scale:

- **Default** — standard borders
- **Subtle/Muted** — softer separation
- **Strong** — emphasis, hover states
- **Stronger** — maximum emphasis, focus rings

### Dedicated Control Tokens

Form controls need dedicated tokens:

- **Control background** — often different from surface backgrounds
- **Control border** — needs to feel interactive
- **Control focus** — clear focus indication

### Alternative Backgrounds for Depth

Beyond shadows, use contrasting backgrounds to create depth. An "alternative" or "inset" background makes content feel recessed. Useful for:

- Empty states in data grids
- Code blocks
- Inset panels
- Visual grouping without borders

---

## Spacing System

Pick a base unit (4px recommended) and use multiples throughout.

Build a scale for different contexts:
- Micro spacing (icon gaps, tight element pairs)
- Component spacing (within buttons, inputs, cards)
- Section spacing (between related groups)
- Major separation (between distinct sections)

## Symmetrical Padding

TLBR must match. If top padding is 16px, left/bottom/right must also be 16px. Exception: when content naturally creates visual balance.

```css
/* Good */
padding: 16px;
padding: 12px 16px; /* Only when horizontal needs more room */

/* Bad */
padding: 24px 16px 12px 16px;
```

## Border Radius Consistency

Sharper corners feel technical, rounder corners feel friendly. Pick a scale that fits your product's personality.

Small radius for inputs and buttons, medium for cards, large for modals. Don't mix sharp and soft randomly.

## Depth & Elevation Strategy

Choose ONE and commit:

**Borders-only (flat)** — Clean, technical, dense. Linear, Raycast.

```css
--border: rgba(0, 0, 0, 0.08);
--border-subtle: rgba(0, 0, 0, 0.05);
border: 0.5px solid var(--border);
```

**Subtle single shadows** — Soft lift without complexity.

```css
--shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
```

**Layered shadows** — Rich, premium, dimensional. Stripe, Mercury.

```css
--shadow-layered:
  0 0 0 0.5px rgba(0, 0, 0, 0.05),
  0 1px 2px rgba(0, 0, 0, 0.04),
  0 2px 4px rgba(0, 0, 0, 0.03),
  0 4px 8px rgba(0, 0, 0, 0.02);
```

**Surface color shifts** — Background tints without any shadows.

## Card Layouts

A metric card doesn't have to look like a plan card. Design each card's internal structure for its content — keep surface treatment consistent.

## Isolated Controls

**Never use native form elements for styled UI.** Build custom:

- Custom select: trigger button + positioned dropdown menu
- Custom date picker: input + calendar popover
- Custom checkbox/radio: styled div with state management

Custom select triggers must use `display: inline-flex` with `white-space: nowrap`.

## Typography Hierarchy

- **Headlines** — heavier weight, tighter letter-spacing
- **Body** — comfortable weight for readability
- **Labels/UI** — medium weight, smaller sizes
- **Data** — monospace, `tabular-nums` for alignment

## Monospace for Data

Numbers, IDs, codes, timestamps belong in monospace. Use `tabular-nums` for columnar alignment.

## Iconography

Icons clarify, not decorate. Choose one set. Give standalone icons subtle background containers.

## Animation

Fast and functional. Micro-interactions ~150ms. Larger transitions 200-250ms. Use deceleration easing. Avoid spring/bounce in professional interfaces.

## Contrast Hierarchy

Build four levels: foreground (primary) → secondary → muted → faint. Use all four consistently.

## Color Carries Meaning

Gray builds structure. Color communicates. Unmotivated color is noise.

## Navigation Context

Include navigation showing where you are. Breadcrumbs, page title, active nav state, user context.

Sidebars: same background as main content, border for separation.

## Dark Mode

Borders over shadows. Adjust semantic colors (desaturate slightly). Same structure, different values.
