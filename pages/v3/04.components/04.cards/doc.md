---
title: Cards
taxonomy:
    category: docs
---

# Cards

Cards display content in a box matching the documentation theme's styles. Use them to highlight related information or group content visually.

## Basic Card

A simple card with a title and content:

[doc-card title="Moons"]
Io, Europa, Ganymede, and Callisto are the four largest moons of Jupiter.
[/doc-card]

[raw]
```markdown
[doc-card title="Moons"]
Io, Europa, Ganymede, and Callisto are the four largest moons of Jupiter.
[/doc-card]
```
[/raw]

## Card with Icon

Add an icon to make cards more visually distinctive:

[doc-card title="Stars" icon="tabler/star.svg"]
Sirius, Vega, and Betelgeuse are some of the brightest stars visible from Earth.
[/doc-card]

[raw]
```markdown
[doc-card title="Stars" icon="tabler/star.svg"]
Sirius, Vega, and Betelgeuse are some of the brightest stars visible from Earth.
[/doc-card]
```
[/raw]

## Link Cards

Add a `link` parameter to make the entire card clickable. A subtle arrow indicator appears to show it's interactive:

[doc-card title="Getting Started" icon="tabler/rocket.svg" link="/v3/getting-started/installation"]
Learn how to install and configure your documentation site.
[/doc-card]

[doc-card title="Configuration Guide" link="/v3/getting-started/configuration"]
Explore all the configuration options available.
[/doc-card]

[raw]
```markdown
[doc-card title="Getting Started" icon="tabler/rocket.svg" link="/v3/getting-started/installation"]
Learn how to install and configure your documentation site.
[/doc-card]

[doc-card title="Configuration Guide" link="/v3/getting-started/configuration"]
Explore all the configuration options available.
[/doc-card]
```
[/raw]

## Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `title`   | Yes      | —       | The card heading |
| `icon`    | No       | —       | Icon path (e.g., `tabler/star.svg`) |
| `link`    | No       | —       | URL to link to (makes entire card clickable) |

## Markdown Support

Cards support full markdown in their content:

[doc-card title="Rich Content" icon="tabler/file-text.svg"]
You can use **bold**, *italic*, and `inline code` in cards.

- Bullet points work
- Multiple items supported

Even [links](/) are supported inside card content.
[/doc-card]
