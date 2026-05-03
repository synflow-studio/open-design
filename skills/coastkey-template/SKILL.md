---
name: coastkey-template
description: |
  Fast CoastKey sandbox template mode. Produces a stable HTML layout by filling
  predefined CoastKey-style slots instead of designing from scratch.
triggers:
  - "coastkey template"
  - "fast coastkey"
  - "coastkey quick"
od:
  mode: template
  platform: desktop
  scenario: product
  preview:
    type: html
    entry: index.html
  design_system:
    requires: true
    sections: [color, typography, layout, components]
  inputs:
    - name: template
      type: enum
      values: [catalog-shell, detail-shell, reference-shell]
      default: catalog-shell
    - name: title
      type: string
      required: true
---

# CoastKey Template

Use this when speed and consistency matter more than free-form generation.
Create a single HTML artifact by filling a predefined layout shell.

## Boundary

This is a sandbox template. Do not inspect or modify `portfolio-cases`. Use only
the active CoastKey Sandbox DESIGN.md and content supplied in the prompt.

## Template shells

### catalog-shell

- Top toolbar with search, filter groups, and view mode.
- Left or center result list with repeated items.
- Right reference/map pane with selected item facts.
- Sticky bottom or side action summary.

### detail-shell

- Compact title/header area.
- Primary facts row.
- Section items for overview, amenities, availability, policy, reviews, and
  related offers.
- Sticky booking/action summary.

### reference-shell

- Dense index of components, states, filters, labels, or taxonomy items.
- Comparison columns and status badges.
- Notes area for assumptions and unresolved questions.

## Output rules

- Keep the layout stable and reusable.
- Prefer real controls over explanatory text.
- Use explicit sandbox labels when sample content is invented.
- Do not create a hero page.
- Include responsive CSS.

## Output contract

Emit a single artifact:

```html
<artifact identifier="coastkey-template" type="text/html" title="CoastKey Template">
<!doctype html>
<html>...</html>
</artifact>
```

One short sentence before the artifact. Nothing after.
