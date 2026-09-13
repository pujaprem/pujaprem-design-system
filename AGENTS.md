# Design System Agent Instructions

## Authority

This repository owns PujaPrem visual and interaction implementation truth. It does not own business/product strategy, devotional knowledge, Shopify domain data, or Hermes agent authority.

Before changing the system, read:

1. this file;
2. `README.md`;
3. `docs/DESIGN-SYSTEM.md`;
4. `tokens/tokens.json`;
5. the current Store UX Architecture and Customer Journeys from `pujaprem-core` when the requested change affects a commerce flow.

## Non-negotiable design direction

- modern Indian devotional minimalism
- warm editorial ecommerce
- calm first, informative second, commercial third
- Temple Ivory dominant surfaces
- PujaPrem Maroon as primary brand anchor
- Saffron used selectively, not as a page-wide background default
- Sacred Green reserved for trust/natural/success-adjacent cues
- excellent whitespace and photography
- no visual clutter, heavy offset shadows, rainbow brutalism, glassmorphism, or generic SaaS styling

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
3. define normal, hover, focus, active, disabled, loading, error/success states as applicable;
4. document responsive behavior;
5. add/update the public lab example;
6. keep machine-readable tokens synchronized with CSS tokens.

Do not copy theme-specific product content into this repository except as clearly marked demo fixtures.