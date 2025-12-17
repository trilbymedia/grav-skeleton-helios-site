---
title: Configuration
taxonomy:
    category: docs
---

# Configuration

Helios is highly configurable through the Admin panel or by editing `user/config/themes/helios.yaml`.

## Basic Configuration

Create or edit `user/config/themes/helios.yaml`:

```yaml
enabled: true

# Appearance settings
appearance:
  default: system    # system, light, or dark
  allow_toggle: true

# Brand colors (CSS variables)
colors:
  primary: '#3B82F6'
  primary_light: '#60A5FA'
  primary_dark: '#2563EB'
```

## Appearance Settings

### Dark Mode

Helios supports three modes for dark/light appearance:

| Mode | Description |
|------|-------------|
| `system` | Follows the user's OS preference |
| `light` | Always use light mode |
| `dark` | Always use dark mode |

```yaml
appearance:
  default: system
  allow_toggle: true  # Show toggle button in header
```

### Color Presets

Choose from built-in color presets or define your own:

```yaml
preset: default  # default, ocean, forest, sunset, midnight
```

Or set custom colors:

```yaml
colors:
  primary: '#8B5CF6'      # Purple
  primary_light: '#A78BFA'
  primary_dark: '#7C3AED'
```

## Navigation Settings

Configure the sidebar and table of contents:

```yaml
navigation:
  sidebar_position: left    # left or right
  toc_position: right       # left, right, or hidden
  toc_depth: 3              # Maximum heading depth (2-6)
  breadcrumbs: true         # Show breadcrumb navigation
  prev_next: true           # Show prev/next links at bottom
```

## Search Configuration

Helios integrates with SimpleSearch by default:

```yaml
search:
  provider: simplesearch    # simplesearch or yetisearch-pro
  keyboard_shortcut: true   # Enable Cmd+K / Ctrl+K
  placeholder: 'Search docs...'
```

For premium search with YetiSearch Pro:

```yaml
search:
  provider: yetisearch-pro
```

## Versioning

Enable folder-based documentation versioning:

```yaml
versioning:
  enabled: true
  root: docs           # Root folder containing versions
  default_version: v2  # Current/default version
  show_badge: true     # Show version badge in header
```

See the [Versioning Guide](/guides/versioning) for more details.

## GitHub Integration

Link your documentation to a GitHub repository:

```yaml
github:
  enabled: true
  repo: 'your-org/your-repo'
  branch: main
  edit_link: true  # Show "Edit this page" links
```

## Full Configuration Example

Here's a complete configuration file:

```yaml
enabled: true

appearance:
  default: system
  allow_toggle: true

colors:
  primary: '#3B82F6'
  primary_light: '#60A5FA'
  primary_dark: '#2563EB'

preset: default

navigation:
  sidebar_position: left
  toc_position: right
  toc_depth: 3
  breadcrumbs: true
  prev_next: true

search:
  provider: simplesearch
  keyboard_shortcut: true
  placeholder: 'Search documentation...'

code:
  theme: github-dark
  copy_button: true
  line_numbers: false

versioning:
  enabled: false

github:
  enabled: false

logo:
  image: null
  text: 'Documentation'
```

## Next Steps

Now that you've configured Helios, check out the [Quick Start](/getting-started/quick-start) guide to create your first documentation page.
