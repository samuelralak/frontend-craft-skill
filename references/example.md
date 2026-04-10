# Craft in Action

This shows how the subtle layering principle translates to real decisions. Learn the thinking, not the code. Your values will differ — the approach won't.

---

## The Subtle Layering Mindset

Before looking at any example, internalize this: **you should barely notice the system working.**

When you look at Vercel's dashboard, you don't think "nice borders." You just understand the structure. When you look at Supabase, you don't think "good surface elevation." You just know what's above what. The craft is invisible — that's how you know it's working.

---

## Example: Dashboard with Sidebar and Dropdown

### The Surface Decisions

**Why so subtle?** Each elevation jump should be only a few percentage points of lightness. You can barely see the difference in isolation. But when surfaces stack, the hierarchy emerges. Whisper-quiet shifts that you feel rather than see.

**What NOT to do:** Don't make dramatic jumps between elevations. Don't use different hues for different levels. Keep the same hue, shift only lightness.

### The Border Decisions

**Why rgba, not solid colors?** Low opacity borders blend with their background. A low-opacity white border on a dark surface is barely there — it defines the edge without demanding attention. Solid hex borders look harsh in comparison.

**The test:** Look at your interface from arm's length. If borders are the first thing you notice, reduce opacity. If you can't find where regions end, increase slightly.

### The Sidebar Decision

**Why same background as canvas, not different?**

Many dashboards make the sidebar a different color. This fragments the visual space — "sidebar world" and "content world."

Better: Same background, subtle border separation. The sidebar is part of the app, not a separate region. Vercel does this. Supabase does this. The border is enough.

### The Dropdown Decision

**Why one level above the parent surface?**

The dropdown floats above the card it emerged from. If both share the same elevation, the dropdown blends into the card — you lose layering. One step up is just enough to feel "above" without being dramatic.

**Why stronger borders on overlays?** Overlays float in space and need slightly more definition. A touch more border opacity helps them feel contained without being harsh.

---

## Example: Form Controls

### Input Background Decision

**Why darker, not lighter?**

Inputs are "inset" — they receive content, they don't project it. A slightly darker background signals "type here" without needing heavy borders.

### Focus State Decision

**Why subtle focus states?**

Focus needs to be visible but not dramatic. A noticeable increase in border opacity is enough. Subtle-but-noticeable — the same principle as surfaces.

---

## Example: Expressive Landing Page

### The Domain Exploration

For a recipe app with an "inherited cookbook" feel:

**Domain:** Handwritten notes, dog-eared pages, flour-dusted margins, family annotations, seasonal produce, stained pages, kitchen warmth, generational knowledge.

**Color world:** Aged parchment (warm cream), terracotta (clay pots, brick ovens), herb green (fresh basil, rosemary), saffron gold (spice jars), dark walnut (wooden spoons, cutting boards).

**Signature:** Handwritten accent typography — like someone's grandmother penciled notes in the margins. Not everywhere, just annotations and personal touches.

**Defaults rejected:**
- Generic food photography grid → Asymmetric editorial layout with featured recipes at different scales
- Standard card shadows → Surface color shifts like layers of worn paper
- System/sans-serif fonts → Playfair Display (editorial), Source Serif 4 (readable body), Caveat (handwritten accents)

### The Execution

Typography choices directly from the domain: serif for the editorial cookbook feel, handwritten for the personal annotations. Colors drawn from the actual physical world of a kitchen, not from a "warm palette" generator. Layout breaks the grid intentionally — a featured recipe takes more space because it's featured, not because all cards are equal.

---

## Adapt to Context

Your product might need:
- Warmer hues (slight yellow/orange tint)
- Cooler hues (blue-gray base)
- Different lightness progression
- Light mode (principles invert — higher elevation = shadow, not lightness)

**The principle is constant:** barely different, still distinguishable. The values adapt to context.

---

## The Craft Check

Apply the squint test to your work:

1. Blur your eyes or step back
2. Can you still perceive hierarchy?
3. Is anything jumping out at you?
4. Can you tell where regions begin and end?

If hierarchy is visible and nothing is harsh — the subtle layering is working.
