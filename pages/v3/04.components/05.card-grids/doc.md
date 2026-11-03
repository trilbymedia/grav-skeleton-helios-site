---
title: Card Grids
taxonomy:
    category: docs
---

# Card Grids

Use the `doc-grid` shortcode to display multiple cards in a responsive grid layout.

## Basic Grid

By default, grids display cards in 2 columns on larger screens:

[doc-grid]
[doc-card title="Stars" icon="tabler/star.svg"]
Sirius, Vega, Betelgeuse
[/doc-card]
[doc-card title="Moons" icon="tabler/moon.svg"]
Io, Europa, Ganymede
[/doc-card]
[/doc-grid]

[raw]
```markdown
[doc-grid]
[doc-card title="Stars" icon="tabler/star.svg"]
Sirius, Vega, Betelgeuse
[/doc-card]
[doc-card title="Moons" icon="tabler/moon.svg"]
Io, Europa, Ganymede
[/doc-card]
[/doc-grid]
```
[/raw]

## Link Cards in Grid

Combine link cards with grids for navigation sections:

[doc-grid]
[doc-card title="Installation" icon="tabler/download.svg" link="/v3/getting-started/installation"]
Get started with installing and setting up your project.
[/doc-card]
[doc-card title="Configuration" icon="tabler/settings.svg" link="/v3/getting-started/configuration"]
Learn about all the configuration options available.
[/doc-card]
[doc-card title="Quick Start" icon="tabler/rocket.svg" link="/v3/getting-started/quick-start"]
Jump right in with our quick start guide.
[/doc-card]
[doc-card title="Theming" icon="tabler/palette.svg" link="/v3/guides/theming"]
Customize the look and feel of your documentation.
[/doc-card]
[/doc-grid]

## Custom Column Count

Control the number of columns with the `columns` parameter (1-4):

### Single Column

[doc-grid columns=1]
[doc-card title="Full Width Card"]
This card spans the entire width of the content area.
[/doc-card]
[/doc-grid]

[raw]
```markdown
[doc-grid columns=1]
[doc-card title="Full Width Card"]
This card spans the entire width.
[/doc-card]
[/doc-grid]
```
[/raw]

### Three Columns

[doc-grid columns=3]
[doc-card title="First"]
Column one
[/doc-card]
[doc-card title="Second"]
Column two
[/doc-card]
[doc-card title="Third"]
Column three
[/doc-card]
[/doc-grid]

[raw]
```markdown
[doc-grid columns=3]
[doc-card title="First"]Column one[/doc-card]
[doc-card title="Second"]Column two[/doc-card]
[doc-card title="Third"]Column three[/doc-card]
[/doc-grid]
```
[/raw]

### Four Columns

[doc-grid columns=4]
[doc-card title="One" icon="tabler/number-1.svg"][/doc-card]
[doc-card title="Two" icon="tabler/number-2.svg"][/doc-card]
[doc-card title="Three" icon="tabler/number-3.svg"][/doc-card]
[doc-card title="Four" icon="tabler/number-4.svg"][/doc-card]
[/doc-grid]

## Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `columns` | No       | `2`     | Number of columns (1-4). Responsive on smaller screens. |

## Responsive Behavior

Grids automatically adjust for different screen sizes:

- **Mobile**: Always single column
- **Tablet**: 2 columns (for 2+ column grids)
- **Desktop**: Full column count
