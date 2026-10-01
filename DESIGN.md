# VisitMade design system

This document records the design conventions implemented by the marketing site. It is descriptive, not a redesign brief, and it does not claim to cover the external visitor site or CRM.

## Experience principles

The implementation suggests these principles:

- **Connected, not complicated:** explain the relationship between visitor experience and operational workspace in plain language.
- **Place first:** lead with destination imagery and outcomes rather than technical features.
- **Credible demonstration:** label Visit Valechester, figures and interface examples as illustrative; avoid unverified customer claims.
- **Progressive detail:** move from proposition, through product areas and workflow, to demos and FAQ.
- **Accessible by default:** use semantic elements, keyboard operation, visible focus and reduced-motion support.

## Visual principles

- Calm, spacious layouts with dark green text, teal actions and pale green supporting surfaces.
- Large editorial headings paired with restrained body copy.
- Product concepts shown through lightweight interface illustrations rather than screenshots presented as real customer data.
- Rounded panels and subtle borders/shadows; animation is limited to small hover movement.
- Destination imagery supplies warmth while the CRM/reporting motifs remain structured and functional.

## Foundations

### Typography

- Headings: `Manrope`, with Arial and sans-serif fallbacks; generally weight 650 and tight negative tracking.
- Body and controls: `DM Sans`, with Arial and sans-serif fallbacks.
- Base size: 16px.
- Eyebrows: small, uppercase, letter-spaced teal labels.
- Fonts are imported from Google Fonts; the fallback stack must remain usable if the import fails.

### Core colours

| Token/use | Value |
| --- | --- |
| Ink / primary text and dark sections | `#12312f` |
| Teal / primary action and focus | `#007f78` |
| Teal hover | `#00665f` |
| Muted text | `#586966` |
| Divider/border | `#dce6e3` |
| Pale green surface | `#eef6f3` |
| White | `#ffffff` |
| Light teal on dark surfaces | `#8edbd0` |

Additional greens and status colours are local component shades. Maintain readable contrast and do not rely on colour alone to convey meaning.

### Shape and spacing

- The core radius token is 14px; buttons use 7px and smaller UI mock-ups vary between 4px and 12px.
- Main content is constrained to 1240px with responsive side gutters.
- Standard desktop sections use 108px vertical padding, reduced at narrower widths.
- Borders are generally 1px and shadows are subtle.

### Brand asset

`assets/visitmade-brand.png` is the approved original artwork. The current header/footer wordmark is exposed through a CSS background crop. Preserve the complete source asset and do not destructively edit it merely to change framing.

## Page and layout conventions

The current page sequence is:

1. sticky global navigation;
2. proposition-led hero with combined visitor-site/CRM illustration;
3. short platform scope strip;
4. tabbed product explanations;
5. connected-record workflow;
6. six-area package summary;
7. visitor and CRM demo links;
8. FAQ; and
9. compact footer.

Desktop layouts commonly use two-column grids. Cards use two or three columns where space allows. Content collapses progressively rather than introducing a separate mobile information architecture.

## Navigation and interaction

- The header is sticky and uses in-page anchors.
- Below 850px, navigation becomes a Menu button with `aria-expanded` and `aria-controls`; selecting a link or pressing Escape closes it.
- Product areas use a WAI-ARIA-style tablist. Click, Left/Right Arrow, Home and End are supported; active state controls `aria-selected`, focusability and panel visibility.
- URL fragments `#website`, `#crm` and `#reporting` select and scroll to the matching content.
- FAQs use native `<details>` and `<summary>` controls.
- Primary buttons are filled teal; secondary text links use a bottom border and directional arrow.

## Components

Established component patterns include:

- sticky header and responsive navigation;
- primary/small buttons and text links;
- eyebrow + heading + supporting copy section headers;
- product tabs and panels;
- feature lists with check marks;
- illustrative browser, CRM table and reporting cards;
- numbered workflow steps;
- package feature grid;
- image-led and workspace demo cards;
- FAQ disclosures; and
- footer navigation.

Reuse these patterns before adding a visually competing component. New interactive components need keyboard, focus, hover, active and reduced-motion behaviour.

## Forms

No form design exists. Do not infer a form system from buttons or mock tables. Before adding a form, define labels, help/error/success states, required-field conventions, keyboard flow, privacy wording, submission handling and spam protection.

## Responsive and mobile behaviour

Implemented breakpoints are:

- above 1450px: modest hero expansion;
- at or below 1100px: tighter gutters, navigation and two-column spacing;
- at or below 850px: collapsed menu and simplified grids/spacing;
- at or below 600px: single-column product, connection, demo and FAQ layouts; the package grid remains two columns; typography and illustration details reduce.

Mobile behaviour keeps touch targets and content order consistent. Changes should be checked at narrow mobile widths, around each breakpoint and on wide desktop screens; there is no automated visual test suite.

## Accessibility requirements

Current implemented measures include:

- semantic landmarks and headings;
- a skip link to `#main`;
- visible 3px focus outlines;
- keyboard-operable navigation and tabs;
- Escape-to-close for the mobile menu;
- accessible names and state attributes for interactive controls;
- native FAQ disclosures;
- descriptive image alternative text and hidden “opens in a new tab” text;
- `prefers-reduced-motion` support; and
- no essential interaction based only on hover.

These measures are not an accessibility audit or certification. Material changes should retain them and be checked with keyboard navigation, zoom/reflow and an automated accessibility scan; screen-reader testing is appropriate for interaction changes.

## Content and tone

- Confident, concise and destination-oriented.
- Outcome-led headings; body copy explains the operational value.
- Use “destination teams”, “visitors”, “businesses”, “members” and “partners” consistently.
- Keep claims specific enough to understand but avoid performance promises.
- Label fictional destinations, mock interfaces and figures as illustrative.
- State configuration or provider dependencies close to the relevant claim.
- Do not claim customer results, live integrations, pricing or compliance status without evidence.
- The VisitMade brand and each destination's own identity are distinct: public visitor sites should be described as configured around the destination's brand.

## Visitor-site and CRM considerations

The marketing treatment deliberately distinguishes two experiences:

- **Visitor site:** place-led imagery, discovery language and content categories such as stays, food and events.
- **CRM/admin:** structured records, statuses, totals, tables and next-action language.

They are tied together through common green tones, typography and the connected-record narrative. These are marketing representations only. The actual visitor-site and CRM design systems must be documented with their implementations rather than inferred from these mock-ups.
