---
title: Callouts
taxonomy:
    category: docs
---

# Callouts

Callouts (also known as alerts or admonitions) help highlight important information in your documentation. Helios uses the `github-markdown-alerts` plugin for callouts support, so please install it first.

## Available Types

Five callout types are available, each with a distinct color and icon.

### Note

Use notes for general information that readers should be aware of:

> [!NOTE]
> Useful information that users should know, even when skimming content.

[raw]
```markdown
> [!NOTE]
> Useful information that users should know, even when skimming content.
```
[/raw]

### Tip

Tips share best practices or helpful suggestions:

> [!TIP]
> Helpful advice for doing things better or more easily.

[raw]
```markdown
> [!TIP]
> Helpful advice for doing things better or more easily.
```
[/raw]

### Important

Important callouts highlight key information users need:

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

[raw]
```markdown
> [!IMPORTANT]
> Key information users need to know to achieve their goal.
```
[/raw]

### Warning

Warnings alert readers to potential issues or caveats:

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

[raw]
```markdown
> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.
```
[/raw]

### Caution

Caution callouts advise about risks or negative outcomes:

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.

[raw]
```markdown
> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.
```
[/raw]

## Markdown Support

Callouts support full markdown inside, including formatting, lists, and code:

> [!TIP]
> You can use **bold**, *italic*, and `inline code` in callouts.
>
> - Bullet points work
> - Multiple items supported
>
> ```javascript
> // Code blocks too!
> console.log('Hello');
> ```

[raw]
```markdown
> [!TIP]
> You can use **bold**, *italic*, and `inline code` in callouts.
>
> - Bullet points work
> - Multiple items supported
>
> ```javascript
> // Code blocks too!
> console.log('Hello');
> ```
```
[/raw]

## Best Practices

1. **Use sparingly** - Limit to one or two alerts per page to avoid overwhelming readers
2. **Choose the right type** - Match the alert type to the importance of the message
3. **Keep it brief** - Callouts work best with concise, actionable information
4. **Don't nest alerts** - Alerts cannot be nested within other elements
