---
title: Copy Text
taxonomy:
    category: docs
---

# Copy Text

Inline copyable text with a one-click clipboard button. Works anywhere — inside paragraphs, tables, lists, or on its own line. Use it for commands, config values, file paths, or any text a reader might want to copy.

## Basic Usage

Install the theme with [doc-copy text="composer require getgrav/grav-theme-helios"] and you're ready to go.

[raw]
```markdown
Install the theme with [doc-copy text="composer require getgrav/grav-theme-helios"] and you're ready to go.
```
[/raw]

## Self-Closing vs Container

Use the `text` parameter for short values:

[doc-copy text="npm install"]

Or wrap content between tags:

[doc-copy]bin/grav install[/doc-copy]

[raw]
```markdown
[doc-copy text="npm install"]

[doc-copy]bin/grav install[/doc-copy]
```
[/raw]

## Inline in Paragraphs

The config file is located at [doc-copy text="user/config/system.yaml"]. Set the theme to [doc-copy text="helios"] and enable caching with [doc-copy text="cache: true"].

[raw]
```markdown
The config file is located at [doc-copy text="user/config/system.yaml"]. Set the theme to [doc-copy text="helios"] and enable caching with [doc-copy text="cache: true"].
```
[/raw]

## In Tables

| Setting | Value |
|---------|-------|
| Theme   | [doc-copy text="helios"] |
| Cache   | [doc-copy text="true"] |
| Debug   | [doc-copy text="false"] |

[raw]
```markdown
| Setting | Value |
|---------|-------|
| Theme   | [doc-copy text="helios"] |
| Cache   | [doc-copy text="true"] |
| Debug   | [doc-copy text="false"] |
```
[/raw]

## Commands

Run [doc-copy text="bin/gpm install helios"] to install the theme.

Then clear the cache with [doc-copy text="bin/grav clearcache"].

[raw]
```markdown
Run [doc-copy text="bin/gpm install helios"] to install the theme.

Then clear the cache with [doc-copy text="bin/grav clearcache"].
```
[/raw]

## File Paths

Templates are in [doc-copy text="user/themes/helios/templates/"] and CSS is built to [doc-copy text="build/css/site.css"].

[raw]
```markdown
Templates are in [doc-copy text="user/themes/helios/templates/"] and CSS is built to [doc-copy text="build/css/site.css"].
```
[/raw]

## Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `text`    | Yes*     | —       | The text to display and copy. Required if self-closing; if using container form, content is used instead. |
