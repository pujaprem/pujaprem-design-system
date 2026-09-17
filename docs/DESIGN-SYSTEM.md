# PujaPrem Design System v0.1

**Status:** Foundation draft  
**Visual north star:** Modern Indian devotional minimalism with warm editorial ecommerce

## 1. Purpose

Create a reusable visual and interaction system for the PujaPrem storefront, Guides, Festival Hubs, Journal, account/help surfaces, and future customer-facing products.

The system must feel distinctly devotional and Indian through color, photography, language, rhythm, and subtle motif — not through visual clutter or generic religious ornament.

## 2. Experience principles

### Warm
Temple Ivory replaces stark white as the default environmental surface. Photography, copy, and spacing should feel hospitable.

### Calm
Do not make every section compete for attention. Use hierarchy and whitespace before decoration.

### Clear
The customer must immediately understand the next action, especially on kit/product/cart surfaces.

### Trustworthy
Use real information, legible hierarchy, honest status, and restrained promotional treatment.

### Modern Indian
Use contemporary layout, typography, and editorial composition. Sacred geometry/pattern may appear as subtle texture, never as visual wallpaper.

### Tactile, not theatrical
Buttons, cards, drawers, and selectors should feel responsive. Motion should communicate state rather than show off.

## 3. Core palette

### Brand

- **PujaPrem Maroon** — `#5A1832`
  - primary buttons
  - wordmark/logo
  - key headings or dark branded surfaces
  - selected navigation emphasis

- **Prem Saffron** — `#F59E0B`
  - badges
  - festival accents
  - selected/highlight states
  - small decorative emphasis

- **Temple Ivory** — `#FFF8E7`
  - default page background
  - warm negative space
  - packaging-inspired surfaces

- **Deep Charcoal** — `#201A17`
  - primary text
  - strong contrast
  - dark footer/surfaces

- **Sacred Green** — `#2E6E50`
  - trust/natural cues
  - success-adjacent semantic support
  - checklist/guide accents

- **Clay** — `#A33A17`
  - warm secondary accent
  - gifting/festival/editorial emphasis

### Neutral semantic expansion

The shipping token layer also defines warm neutral surfaces/borders/muted text so components do not overuse brand colors.

## 4. Color usage rules

- Temple Ivory is the dominant light-mode canvas.
- Maroon is the main brand anchor, not a background for every section.
- Saffron should feel special. Do not use it for long text blocks or every CTA.
- Green is not a second primary brand color. It communicates trust/natural/success contexts.
- Clay is supporting, not competing.
- Error/warning/success semantic colors remain distinguishable from decorative brand accents.

## 5. Typography

PujaPrem uses exactly two named design-system font families.

### Headings / display
**Poppins** is the required heading family.

Use Poppins for:
- H1–H6
- product and Puja Kit titles
- campaign and promotional headings
- card titles
- navigation emphasis where a heading-style treatment is intended
- large display typography

### Body / UI
**Inter** is the required body and interface family.

Use Inter for:
- paragraphs
- product details
- descriptions
- forms and inputs
- tables and checklists
- buttons and utility labels unless a heading treatment is explicitly required
- account, support, cart, and other UI text

### Typography lock

- Do not introduce Sora, Manrope, Noto Sans Devanagari, or another named brand/UI font into PujaPrem.
- The canonical font pairing is **Poppins for headings + Inter for body/UI**.
- Browser/platform glyph fallback may occur only where a character is unavailable in the named family; that fallback is not a third PujaPrem design-system font role.
- The production theme must load Poppins and Inter efficiently and avoid duplicate or unused font payloads.

### Type scale

Use fluid `clamp()`-based sizing. The system exposes:

- `--pp-text-xs`
- `--pp-text-sm`
- `--pp-text-md`
- `--pp-text-lg`
- `--pp-text-xl`
- `--pp-text-2xl`
- `--pp-text-3xl`
- `--pp-text-display`

Long editorial content should preserve comfortable line length and rhythm rather than using oversized marketing type everywhere.

## 6. Spacing

4px base rhythm:

- 4
- 8
- 12
- 16
- 24
- 32
- 48
- 64
- 96

CSS uses fluid spacing tokens for larger values so layouts breathe across mobile/desktop without breakpoint sprawl.

## 7. Radius

- Small: 6px
- Medium: 10px
- Large: 16px
- Extra large / hero media: 24px where appropriate
- Pills reserved for badges, chips, compact filters, or status tags

Avoid turning every surface into a pill.

## 8. Depth and borders

PujaPrem depth is soft and editorial.

- subtle warm border
- low-elevation shadow for cards/dropdowns
- stronger overlay shadow only for dialogs/drawers
- no 6–10px hard offset Neo-Brutalist shadows
- no glossy inset effects

Cards should still read clearly when shadows are removed (forced colors / print / reduced visual styling).

## 9. Motion

### Timing

- fast feedback: ~120–160ms
- standard transition: ~180–240ms
- drawer/sheet: ~220–300ms

### Allowed

- button press/compression
- selected-card feedback
- menu/drawer open/close
- add-to-cart confirmation
- accordion disclosure
- progress/result feedback

### Avoid

- hover float/lift as the default card behavior
- parallax
- autoplay ornamental motion
- large festival animations that block commerce

### Reduced motion

Under `prefers-reduced-motion: reduce`, remove nonessential movement and keep state changes immediate/low-motion.

## 10. Core components

### Buttons

Variants:
- Primary — Maroon
- Secondary — Ivory/neutral outlined
- Quiet/text
- Destructive

States:
- default
- hover
- focus-visible
- active
- disabled
- loading

### Inputs

- text
- search
- select
- textarea
- checkbox
- radio
- quantity stepper

Requirements:
- visible label
- help/error text
- strong focus state
- minimum touch target

### Cards

Core card anatomies:
- Product Card
- Puja Kit Card
- Ritual/Occasion Card
- Festival Card
- Guide Card
- Checklist Card
- Journal Card
- Trust Card
- Gifting Card

Card visuals should be reusable across background contexts without relying on one fixed page color.

### Commerce blocks

- price block
- delivery block
- rating/review summary
- variant selector
- quantity selector
- Add to Cart
- sticky mobile purchase bar
- cart line item
- cart drawer
- kit comparison
- included-vs-fresh table

### Content blocks

- Guide table of contents
- checklist row
- FAQ accordion
- callout/note
- related content module
- editorial image/caption
- contextual help trigger/panel

## 11. Product card pattern

Minimum information:

- media
- product/kit name
- short category/intent context
- price
- optional rating only when real
- clear action or link

Do not overload cards with shipping, badges, discount math, product descriptions, and multiple CTAs simultaneously.

## 12. Puja Kit card pattern

Differentiate kits from normal products.

Recommended content:

- ritual/occasion
- kit name/level
- product image
- included-item count
- price
- compact “what it helps with” line
- CTA

Fresh-item exclusions belong on the PDP/Guide, not squeezed into every grid card.

## 13. Guide and checklist patterns

Guide cards should visually communicate practical help rather than product promotion.

Checklist pattern must support:

- item name
- included-in-kit status
- arrange-fresh status
- future interactive checked state

Status may not rely on color alone.

## 14. Festival pattern

Festival cards may use Saffron/Clay more strongly than normal commerce cards, but preserve the PujaPrem hierarchy and avoid generic celebratory clutter.

## 15. Contextual Help pattern

The `Need Help?` trigger is persistent but quiet.

The panel should:

- inherit page context;
- present likely questions first;
- distinguish self-service answers from contact/escalation;
- use approved knowledge only;
- work as a structured FAQ shell before AI is introduced.

## 16. Responsive behavior

### Mobile

- 320px baseline support
- large touch targets
- 1-column primary reading flow
- horizontal card scrollers only when they improve browsing and remain accessible
- sticky purchase bar permitted on PDPs
- drawers/sheets use most of viewport but preserve close/focus affordance

### Tablet

- 2-column editorial/product compositions where useful
- do not assume pointer hover

### Desktop

- larger image/typographic hierarchy
- comfortable 3–4 card commerce grids
- editorial whitespace instead of maximum density

## 17. State language

Every relevant component should have:

- default
- hover where pointer exists
- focus-visible
- active/selected
- disabled
- loading
- empty where applicable
- error
- success/result

Examples in the public lab should make these inspectable.

## 18. Accessibility

Foundation requirements:

- WCAG A/AA contrast for production text/controls
- visible focus ring independent of hover
- keyboard-operable examples
- no color-only status
- readable 200% zoom behavior
- minimum practical touch targets (~44px for primary controls)
- semantic HTML in consuming applications
- reduced motion
- forced-colors survivability

## 19. Photography direction

- warm natural lighting
- real product texture
- clean devotional arrangements
- show scale and contents clearly
- avoid overcrowded altar imagery as default commerce photography
- use hands/people only when they add authentic context
- no generic deity clipart as a substitute for product photography

## 20. Content density

Production pages should be less dense than a presentation mockup.

Use progressive disclosure for:

- detailed kit contents
- long FAQs
- educational depth

Do not hide critical purchase facts such as price, quantity, included/excluded items, or delivery behind disclosure controls.

## 21. Machine-readable contract

`tokens/tokens.json` is the canonical token representation for agents/tools. `tokens/tokens.css` is the CSS implementation. When values change, both must change in the same PR.

The typography token contract must always resolve to Poppins for display/headings and Inter for body/UI. A future change to either family requires explicit user approval and a synchronized update to this document plus both token files.

## 22. v0.1 acceptance criteria

- palette encoded as semantic tokens
- Poppins locked as the heading/display family
- Inter locked as the body/UI family
- no third named PujaPrem design-system font role
- fluid type/spacing encoded
- focus/motion/accessibility tokens present
- primary/secondary button styles
- form/search style
- product, kit, guide, festival, trust card examples
- state examples
- responsive public lab
- no dependency on Shopify data/runtime
- no conflict with Store UX Architecture v0.1
