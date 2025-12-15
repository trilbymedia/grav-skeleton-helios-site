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
  theme: system        # system, light, or dark
  selector: true       # Show theme toggle in header
  storage: true        # Remember user's selection

# Brand colors
colors:
  primary: '#3B82F6'
  primary_dark: '#60A5FA'
  accent: '#8B5CF6'
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
  theme: system
  selector: true    # Show toggle button in header
  storage: true     # Remember user's preference
  cookie: true      # Use cookie (true) or localStorage (false)
```

### Color Presets

Choose from built-in color presets or define custom colors:

```yaml
preset: default  # default, ocean, forest, sunset, midnight
```

Or set custom colors:

```yaml
colors:
  primary: '#8B5CF6'       # Primary brand color
  primary_dark: '#A78BFA'  # Primary color for dark mode
  accent: '#EC4899'        # Accent color for highlights
```

### Fonts

Configure body and code fonts:

```yaml
fonts:
  body: inter           # inter, open-sans, nunito-sans, work-sans, public-sans, quicksand
  code: jetbrains-mono  # Monospace font for code blocks
```

## Logo & Branding

```yaml
logo:
  image: 'user://assets/logo.svg'  # Path to logo image (SVG recommended)
  text: 'My Docs'                  # Fallback text if no image
  height: h-8                      # Tailwind height class

custom_favicon: 'user://assets/favicon.png'  # Custom favicon
```

## Header Menu

Add navigation links to the header:

```yaml
header:
  menu:
    - route: '/changelog'
      label: 'Changelog'
    - route: 'https://github.com/your/repo'
      label: 'GitHub'
      external: true
```

## Navigation Settings

Configure the sidebar, content area, and table of contents:

```yaml
navigation:
  sidebar_width: 280    # Sidebar width in pixels
  content_width: 768    # Max content width in pixels
  toc_width: 240        # TOC width in pixels
  toc_position: right   # right, left, or hidden
  toc_start: 2          # Start heading level (1=h1, 2=h2)
  toc_depth: 3          # Number of heading levels to include
  breadcrumbs: true     # Show breadcrumb navigation
  prev_next: true       # Show prev/next links at bottom
  scroll_spy: true      # Highlight current section in TOC
```

## Search Configuration

Helios integrates with SimpleSearch by default:

```yaml
search:
  enabled: true
  provider: simplesearch    # simplesearch or yetisearch
  keyboard_shortcut: true   # Enable Cmd+K / Ctrl+K
  placeholder: 'Search documentation...'
  min_chars: 2              # Minimum characters before searching
```

For premium search with YetiSearch:

```yaml
search:
  provider: yetisearch
```

## Code Block Settings

Configure syntax highlighting and code features:

```yaml
code:
  theme: github-dark    # github-dark, dracula, nord, one-dark
  copy_button: true     # Show copy button
  line_numbers: false   # Show line numbers by default
  word_wrap: false      # Enable word wrap
```

> [!NOTE]
> When using the Codesh plugin, syntax highlighting is handled by Shiki instead of Prism.js, providing more accurate highlighting for modern languages.

## Versioning

Enable folder-based documentation versioning:

```yaml
versioning:
  enabled: true
  mode: explicit           # explicit (all prefixed) or implicit (current unprefixed)
  auto_detect: true        # Auto-detect version folders
  root: ''                 # Root folder containing versions (empty = site root)
  default_version: v3      # Default/latest version
  current_version: v3      # Current version for implicit mode
  version_pattern: '/^v?\d+(\.\d+)*$/'  # Regex for version detection
  show_badge: true         # Show version badge in header
  show_dropdown: true      # Show version dropdown in sidebar
  labels:                  # Custom labels
    v1: 'v1 (Legacy)'
    v2: 'v2 (Stable)'
    v3: 'v3 (Latest)'
```

See the [Versioning Guide](/v3/guides/versioning) for detailed instructions.

## API Documentation

Configure API documentation features:

```yaml
api:
  enabled: true
  base_url: 'https://api.example.com'  # Base URL shown in endpoint paths
```

## GitHub Integration

Link your documentation to a GitHub repository:

```yaml
github:
  enabled: true
  repo: 'your-org/your-repo'
  branch: main
  edit_link: true           # Show "Edit this page" links
  edit_text: 'Edit this page'
```

## HTMX Navigation (Experimental)

Enable SPA-like navigation that loads content via XHR:

```yaml
htmx:
  enabled: true
```

When enabled, navigation between pages happens without full page reloads, providing a smoother user experience.

## Advanced Settings

```yaml
external_in_new_tab: true              # Open external links in new tab
append_site_title: true                # Append site title to page titles
body_classes: ''                       # Additional body CSS classes
section_classes: 'bg-white dark:bg-gray-950'  # Content section classes
```

## Full Configuration Example

Here's a complete configuration file:

```yaml
enabled: true

appearance:
  theme: system
  selector: true
  storage: true

colors:
  primary: '#3B82F6'
  primary_dark: '#60A5FA'
  accent: '#8B5CF6'

preset: default

fonts:
  body: inter
  code: jetbrains-mono

logo:
  text: 'My Documentation'
  height: h-8

header:
  menu:
    - route: '/changelog'
      label: 'Changelog'

navigation:
  sidebar_width: 280
  content_width: 768
  toc_position: right
  toc_depth: 3
  breadcrumbs: true
  prev_next: true
  scroll_spy: true

search:
  enabled: true
  provider: simplesearch
  keyboard_shortcut: true

code:
  copy_button: true
  line_numbers: false

versioning:
  enabled: false

github:
  enabled: false

api:
  enabled: true

htmx:
  enabled: false
```

## Next Steps

Now that you've configured Helios, check out the [Quick Start](/v3/getting-started/quick-start) guide to create your first documentation page.
