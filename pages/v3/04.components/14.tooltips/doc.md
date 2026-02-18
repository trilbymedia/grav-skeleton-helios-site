---
title: Tooltips
taxonomy:
    category: docs
---

# Tooltips

Inline hover/focus tooltips for defining terms, abbreviations, and providing contextual help. Tooltips are accessible via keyboard (Tab key) and display a popup above the term.

## Basic Tooltip

Hover over the term to see the definition:

The [doc-tooltip tip="Grav is a modern flat-file CMS built with PHP"]Grav CMS[/doc-tooltip] uses [doc-tooltip tip="Markdown is a lightweight markup language for formatting text"]Markdown[/doc-tooltip] for content authoring.

[raw]
```markdown
The [doc-tooltip tip="Grav is a modern flat-file CMS built with PHP"]Grav CMS[/doc-tooltip]
uses [doc-tooltip tip="Markdown is a lightweight markup language for formatting text"]Markdown[/doc-tooltip]
for content authoring.
```
[/raw]

## Styles

Three visual styles control how the trigger term appears:

### Underline (default)

A dotted underline indicates the term has a tooltip:

[doc-tooltip tip="Cascading Style Sheets" style="underline"]CSS[/doc-tooltip] is used for styling web pages.

### Highlight

A tinted background highlights the term:

[doc-tooltip tip="Cascading Style Sheets" style="highlight"]CSS[/doc-tooltip] is used for styling web pages.

### Plain

No visual indicator — the cursor changes to a help icon:

[doc-tooltip tip="Cascading Style Sheets" style="plain"]CSS[/doc-tooltip] is used for styling web pages.

[raw]
```markdown
[doc-tooltip tip="Cascading Style Sheets" style="underline"]CSS[/doc-tooltip]
[doc-tooltip tip="Cascading Style Sheets" style="highlight"]CSS[/doc-tooltip]
[doc-tooltip tip="Cascading Style Sheets" style="plain"]CSS[/doc-tooltip]
```
[/raw]

## Keyboard Accessible

Tooltips can be triggered by keyboard focus (Tab key). Try tabbing through this paragraph:

Press [doc-tooltip tip="Tab moves focus to the next interactive element"]Tab[/doc-tooltip] to navigate, [doc-tooltip tip="Enter activates the focused element"]Enter[/doc-tooltip] to activate, and [doc-tooltip tip="Escape closes menus and dialogs"]Escape[/doc-tooltip] to dismiss.

## Glossary Example

A paragraph with multiple defined terms:

The [doc-tooltip tip="A system for organizing content into discrete web pages"]CMS[/doc-tooltip] renders pages using [doc-tooltip tip="A template engine for PHP that separates logic from presentation" style="highlight"]Twig[/doc-tooltip] templates. Content is written in [doc-tooltip tip="A text-to-HTML conversion tool that uses plain text formatting"]Markdown[/doc-tooltip] and stored as flat files, with configuration managed through [doc-tooltip tip="YAML Ain't Markup Language — a human-readable data serialization format"]YAML[/doc-tooltip] files.

[raw]
```markdown
The [doc-tooltip tip="A system for organizing content into discrete web pages"]CMS[/doc-tooltip]
renders pages using [doc-tooltip tip="A template engine for PHP" style="highlight"]Twig[/doc-tooltip]
templates. Content is written in [doc-tooltip tip="A text-to-HTML conversion tool"]Markdown[/doc-tooltip]
and stored as flat files, with configuration managed through
[doc-tooltip tip="YAML Ain't Markup Language"]YAML[/doc-tooltip] files.
```
[/raw]

## Parameters

| Parameter | Required | Default     | Description |
|-----------|----------|-------------|-------------|
| `tip`     | Yes      | —           | The tooltip text shown on hover/focus |
| `style`   | No       | `underline` | `underline` (dotted), `highlight` (tinted background), `plain` (no visual indicator) |
| `classes` | No       | —           | Extra CSS classes |

The content between `[doc-tooltip]...[/doc-tooltip]` is the visible term text.
