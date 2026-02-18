---
title: Tabs
taxonomy:
    category: docs
---

# Tabs

Tabs organize content into switchable panels. With the `sync-labels` feature, tabs with matching labels stay synchronized across your entire documentation site.

## Basic Tabs

Simple tabs without synchronization:

[doc-tabs]
[doc-tab title="Preview"]
This is the preview content.
[/doc-tab]
[doc-tab title="Code"]
This is the code content.
[/doc-tab]
[/doc-tabs]

[raw]
```markdown
[doc-tabs]
[doc-tab title="Preview"]
This is the preview content.
[/doc-tab]
[doc-tab title="Code"]
This is the code content.
[/doc-tab]
[/doc-tabs]
```
[/raw]

## Synced Tabs

Add `sync-labels=true` to synchronize tabs with matching labels. When you click a tab, all other synced tab groups on the page (and across pages) with the same label will switch too.

**Try it:** Click on JavaScript, HTML, or CSS below, then scroll down to see the other examples sync automatically.

### Example 1: Installation

[doc-tabs sync-labels=true]
[doc-tab title="JavaScript"]
```javascript
// Install via npm
npm install my-library

// Import in your code
import { myFunction } from 'my-library';

myFunction();
```
[/doc-tab]
[doc-tab title="HTML"]
```html
<!-- Include via CDN -->
<script src="https://cdn.example.com/my-library.js"></script>

<script>
  myLibrary.myFunction();
</script>
```
[/doc-tab]
[doc-tab title="CSS"]
```css
/* Import styles */
@import url('https://cdn.example.com/my-library.css');

/* Or use the npm package */
@import 'my-library/styles.css';
```
[/doc-tab]
[/doc-tabs]

### Example 2: Configuration

[doc-tabs sync-labels=true]
[doc-tab title="JavaScript"]
```javascript
// Configure with JavaScript
const config = {
  theme: 'dark',
  language: 'en',
  debug: false
};

myLibrary.init(config);
```
[/doc-tab]
[doc-tab title="HTML"]
```html
<!-- Configure with data attributes -->
<div
  data-my-library
  data-theme="dark"
  data-language="en"
  data-debug="false">
</div>
```
[/doc-tab]
[doc-tab title="CSS"]
```css
/* Configure with CSS custom properties */
:root {
  --my-library-theme: dark;
  --my-library-primary-color: #3b82f6;
  --my-library-font-size: 16px;
}
```
[/doc-tab]
[/doc-tabs]

### Example 3: Usage

[doc-tabs sync-labels=true]
[doc-tab title="JavaScript"]
```javascript
// Using the JavaScript API
const element = document.querySelector('#my-element');

myLibrary.animate(element, {
  duration: 300,
  easing: 'ease-out'
});
```
[/doc-tab]
[doc-tab title="HTML"]
```html
<!-- Using HTML markup -->
<div class="my-library-component">
  <button data-action="toggle">
    Toggle
  </button>
  <div data-content>
    Hidden content here
  </div>
</div>
```
[/doc-tab]
[doc-tab title="CSS"]
```css
/* Styling components */
.my-library-component {
  padding: 1rem;
  border-radius: 0.5rem;
  background: var(--my-library-bg);
}

.my-library-component [data-content] {
  transition: opacity 0.3s ease;
}
```
[/doc-tab]
[/doc-tabs]

## How Sync Works

When `sync-labels=true` is set:

1. **On click**: The selected tab label is saved to localStorage
2. **On page load**: Tabs check localStorage and activate matching labels
3. **Cross-tab**: Changes sync across browser tabs via storage events

This is perfect for:
- Programming language selectors (JavaScript/TypeScript/Python)
- Package manager choices (npm/yarn/pnpm)
- Framework examples (React/Vue/Angular)
- OS-specific instructions (macOS/Windows/Linux)

## Parameters

### `doc-tabs`

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `sync-labels` | No | `false` | Enable cross-page tab synchronization |
| `active` | No | `0` | Initial active tab (0-indexed) |

### `doc-tab`

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `title` | Yes | — | The tab label displayed in the tab bar |

## Mixed Content

Tabs can contain any markdown content:

[doc-tabs]
[doc-tab title="Text"]
Plain text content with **bold** and *italic* formatting.

- Lists work too
- Multiple items
[/doc-tab]
[doc-tab title="Code"]
```python
def greet(name):
    return f"Hello, {name}!"
```
[/doc-tab]
[doc-tab title="Table"]
| Name | Type | Description |
|------|------|-------------|
| title | string | Tab label |
| active | number | Active index |
[/doc-tab]
[/doc-tabs]
