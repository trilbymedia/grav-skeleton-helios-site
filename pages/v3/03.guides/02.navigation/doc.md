---
title: Navigation
taxonomy:
    category: docs
---

# Navigation Guide

Helios provides a flexible navigation system with sidebar, breadcrumbs, and on-page table of contents.

## Sidebar Navigation

### Automatic Structure

The sidebar automatically reflects your page structure. Pages are ordered by their folder prefix:

[doc-file-tree]
user/pages/
├── 01.getting-started/    # Shows first
├── 02.guides/             # Shows second
└── 03.api/                # Shows third
[/doc-file-tree]

### Controlling Visibility

Hide a page from navigation using frontmatter:

```yaml
---
title: Hidden Page
visible: false
---
```

Or use `routable: false` to make it non-navigable:

```yaml
---
title: Non-routable Page
routable: false
---
```

### Custom Menu Labels

By default, the page title appears in navigation. Override with `menu`:

```yaml
---
title: Getting Started with Helios Documentation Theme
menu: Getting Started
---
```

### Collapsible Sections

Parent pages with children automatically become collapsible sections. Control the default state:

```yaml
navigation:
  sidebar_collapsed: false  # Expand all by default
```

## Breadcrumbs

Breadcrumbs show the current page's location in the hierarchy:

```
Home > Guides > Navigation
```

### Configuration

```yaml
navigation:
  breadcrumbs: true
```

### Customizing Breadcrumbs

Override the breadcrumb separator in your CSS or template:

```twig
{# In partials/breadcrumbs.html.twig #}
{% set separator = '/' %}
```

## On-Page Table of Contents

The TOC automatically extracts headings from your content.

### Configuration

```yaml
navigation:
  toc_position: right   # left, right, or hidden
  toc_depth: 3          # Include h2, h3 (up to h6)
```

### TOC Depth

| Value | Headings Included |
|-------|-------------------|
| 2 | h2 only |
| 3 | h2, h3 |
| 4 | h2, h3, h4 |
| 5 | h2, h3, h4, h5 |
| 6 | All headings |

### Excluding Headings

Add the `no-toc` class to exclude a heading:

```markdown
## This Appears in TOC

## This Does Not {.no-toc}
```

### Scroll Spy

The TOC highlights the current section as you scroll. This is handled automatically via JavaScript.

## Previous/Next Navigation

Page-to-page navigation appears at the bottom of each page.

### Configuration

```yaml
navigation:
  prev_next: true
```

### Customizing Order

Prev/Next follows the same order as the sidebar. To change the order of a page, rename its folder prefix:

```bash
# Change from third to second position
mv 03.my-page 02.my-page
```

### Excluding from Prev/Next

Pages with `routable: false` are excluded from prev/next navigation.

## Mobile Navigation

On mobile devices, the sidebar becomes a slide-out menu activated by the hamburger icon.

### Breakpoints

- **Desktop**: Sidebar always visible (>= 1024px)
- **Tablet**: Sidebar hidden, hamburger shown (768px - 1024px)
- **Mobile**: Sidebar hidden, simplified layout (< 768px)

### Customizing Mobile Behavior

The mobile menu is controlled by Alpine.js. Customize in `js/navigation.js`:

```javascript
Alpine.data('navigation', () => ({
    open: false,
    toggle() {
        this.open = !this.open;
    }
}))
```

## Search Integration

The search button in the header opens the search modal.

### Keyboard Shortcut

Press `Cmd+K` (Mac) or `Ctrl+K` (Windows/Linux) to open search anywhere on the page.

### Configuration

```yaml
search:
  keyboard_shortcut: true
  placeholder: 'Search documentation...'
```

See the [Search documentation](/components/search) for more details.
