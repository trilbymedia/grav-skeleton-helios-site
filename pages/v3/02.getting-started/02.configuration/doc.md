---
title: Configuration
taxonomy:
    category: docs
---

# Configuration

Helios is highly configurable through the Admin panel or by editing `user/config/themes/helios.yaml`.

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
  theme: system       # system, light, or dark
  selector: true      # Show theme toggle button in header
```

### Color Customization

Helios exposes separate color settings for light and dark modes:

```yaml
colors:
  # Light Mode
  primary: '#3B82F6'              # Primary brand color (blue-500)
  primary_hover: '#2563EB'        # Primary hover color (blue-600)
  primary_text: '#FFFFFF'         # Text color on primary backgrounds (white)
  accent: '#8B5CF6'               # Accent color (violet-500)
  # Dark Mode
  primary_dark: '#60A5FA'         # Primary color for dark mode (blue-400)
  primary_dark_hover: '#93C5FD'   # Primary hover for dark mode (blue-300)
  primary_dark_text: '#111827'    # Text on primary backgrounds in dark mode (gray-900)
  accent_dark: '#A78BFA'          # Accent color for dark mode (violet-400)
```

The `primary_text` and `primary_dark_text` values control the text color on primary-colored backgrounds (e.g., filled buttons). Adjust these when your primary color requires different contrast -- use light text on dark primary colors and dark text on light primary colors.

These map to CSS variables that you can also override directly in custom CSS:

```css
:root {
    --helios-color-primary: #3B82F6;
    --helios-color-primary-light: #60A5FA;
    --helios-color-primary-dark: #2563EB;
}

.dark {
    --helios-color-primary: #60A5FA;
}
```

### Gray Scale

Choose from built-in gray scale presets or define a custom gray scale:

```yaml
colors:
  gray_preset: zinc      # zinc, slate, stone, neutral, gray, or custom
  gray_custom: ''         # Custom gray scale CSS (used when preset is 'custom')
```

When using `custom`, provide CSS variable definitions in `gray_custom`:

```css
--color-helios-gray-50: #fafafa;
--color-helios-gray-100: #f4f4f5;
--color-helios-gray-200: #e4e4e7;
--color-helios-gray-300: #d4d4d8;
--color-helios-gray-400: #a1a1aa;
--color-helios-gray-500: #71717a;
--color-helios-gray-600: #52525b;
--color-helios-gray-700: #3f3f46;
--color-helios-gray-800: #27272a;
--color-helios-gray-900: #18181b;
--color-helios-gray-950: #09090b;
```

### Fonts

Configure body and code fonts along with their sizes:

```yaml
fonts:
  body: inter              # Body font family
  body_size: medium        # Body font size: small, medium, or large
  code: jetbrains-mono     # Code font family
  code_size: medium        # Code font size: small, medium, or large
```

Available body fonts:

| Font | Description |
|------|-------------|
| `inter` | Clean, modern sans-serif (default) |
| `open-sans` | Friendly, highly legible |
| `geom` | Geometric, contemporary |
| `nunito-sans` | Rounded, approachable |
| `ubuntu-sans` | Ubuntu system font |
| `work-sans` | Optimized for screen |
| `public-sans` | Neutral, government-style |
| `quicksand` | Rounded, display-friendly |

Available code fonts:

| Font | Description |
|------|-------------|
| `jetbrains-mono` | Developer-focused monospace (default) |
| `fira-code` | Popular monospace with ligatures |
| `intel-one-mono` | Clear, readable monospace |
| `atkinson-hyperlegible-mono` | Accessibility-focused monospace |
| `inconsolata` | Classic monospace font |

## Logo & Branding

```yaml
logo:
  image:                                 # Logo image for light mode (SVG recommended)
  image_dark:                            # Logo image for dark mode (optional, falls back to light)
  text: 'My Docs'                        # Fallback text if no image
  height: h-8                            # Tailwind height class

custom_favicon:                          # Path to custom favicon
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
  sidebar_width: 280    # Sidebar width in pixels (200-400)
  content_width: 768    # Max content width in pixels (600-1200)
  toc_width: 240        # TOC width in pixels
  toc_position: right   # right, left, or hidden
  toc_start: 2          # Start heading level (1=h1, 2=h2, etc.)
  toc_depth: 3          # Number of heading levels to include (2-6)
  breadcrumbs: true     # Show breadcrumb navigation
  prev_next: true       # Show prev/next links at bottom
  scroll_spy: true      # Highlight current section in TOC
```

### Sidebar

```yaml
sidebar:
  powered_by: true      # Show "Powered by Grav" in sidebar footer
```

## Search Configuration

Helios integrates with SimpleSearch by default, with support for keyboard shortcuts:

```yaml
search:
  enabled: true
  provider: simplesearch           # simplesearch or yetisearch-pro
  keyboard_shortcut: true          # Enable keyboard shortcut for search
  shortcut_key: k                  # Shortcut key: k, p, s, f, or /
  placeholder: 'Search documentation...'
  min_chars: 2                     # Minimum characters before searching
```

For larger documentation sites, upgrade to YetiSearch Pro for advanced fuzzy matching:

```yaml
search:
  provider: yetisearch-pro
```

## Versioning

Enable folder-based documentation versioning:

```yaml
versioning:
  enabled: true
  mode: explicit                     # explicit (all prefixed) or implicit (current unprefixed)
  auto_detect: true                  # Auto-detect version folders matching pattern
  root:                              # Root folder for versioned docs (empty = site root)
  versions: []                       # Manual list of versions (used if auto_detect: false)
  default_version:                   # Default/latest version to show new visitors
  current_version:                   # Current version for implicit mode
  version_pattern: '/^v?\d+(\.\d+)*$/'  # Regex pattern for version folder detection
  redirect_unversioned: true         # Redirect URLs without version prefix to default version
  show_badge: true                   # Show version badge in header
  show_dropdown: true                # Show version dropdown in sidebar
  labels:                            # Custom labels
    v1: 'v1 (Legacy)'
    v2: 'v2 (Stable)'
    v3: 'v3 (Latest)'
```

See the [Versioning Guide](/v3/guides/versioning) for detailed instructions.

## GitHub Integration

Link your documentation to a GitHub repository:

```yaml
github:
  enabled: true
  repo: 'your-org/your-repo'        # Repository in format 'owner/repo'
  branch: main                       # Branch for edit links
  edit_link: true                    # Show "Edit on GitHub" link
  edit_text: 'Edit this page'        # Edit link text
  path_prefix:                       # Path prefix to strip (e.g., 'user/' for Grav skeletons)
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
body_classes:                          # Additional body CSS classes
append_site_title: true                # Append site title to page titles
```

## Full Configuration Example

Here's a complete configuration file with all defaults:

```yaml
enabled: true

# Appearance
appearance:
  theme: system
  selector: true

# Colors - Light Mode
colors:
  primary: '#3B82F6'
  primary_hover: '#2563EB'
  primary_text: '#FFFFFF'
  accent: '#8B5CF6'
  # Dark Mode
  primary_dark: '#60A5FA'
  primary_dark_hover: '#93C5FD'
  primary_dark_text: '#111827'
  accent_dark: '#A78BFA'
  # Gray Scale
  gray_preset: zinc
  gray_custom: ''

# Fonts
fonts:
  body: inter
  body_size: medium
  code: jetbrains-mono
  code_size: medium

# Logo
logo:
  image:
  image_dark:
  text: 'Helios Theme'
  height: h-8

# Header Menu
header:
  menu: []

# Favicon
custom_favicon:

# Sidebar
sidebar:
  powered_by: true

# Navigation
navigation:
  sidebar_width: 280
  toc_width: 240
  content_width: 768
  toc_start: 2
  toc_depth: 3
  toc_position: right
  breadcrumbs: true
  prev_next: true
  scroll_spy: true

# Versioning
versioning:
  enabled: false
  mode: explicit
  auto_detect: true
  root:
  versions: []
  default_version:
  current_version:
  version_pattern: '/^v?\d+(\.\d+)*$/'
  redirect_unversioned: true
  show_badge: true
  show_dropdown: true
  labels: {}

# Search
search:
  enabled: true
  provider: simplesearch
  keyboard_shortcut: true
  shortcut_key: k
  placeholder: 'Search documentation...'
  min_chars: 2

# GitHub integration
github:
  enabled: false
  repo:
  branch: main
  edit_link: true
  edit_text: 'Edit this page'
  path_prefix:

# HTMX Navigation (experimental)
htmx:
  enabled: true

# Advanced
body_classes:
append_site_title: true
```

## Next Steps

Now that you've configured Helios, check out the [Quick Start](/v3/getting-started/quick-start) guide to create your first documentation page.
