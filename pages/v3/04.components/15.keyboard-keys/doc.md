---
title: Keyboard Keys
taxonomy:
    category: docs
---

# Keyboard Keys

Styled keyboard keys for documenting shortcuts and key combinations. Each key gets a raised appearance with a subtle border and shadow.

## Single Key

[doc-kbd key="Enter"]

[raw]
```markdown
[doc-kbd key="Enter"]
```
[/raw]

## Key Combinations

Separate keys with `+` to render compound shortcuts:

Press [doc-kbd key="Ctrl+C"] to copy and [doc-kbd key="Ctrl+V"] to paste.

[raw]
```markdown
Press [doc-kbd key="Ctrl+C"] to copy and [doc-kbd key="Ctrl+V"] to paste.
```
[/raw]

## Multi-Key Shortcuts

Works with three or more keys:

[doc-kbd key="Ctrl+Shift+P"] opens the command palette.

[raw]
```markdown
[doc-kbd key="Ctrl+Shift+P"] opens the command palette.
```
[/raw]

## Mac Shortcuts

Use the standard Mac modifier symbols:

| Action         | Shortcut |
|----------------|----------|
| Save           | [doc-kbd key="⌘+S"] |
| Undo           | [doc-kbd key="⌘+Z"] |
| Find           | [doc-kbd key="⌘+F"] |
| Select All     | [doc-kbd key="⌘+A"] |
| Bold           | [doc-kbd key="⌘+B"] |
| Command Palette | [doc-kbd key="⌘+⇧+P"] |
| Preferences    | [doc-kbd key="⌘+,"] |
| Special Char   | [doc-kbd key="⌥+⇧+8"] |
| Spotlight      | [doc-kbd key="⌘+Space"] |

[raw]
```markdown
| Action         | Shortcut |
|----------------|----------|
| Save           | [doc-kbd key="⌘+S"] |
| Undo           | [doc-kbd key="⌘+Z"] |
| Command Palette | [doc-kbd key="⌘+⇧+P"] |
| Special Char   | [doc-kbd key="⌥+⇧+8"] |
```
[/raw]

Available Mac symbols: `⌘` (Command), `⌥` (Option), `⇧` (Shift), `⌃` (Control), `⎋` (Escape)

## Common Shortcuts

| Action         | Windows/Linux | Mac |
|----------------|---------------|-----|
| Save           | [doc-kbd key="Ctrl+S"] | [doc-kbd key="⌘+S"] |
| Undo           | [doc-kbd key="Ctrl+Z"] | [doc-kbd key="⌘+Z"] |
| Find           | [doc-kbd key="Ctrl+F"] | [doc-kbd key="⌘+F"] |
| Select All     | [doc-kbd key="Ctrl+A"] | [doc-kbd key="⌘+A"] |

[raw]
```markdown
| Action | Windows/Linux | Mac |
|--------|---------------|-----|
| Save   | [doc-kbd key="Ctrl+S"] | [doc-kbd key="⌘+S"] |
| Undo   | [doc-kbd key="Ctrl+Z"] | [doc-kbd key="⌘+Z"] |
```
[/raw]

## Special Keys

Works with any key label:

[doc-kbd key="Esc"] [doc-kbd key="Tab"] [doc-kbd key="Space"] [doc-kbd key="Backspace"] [doc-kbd key="Delete"]

[raw]
```markdown
[doc-kbd key="Esc"] [doc-kbd key="Tab"] [doc-kbd key="Space"] [doc-kbd key="Backspace"] [doc-kbd key="Delete"]
```
[/raw]

## Arrow Keys

[doc-kbd key="Up"] [doc-kbd key="Down"] [doc-kbd key="Left"] [doc-kbd key="Right"]

[raw]
```markdown
[doc-kbd key="Up"] [doc-kbd key="Down"] [doc-kbd key="Left"] [doc-kbd key="Right"]
```
[/raw]

## Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `key`     | Yes      | —       | Key text, use `+` for combinations (e.g., `Ctrl+Shift+P` or `⌘+S`) |
