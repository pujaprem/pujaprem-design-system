# Design System Agent Instructions

## Authority

This repository owns PujaPrem visual and interaction implementation truth. It does not own business/product strategy, devotional knowledge, Shopify domain data, or Hermes agent authority.

Before changing the system, read:

1. this file;
2. `README.md`;
3. `docs/DESIGN-SYSTEM.md`;
4. `docs/FLUID-SIZING-CONTRACT.md`;
5. `tokens/tokens.json`;
6. the current Store UX Architecture and Customer Journeys from `pujaprem-core` when the requested change affects a commerce flow.

## Current execution priority

- The PujaPrem Shopify theme is the active build priority.
- Design-system work should directly support finishing the real Shopify storefront before broader future productization or platform expansion.
- Do not create speculative component systems that distract from current storefront needs.

## Non-negotiable design direction

- modern Indian devotional minimalism
- warm editorial ecommerce
- calm first, informative second, commercial third
- Temple Ivory dominant surfaces
- PujaPrem Maroon as primary brand anchor
- Saffron used selectively, not as a page-wide background default
- Sacred Green reserved for trust/natural/success-adjacent cues
- excellent whitespace and photography
- **Poppins is the only named heading/display font**
- **Inter is the only named body/UI font**
- do not introduce Sora, Manrope, Noto Sans Devanagari, or any other third named PujaPrem font without explicit user approval
- no visual clutter, heavy offset shadows, rainbow brutalism, glassmorphism, or generic SaaS styling

## Fluid responsive laws

- Use bounded CSS `clamp()` as the default for visual values that should resize continuously across viewport widths.
- Prefer clamp-based tokens for typography, section spacing, gutters, gaps, and scalable component/media-container dimensions.
- Use media queries primarily for structural layout changes such as grid-column changes, navigation-to-drawer transitions, and stacking.
- Do not distort source imagery; resize/crop through responsive containers, `aspect-ratio`, `object-fit`, and appropriate image sources.
- Do not make fixed accessibility or semantic invariants fluid merely for consistency. Minimum touch targets, border thickness, focus-ring thickness, and icon stroke widths remain appropriately bounded/fixed.
- Preserve accessibility at 320px and 200% zoom.

## Interaction laws

- controls must show clear hover/focus/pressed/disabled states;
- tactile press feedback is allowed but subtle;
- do not move controls upward aggressively on hover;
- no hover-only content;
- `prefers-reduced-motion` must remove nonessential transforms/transitions;
- drawers/dialogs must support keyboard focus management in consuming applications.

## Accessibility laws

- do not weaken contrast, focus, touch targets, semantics, or reduced-motion behavior for aesthetics;
- do not rely on color alone for status;
- every interactive component requires a visible focus state;
- components must remain legible at 320px width and at zoom.

## Change discipline

When adding a component/pattern:

1. identify the UX use case in Core;
2. use semantic tokens before adding one-off values;
3. preserve the Poppins-heading / Inter-body typography contract;
4. use bounded `clamp()` for fluid sizing before adding breakpoint-only resize overrides;
5. define normal, hover, focus, active, disabled, loading, error/success states as applicable;
6. document structural breakpoint behavior;
7. add/update the public lab example;
8. keep machine-readable tokens synchronized with CSS tokens.

Do not copy theme-specific product content into this repository except as clearly marked demo fixtures.