---
title: Details
taxonomy:
    category: docs
---

# Details

A simple collapsible section using the native HTML `<details>` element. Lighter than the full accordion shortcode — ideal for one-off toggles.

## Basic Usage

[doc-details title="Click to expand"]
This content is hidden by default and revealed when the user clicks the summary.
[/doc-details]

[raw]
```markdown
[doc-details title="Click to expand"]
This content is hidden by default and revealed when the user clicks the summary.
[/doc-details]
```
[/raw]

## Open by Default

Use `open=true` to show the content expanded initially:

[doc-details title="Already open" open=true]
This details section starts in the open state. The user can still toggle it closed.
[/doc-details]

[raw]
```markdown
[doc-details title="Already open" open=true]
This details section starts in the open state.
[/doc-details]
```
[/raw]

## Rich Content

Details sections support full markdown:

[doc-details title="Configuration options"]
You can configure the following settings:

- **theme** — Choose between `light` and `dark`
- **language** — Set the default language code
- **cache** — Enable or disable page caching

```yaml
system:
  theme: helios
  language: en
  cache:
    enabled: true
```
[/doc-details]

[raw]
```markdown
[doc-details title="Configuration options"]
You can configure the following settings:

- **theme** — Choose between `light` and `dark`
- **language** — Set the default language code
- **cache** — Enable or disable page caching
[/doc-details]
```
[/raw]

## Multiple Details

Stack multiple details for a lightweight FAQ:

[doc-details title="How do I install the theme?"]
Download the theme package and extract it to `user/themes/helios/`. Then set `theme: helios` in your `system.yaml`.
[/doc-details]

[doc-details title="Does it support dark mode?"]
Yes! Dark mode is built in and follows the user's system preference. You can also toggle it manually.
[/doc-details]

[doc-details title="Can I customize the colors?"]
Absolutely. Override the CSS custom properties `--color-primary` and related variables in your custom CSS.
[/doc-details]

[raw]
```markdown
[doc-details title="How do I install the theme?"]
Download and extract to `user/themes/helios/`.
[/doc-details]

[doc-details title="Does it support dark mode?"]
Yes! Dark mode follows system preference.
[/doc-details]

[doc-details title="Can I customize the colors?"]
Override `--color-primary` in custom CSS.
[/doc-details]
```
[/raw]

## Parameters

| Parameter | Required | Default   | Description |
|-----------|----------|-----------|-------------|
| `title`   | Yes      | `Details` | The summary/toggle text |
| `open`    | No       | `false`   | Whether to start in the open state |
