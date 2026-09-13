# PujaPrem Design System

Design-system source for PujaPrem's modern Indian devotional commerce experience.

## Direction

**Modern Indian devotional minimalism with warm editorial ecommerce.**

The experience should feel:

- calm first
- informative second
- commercial third
- warm, trustworthy, contemporary, and accessible
- devotional without visual overload
- premium but not exclusive

The system intentionally avoids heavy Neo-Brutalist borders/shadows as the primary visual language. Tactile interaction ideas may be borrowed selectively where they improve feedback, but PujaPrem remains visually soft, modern, and editorial.

## Canonical upstream authority

Product/UX intent lives in `pujaprem/pujaprem-core`.

This repository owns visual and interaction implementation contracts:

- semantic color tokens
- typography
- spacing
- radii
- depth/shadows
- motion
- component anatomy
- states
- responsive behavior at component/pattern level
- accessibility behavior
- public design-system lab

## Current milestone

**v0.1 foundation**

- brand palette
- semantic token layer
- fluid type and spacing
- button/form/card primitives
- product, kit, guide, festival, and trust-card patterns
- basic loading/empty/error/success state language
- responsive public lab skeleton

## Files

- `docs/DESIGN-SYSTEM.md` — human-readable contract
- `tokens/tokens.json` — machine-readable design tokens
- `tokens/tokens.css` — shipping CSS custom properties
- `index.html` — public design-system lab
- `styles.css` — lab/component foundation styles

## Quality laws

- WCAG A/AA contrast on customer-facing text/controls
- visible keyboard focus
- no hover-only information
- honor `prefers-reduced-motion`
- touch-friendly controls
- no color-only state meaning
- no decorative motion that obstructs task completion
- no fake scarcity/urgency visual patterns

The design system must be consumable by both humans and coding agents without requiring visual guesswork.