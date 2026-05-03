# CoastKey Sandbox

> Category: Synflow
> CoastKey-inspired sandbox system for Open Design prototypes. This is not a
> direct mirror of the production repository.

## Visual Theme & Atmosphere
Quiet coastal utility with editorial restraint. The interface should feel like
a premium travel and venue operations product: clear, scan-friendly, warm, and
commercially useful without looking like a generic booking template.

## Color Palette & Roles
- **Background:** `#F7F5F0` — warm page canvas.
- **Foreground:** `#17211F` — primary text.
- **Surface:** `#FFFFFF` — cards, panels, menus, and sheets.
- **Muted:** `#64706B` — secondary text and metadata.
- **Border:** `#D9D6CD` — low-contrast structural dividers.
- **Accent:** `#0E6F68` — primary action, active state, selected map/list item.
- **Accent Soft:** `#D7ECE7` — subtle selected backgrounds.
- **Commerce:** `#A45A2A` — price, availability, or offer emphasis.
- **Success:** `#287A4F`, **Warn:** `#B7791F`, **Danger:** `#B84040`.

Use the accent sparingly. A screen may combine the teal accent with the commerce
color, but neither should dominate the page.

## Typography Rules
- **Display / headings:** `Inter`, `Avenir Next`, `-apple-system`, `system-ui`,
  sans-serif; weights 600-700.
- **Body:** `Inter`, `-apple-system`, `system-ui`, sans-serif; weight 400.
- **Metadata / numerics:** `ui-monospace`, `SFMono-Regular`, monospace for
  compact availability, ETA, distance, and price metadata.
- Scale: 12, 13, 14, 16, 20, 24, 32, 44.
- Line-height: 1.45 body, 1.18 headings.
- Letter spacing: 0. Do not use compressed or negative tracking.

## Component Stylings
- **Buttons:** 8px radius or less. Primary uses accent fill and white text.
  Secondary uses surface fill, border, and foreground text.
- **Cards:** 8px radius, 1px border, surface fill. Avoid nested cards.
- **Filters:** compact segmented controls, checkboxes, and chips. Chips are
  functional controls, not decoration.
- **Map/list items:** selected state uses Accent Soft plus a left or top accent
  mark. Do not rely on color alone; add label or icon state.
- **Offers/prices:** price and availability can use Commerce, but only in small
  high-signal areas.
- **Imagery:** use explicit image placeholders or user-provided assets. Avoid
  dark blurred stock-style imagery.

## Layout Principles
- Operational screens should be dense but calm: search/filter controls, results,
  map/reference panel, and selected-item details must be visible without a
  marketing hero.
- Use full-width bands or unframed app layouts. Cards are for repeated items,
  not for wrapping whole page sections.
- Keep common CoastKey surfaces scannable: destination, beach/object, day pass,
  route, amenity, review, offer, and availability.
- Desktop layouts can use two or three panes. Mobile layouts should collapse to
  tabs or stacked sections with persistent primary action.

## Depth & Elevation
Default to flat surfaces. Use a single soft shadow only for popovers, sheets,
menus, or active map overlays. Avoid glassmorphism, heavy gradients, decorative
orbs, and bokeh backgrounds.

## Do's and Don'ts
- Do use real labels for coastal commerce: area, distance, opening window,
  included amenities, cancellation, route stops, and day-pass constraints.
- Do make filters and selected states explicit.
- Do keep repeated detail units as section items unless a card family is
  explicitly part of the brief.
- Do not invent production taxonomy.
- Do not imply access to live CoastKey runtime data.
- Do not read or modify `portfolio-cases`; this system is for sandbox output.
- Do not create a marketing landing page unless the brief explicitly asks for
  one.

## Responsive Behavior
- Desktop: split-pane layouts are preferred for search/catalog/map and reference
  surfaces.
- Tablet: keep filters reachable and collapse secondary reference panels below
  the main content.
- Phone: use compact sticky actions, tabs, and section accordions. Keep text
  inside controls readable without viewport-based font scaling.

## Agent Prompt Guide
Treat every output as a sandbox artifact for review, not production code. Ask
for missing taxonomy or data when it materially affects the surface. Prefer
small, inspectable prototypes that can inform a later handoff into the real
CoastKey implementation workflow.
