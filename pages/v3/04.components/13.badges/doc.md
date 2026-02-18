---
title: Badges
taxonomy:
    category: docs
---

# Badges

Inline status pills for labels, tags, version indicators, and status markers. Badges render as `<span>` elements and flow naturally within prose text.

## Basic Badge

A default primary-colored badge:

[doc-badge label="New"]

[raw]
```markdown
[doc-badge label="New"]
```
[/raw]

## Inline Usage

Badges work inline within text. The Helios theme [doc-badge label="v3.0"] ships with built-in [doc-badge label="Stable" color="green"] component shortcodes that are [doc-badge label="Easy" color="blue"] to use.

[raw]
```markdown
The Helios theme [doc-badge label="v3.0"] ships with built-in
[doc-badge label="Stable" color="green"] component shortcodes
that are [doc-badge label="Easy" color="blue"] to use.
```
[/raw]

## Color Variants

### Filled (default)

[doc-badge label="Default"] [doc-badge label="Blue" color="blue"] [doc-badge label="Green" color="green"] [doc-badge label="Yellow" color="yellow"] [doc-badge label="Red" color="red"] [doc-badge label="Purple" color="purple"] [doc-badge label="Plain" color="plain"]

[raw]
```markdown
[doc-badge label="Default"]
[doc-badge label="Blue" color="blue"]
[doc-badge label="Green" color="green"]
[doc-badge label="Yellow" color="yellow"]
[doc-badge label="Red" color="red"]
[doc-badge label="Purple" color="purple"]
[doc-badge label="Plain" color="plain"]
```
[/raw]

### Outline

[doc-badge label="Default" style="outline"] [doc-badge label="Blue" color="blue" style="outline"] [doc-badge label="Green" color="green" style="outline"] [doc-badge label="Yellow" color="yellow" style="outline"] [doc-badge label="Red" color="red" style="outline"] [doc-badge label="Purple" color="purple" style="outline"] [doc-badge label="Plain" color="plain" style="outline"]

[raw]
```markdown
[doc-badge label="Default" style="outline"]
[doc-badge label="Blue" color="blue" style="outline"]
[doc-badge label="Green" color="green" style="outline"]
[doc-badge label="Yellow" color="yellow" style="outline"]
[doc-badge label="Red" color="red" style="outline"]
[doc-badge label="Purple" color="purple" style="outline"]
[doc-badge label="Plain" color="plain" style="outline"]
```
[/raw]

## Sizes

Two sizes are available: `default` and `sm`.

[doc-badge label="Default Size"] [doc-badge label="Small Size" size="sm"]

[raw]
```markdown
[doc-badge label="Default Size"]
[doc-badge label="Small Size" size="sm"]
```
[/raw]

## With Icons

Add an icon to the badge using the `icon` parameter:

[doc-badge label="Star" icon="tabler/star.svg"] [doc-badge label="Check" icon="tabler/check.svg" color="green"] [doc-badge label="Alert" icon="tabler/alert-triangle.svg" color="yellow"]

[raw]
```markdown
[doc-badge label="Star" icon="tabler/star.svg"]
[doc-badge label="Check" icon="tabler/check.svg" color="green"]
[doc-badge label="Alert" icon="tabler/alert-triangle.svg" color="yellow"]
```
[/raw]

## Common Patterns

### Status Labels

[doc-badge label="Published" color="green" icon="tabler/check.svg"] [doc-badge label="Draft" color="yellow"] [doc-badge label="Deprecated" color="red"] [doc-badge label="Beta" color="purple"]

### Version Tags

[doc-badge label="v3.0" color="blue"] [doc-badge label="v2.x" color="plain" style="outline"] [doc-badge label="Latest" color="green" size="sm"]

### Method Badges

[doc-badge label="GET" color="green"] [doc-badge label="POST" color="blue"] [doc-badge label="PUT" color="yellow"] [doc-badge label="DELETE" color="red"]

## Parameters

| Parameter | Required | Default   | Description |
|-----------|----------|-----------|-------------|
| `label`   | Yes      | —         | Badge text |
| `color`   | No       | `default` | `default`, `blue`, `green`, `yellow`, `red`, `purple`, `plain` |
| `style`   | No       | `filled`  | `filled` or `outline` |
| `size`    | No       | `default` | `default` or `sm` |
| `icon`    | No       | —         | Icon path (e.g., `tabler/star.svg`) |
| `classes` | No       | —         | Extra CSS classes |
