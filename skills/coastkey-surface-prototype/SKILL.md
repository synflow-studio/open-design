---
name: coastkey-surface-prototype
description: |
  CoastKey sandbox prototype for search, catalog, detail, route, map/list, or
  reference-surface explorations. Generates a single self-contained HTML file
  from the active CoastKey Sandbox DESIGN.md and user-provided snippets only.
triggers:
  - "coastkey"
  - "coastkey prototype"
  - "coastkey surface"
  - "reference surface"
  - "map list"
  - "catalog"
od:
  mode: prototype
  platform: desktop
  scenario: product
  preview:
    type: html
    entry: index.html
  design_system:
    requires: true
    sections: [color, typography, layout, components]
  inputs:
    - name: surface
      type: enum
      values: [search-catalog, destination-detail, object-detail, day-pass, route, reference-surface]
      default: search-catalog
    - name: density
      type: enum
      values: [compact, balanced, editorial]
      default: balanced
---

# CoastKey Surface Prototype

Create a sandbox-only CoastKey prototype. The goal is to produce an inspectable
HTML artifact that can inform later implementation, not to write production
CoastKey code.

## Hard boundary

- Do not read, reference, mount, or modify `portfolio-cases`.
- Do not claim runtime accuracy unless the user provided the relevant facts in
  the prompt.
- Use only the active DESIGN.md, this skill, and user-provided snippets.
- If a production taxonomy detail is missing, use a visibly generic label and
  mention the assumption before the artifact.

## Workflow

1. Classify the requested surface:
   - `search-catalog`: filters, result list, selected item, map/reference pane.
   - `destination-detail`: destination overview, places, routes, amenities.
   - `object-detail`: beach club/object page, offers, amenities, reviews.
   - `day-pass`: availability, inclusions, constraints, price/action.
   - `route`: route summary, stops, timing, transport, notes.
   - `reference-surface`: inspection page for components, states, or taxonomy.
2. Choose a compact layout before writing:
   - Desktop search/catalog should use two or three panes.
   - Detail pages should use a header strip, primary facts, content sections,
     and a sticky action/summary area.
   - Reference surfaces should be dense, labeled, and comparison-friendly.
3. Write one self-contained `index.html` with inline CSS only.
4. Use semantic HTML and add `data-od-id` to every major region.
5. Use the active DESIGN.md palette and no external assets.
6. Include realistic sample content only when the user supplied no data.
   Keep it generic and clearly sandboxed.

## Quality checks

- No nested page-section cards.
- No marketing hero unless explicitly requested.
- No decorative blobs, dark stock imagery, or generic SaaS gradients.
- Filters, selected states, prices, availability, and route/detail metadata are
  clear at a glance.
- Mobile styles are included with stable dimensions for controls and cards.

## Output contract

Emit a single artifact:

```html
<artifact identifier="coastkey-surface-prototype" type="text/html" title="CoastKey Surface Prototype">
<!doctype html>
<html>...</html>
</artifact>
```

One short sentence before the artifact. Nothing after.
