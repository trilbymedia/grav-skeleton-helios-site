---
title: Buttons
taxonomy:
    category: docs
---

# Buttons

Styled buttons for calls-to-action, navigation links, and interactive triggers. Buttons support color variants, sizes, icons, and can render as links or button elements.

## Basic Button

A default primary filled button with a link:

[doc-button label="Get Started" link="/v3/getting-started/installation"]

[raw]
```markdown
[doc-button label="Get Started" link="/v3/getting-started/installation"]
```
[/raw]

## Bordered Style

Use `style="bordered"` for an outlined variant:

[doc-button label="Learn More" link="/v3/getting-started" style="bordered"]

[raw]
```markdown
[doc-button label="Learn More" link="/v3/getting-started" style="bordered"]
```
[/raw]

## Color Variants

Buttons support seven color options. The named colors (blue, green, yellow, red, purple) use the same Tailwind shades as the API method badges for visual consistency.

### Filled

[doc-button label="Default" link="#" classes="mr-2"]
[doc-button label="Blue" link="#" color="blue" classes="mr-2"]
[doc-button label="Green" link="#" color="green" classes="mr-2"]
[doc-button label="Yellow" link="#" color="yellow" classes="mr-2"]
[doc-button label="Red" link="#" color="red" classes="mr-2"]
[doc-button label="Purple" link="#" color="purple" classes="mr-2"]
[doc-button label="Plain" link="#" color="plain"]

[raw]
```markdown
[doc-button label="Default" link="#"]
[doc-button label="Blue" link="#" color="blue"]
[doc-button label="Green" link="#" color="green"]
[doc-button label="Yellow" link="#" color="yellow"]
[doc-button label="Red" link="#" color="red"]
[doc-button label="Purple" link="#" color="purple"]
[doc-button label="Plain" link="#" color="plain"]
```
[/raw]

### Bordered

[doc-button label="Default" link="#" style="bordered" classes="mr-2"]
[doc-button label="Blue" link="#" style="bordered" color="blue" classes="mr-2"]
[doc-button label="Green" link="#" style="bordered" color="green" classes="mr-2"]
[doc-button label="Yellow" link="#" style="bordered" color="yellow" classes="mr-2"]
[doc-button label="Red" link="#" style="bordered" color="red" classes="mr-2"]
[doc-button label="Purple" link="#" style="bordered" color="purple" classes="mr-2"]
[doc-button label="Plain" link="#" style="bordered" color="plain"]

[raw]
```markdown
[doc-button label="Default" link="#" style="bordered"]
[doc-button label="Blue" link="#" style="bordered" color="blue"]
[doc-button label="Green" link="#" style="bordered" color="green"]
[doc-button label="Yellow" link="#" style="bordered" color="yellow"]
[doc-button label="Red" link="#" style="bordered" color="red"]
[doc-button label="Purple" link="#" style="bordered" color="purple"]
[doc-button label="Plain" link="#" style="bordered" color="plain"]
```
[/raw]

## Sizes

Four sizes are available: `sm`, `default`, `lg`, and `xl`.

[doc-button label="Small" link="#" size="sm" classes="mr-2"]
[doc-button label="Default" link="#" classes="mr-2"]
[doc-button label="Large" link="#" size="lg" classes="mr-2"]
[doc-button label="Extra Large" link="#" size="xl"]

[raw]
```markdown
[doc-button label="Small" link="#" size="sm"]
[doc-button label="Default" link="#"]
[doc-button label="Large" link="#" size="lg"]
[doc-button label="Extra Large" link="#" size="xl"]
```
[/raw]

## Icons

Add icons to the left, right, or both sides of the button text:

[doc-button label="Star" link="#" icon-left="tabler/star.svg" classes="mr-2"]
[doc-button label="Continue" link="#" icon-right="tabler/arrow-right.svg" classes="mr-2"]
[doc-button label="Download" link="#" icon-left="tabler/download.svg" icon-right="tabler/arrow-down.svg"]

[raw]
```markdown
[doc-button label="Star" link="#" icon-left="tabler/star.svg"]
[doc-button label="Continue" link="#" icon-right="tabler/arrow-right.svg"]
[doc-button label="Download" link="#" icon-left="tabler/download.svg" icon-right="tabler/arrow-down.svg"]
```
[/raw]

Icons also scale with the button size:

[doc-button label="Large with Icon" link="#" size="lg" icon-left="tabler/rocket.svg"]

[raw]
```markdown
[doc-button label="Large with Icon" link="#" size="lg" icon-left="tabler/rocket.svg"]
```
[/raw]

## New Tab

Use `new-tab=true` to open the link in a new browser tab:

[doc-button label="Open External" link="https://getgrav.org" new-tab=true icon-right="tabler/external-link.svg"]

[raw]
```markdown
[doc-button label="Open External" link="https://getgrav.org" new-tab=true icon-right="tabler/external-link.svg"]
```
[/raw]

## Centering

Wrap the button in a centered flex container with `center=true`:

[doc-button label="Centered Button" link="#" center=true]

[raw]
```markdown
[doc-button label="Centered Button" link="#" center=true]
```
[/raw]

## Data Attributes

Add custom data attributes for JavaScript interactivity:

[doc-button label="Trigger Action" data-attr="action" data-val="toggle-modal"]

[raw]
```markdown
[doc-button label="Trigger Action" data-attr="action" data-val="toggle-modal"]
```
[/raw]

When no `link` is provided, the button renders as a `<button>` element instead of an `<a>` tag, which is ideal for JavaScript-triggered actions.

## Custom Classes

Use the `classes` parameter to add extra CSS utility classes:

[doc-button label="With Margin" link="#" classes="mt-4 mb-4"]

[raw]
```markdown
[doc-button label="With Margin" link="#" classes="mt-4 mb-4"]
```
[/raw]

## Parameters

| Parameter    | Required | Default   | Description |
|--------------|----------|-----------|-------------|
| `label`      | Yes      | —         | Button text |
| `link`       | No       | —         | URL href (renders as `<a>` if set, `<button>` if not) |
| `style`      | No       | `default` | `default` (filled) or `bordered` (outline) |
| `color`      | No       | `default` | `default`, `blue`, `green`, `yellow`, `red`, `purple`, `plain` |
| `size`       | No       | `default` | `sm`, `default`, `lg`, `xl` |
| `icon-left`  | No       | —         | Icon path for left icon (e.g., `tabler/star.svg`) |
| `icon-right` | No       | —         | Icon path for right icon |
| `new-tab`    | No       | `false`   | Open link in new tab |
| `center`     | No       | `false`   | Wrap button in a centered flex container |
| `classes`    | No       | —         | Extra CSS classes |
| `data-attr`  | No       | —         | Data attribute name (renders as `data-{name}`) |
| `data-val`   | No       | —         | Data attribute value |
