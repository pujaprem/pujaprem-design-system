# PujaPrem Fluid Sizing Contract

**Status:** Active design-system contract  
**Applies to:** PujaPrem Shopify theme and all future PujaPrem customer-facing UI

## 1. Responsive strategy

PujaPrem uses a **fluid-first responsive system**.

When a visual value should grow or shrink continuously with viewport size, the default technique is CSS `clamp(min, preferred, max)` rather than a chain of breakpoint-specific fixed values.

Use `clamp()` for fluid values such as:

- heading and body typography sizes;
- section padding and vertical rhythm;
- page gutters;
- gaps between cards and layout regions;
- card and media-container sizing where smooth scaling is desired;
- hero content sizing;
- selected widths, min-heights, and max-widths that should interpolate across viewport sizes.

Example:

```css
font-size: clamp(1rem, 0.9rem + 0.5vw, 1.25rem);
padding-inline: clamp(1rem, 0.5rem + 2vw, 2rem);
gap: clamp(0.75rem, 0.5rem + 1vw, 1.5rem);
```

Each fluid value must have meaningful lower and upper bounds. Prefer `rem`-based bounds and use viewport-relative math in the preferred middle term.

## 2. Breakpoints are structural

Media queries are still required when the layout mode itself changes.

Use breakpoints for changes such as:

- navigation becoming a drawer;
- 4-column grids becoming 2-column or 1-column layouts;
- PDP columns stacking;
- desktop/mobile art-direction swaps;
- control groups changing composition due to available space.

Do not create a breakpoint solely to step a font, gap, or section padding through several nearby pixel values when one bounded `clamp()` can represent the intended scale.

## 3. Image and media resizing

Fluid layout must never distort imagery.

- Preserve intrinsic image proportions.
- Prefer `width: 100%` and `height: auto` when no crop is required.
- Use `aspect-ratio`, `object-fit`, and `object-position` for intentional crop containers.
- Apply `clamp()` to media-container dimensions when useful rather than stretching source pixels independently.
- Consuming Shopify code should use responsive image `srcset`/`sizes` behavior and intentional LCP handling.

## 4. Do not make invariants fluid

Do not use `clamp()` where a fixed invariant is safer or more semantically correct.

Typical invariants include:

- semantic 1px borders;
- icon stroke widths;
- focus-ring thickness;
- minimum accessible touch/control target sizes;
- platform-defined dimensions;
- exact aspect-ratio relationships.

The accessibility floor always wins over visual scaling.

## 5. Typography

The canonical PujaPrem font pairing remains:

- **Poppins** — headings/display;
- **Inter** — body/UI.

Typography scale should use bounded `clamp()` tokens. No third named PujaPrem brand/UI font role is introduced by responsive behavior.

## 6. Token rule

Reusable fluid values belong in semantic tokens instead of being re-invented inside individual components. New responsive values should prefer the pattern:

`minimum rem value → fluid preferred expression → maximum rem value`.

The existing `--pp-text-*`, larger `--pp-space-*`, and `--pp-gutter` tokens are the model for this approach.

## 7. Acceptance rule

A component is responsive-ready when:

- routine scaling is fluid and bounded;
- structural changes happen at intentional breakpoints;
- no source image is distorted;
- layout works at 320px and large desktop widths;
- content remains usable at 200% zoom;
- accessible control minimums are preserved;
- the result avoids breakpoint sprawl.

The operating principle is: **fluid sizing handles resizing; breakpoints handle structural change.**
