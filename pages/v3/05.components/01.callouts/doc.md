---
title: Callouts
taxonomy:
    category: docs
---

# Callouts

Callouts (also known as admonitions or alerts) help highlight important information in your documentation.

## Available Types

Helios supports five callout types, each with a distinct color and icon.

### Note

Use notes for general information that readers should be aware of:

[notice]
This is a **note** callout. Use it to highlight important information that readers should be aware of.
[/notice]

```markdown
[notice]
This is a note callout.
[/notice]
```

### Info

Info callouts provide helpful context or additional details:

[info]
This is an **info** callout. Use it for helpful context or supplementary information.
[/info]

```markdown
[info]
This is an info callout.
[/info]
```

### Tip

Tips share best practices or helpful suggestions:

[tip]
This is a **tip** callout. Use it to share best practices, shortcuts, or helpful suggestions.
[/tip]

```markdown
[tip]
This is a tip callout.
[/tip]
```

### Warning

Warnings alert readers to potential issues or caveats:

[warning]
This is a **warning** callout. Use it when there's a potential issue readers should be aware of.
[/warning]

```markdown
[warning]
This is a warning callout.
[/warning]
```

### Danger

Danger callouts highlight critical information that could cause problems:

[danger]
This is a **danger** callout. Use it for critical information that could lead to data loss or security issues.
[/danger]

```markdown
[danger]
This is a danger callout.
[/danger]
```

## Markdown Support

Callouts support full markdown inside:

[notice]
You can use **bold**, *italic*, `code`, and even:

- Bullet points
- Lists
- [Links](/components/callouts)

```javascript
// Code blocks too!
console.log('Hello');
```
[/notice]

## Custom Titles

Add a custom title to any callout:

[notice=Custom Title]
This callout has a custom title instead of the default "Note".
[/notice]

```markdown
[notice=Custom Title]
This callout has a custom title.
[/notice]
```

## Styling

Callout colors can be customized in your CSS:

```css
.callout-warning {
    --callout-border-color: #f59e0b;
    --callout-bg-color: #fef3c7;
}
```
