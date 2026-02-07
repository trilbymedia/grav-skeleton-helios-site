---
title: Theming
taxonomy:
    category: docs
---

# Theming Guide

Helios is built on Tailwind CSS 4, making it highly customizable. Most visual aspects of the theme can be configured directly in `user/config/themes/helios.yaml` or via the Admin panel -- no CSS or build step required.

## Appearance (Dark Mode)

Helios supports light mode, dark mode, and automatic system detection. Configure the default behavior and whether users can toggle between them:

```yaml
appearance:
  theme: system       # system, light, or dark
  selector: true      # Show the light/dark toggle in the header
```

| Mode | Description |
|------|-------------|
| `system` | Follows the user's OS preference automatically |
| `light` | Always use light mode |
| `dark` | Always use dark mode |

When `selector` is enabled, a toggle button appears in the header allowing visitors to switch between light and dark mode. Their preference is stored in `localStorage` so it persists between visits.

## Colors

Helios exposes eight color settings that let you brand the theme without touching CSS. These control links, buttons, badges, and other UI accents throughout the theme.

### Light Mode Colors

```yaml
colors:
  primary: '#3B82F6'         # Primary brand color (default: blue-500)
  primary_hover: '#2563EB'   # Hover state for primary color (default: blue-600)
  primary_text: '#FFFFFF'    # Text color on primary backgrounds (default: white)
  accent: '#8B5CF6'          # Accent color for highlights (default: violet-500)
```

### Dark Mode Colors

```yaml
colors:
  primary_dark: '#60A5FA'          # Primary color in dark mode (default: blue-400)
  primary_dark_hover: '#93C5FD'    # Hover state in dark mode (default: blue-300)
  primary_dark_text: '#111827'     # Text on primary backgrounds in dark mode (default: gray-900)
  accent_dark: '#A78BFA'           # Accent color in dark mode (default: violet-400)
```

These values are injected as CSS custom properties, so they automatically apply everywhere the theme references primary/accent colors. You can use any valid CSS hex color value.

### Primary Text Color

The `primary_text` and `primary_dark_text` settings control the text color used on primary-colored backgrounds, such as filled buttons. This ensures readability regardless of your chosen primary color:

- For **dark** primary colors (e.g., `#1E40AF`), use a **light** text color like `#FFFFFF`
- For **light** primary colors (e.g., `#93C5FD`), use a **dark** text color like `#111827`

These settings are particularly important when customizing the primary color, as the default white text may not provide sufficient contrast on lighter primary backgrounds.

### Gray Scale

The gray scale controls the neutral tones used for backgrounds, borders, and text throughout the theme. Choose from several built-in presets:

```yaml
colors:
  gray_preset: zinc      # zinc, slate, stone, neutral, gray, or custom
```

| Preset | Character |
|--------|-----------|
| `zinc` | Cool blue-gray (default) |
| `slate` | Subtle blue undertone |
| `stone` | Warm, slightly brown-gray |
| `neutral` | True neutral gray, no undertone |
| `gray` | Standard cool gray |
| `custom` | Define your own gray scale |

For full control, set `gray_preset: custom` and provide your own scale using CSS custom properties:

```yaml
colors:
  gray_preset: custom
  gray_custom: |
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

## Typography

### Body Font

Choose from a curated set of web fonts for body text:

```yaml
fonts:
  body: inter          # Default body font
  body_size: medium    # small, medium, or large
```

Available body fonts:

| Font | Description |
|------|-------------|
| `inter` | Clean, modern sans-serif (default) |
| `open-sans` | Highly readable, friendly |
| `geom` | Geometric, modern feel |
| `nunito-sans` | Rounded, approachable |
| `ubuntu-sans` | Ubuntu's distinctive sans-serif |
| `work-sans` | Optimized for screen reading |
| `public-sans` | Neutral government-grade font |
| `quicksand` | Rounded, playful geometric |

### Code Font

Choose the monospace font used for code blocks and inline code:

```yaml
fonts:
  code: jetbrains-mono   # Default code font
  code_size: medium       # small, medium, or large
```

Available code fonts:

| Font | Description |
|------|-------------|
| `jetbrains-mono` | Developer favorite with ligatures (default) |
| `fira-code` | Popular coding font with ligatures |
| `intel-one-mono` | Clear, legible monospace by Intel |
| `atkinson-hyperlegible-mono` | Designed for maximum legibility |
| `inconsolata` | Classic, clean monospace |

### Font Sizing

Both body and code fonts support three size presets:

| Size | Description |
|------|-------------|
| `small` | Compact sizing for dense documentation |
| `medium` | Balanced default sizing |
| `large` | Larger text for improved readability |

## Logo & Branding

Customize the logo displayed in the sidebar header:

```yaml
logo:
  image:                              # Logo image for light mode (SVG recommended)
  image_dark:                         # Separate logo for dark mode (optional)
  text: 'My Documentation'           # Fallback text when no image is set
  height: h-8                        # Tailwind height class for the logo

custom_favicon:                       # Path to a custom favicon image
```

When both `image` and `image_dark` are set, Helios automatically swaps between them based on the current theme. If only `image` is set, it's used for both modes.

## Layout Dimensions

Fine-tune the widths of the three-column layout directly in the YAML configuration:

```yaml
navigation:
  sidebar_width: 280    # Sidebar width in pixels (200-400)
  content_width: 768    # Max content width in pixels (600-1200)
  toc_width: 240        # Table of contents width in pixels
```

These values are applied as CSS custom properties and take effect immediately without any build step.

## Advanced CSS Customization

For deeper customizations beyond what the YAML configuration offers, you can modify the theme's CSS source.

### Creating a Child Theme

It's strongly recommended to create a child theme rather than editing Helios directly. This allows you to update Helios without losing your customizations:

```bash
bin/plugin devtools new-theme
```

When prompted, select **copy** and choose **Helios** as the base theme.

### Building CSS

Helios uses Tailwind CSS 4. To compile CSS after making changes:

```bash
cd user/themes/helios
npm install
npm run dev      # Development with watch mode
npm run prod     # Production build (minified)
```

The compiled CSS is output to `css/site.min.css`.

### Overriding CSS Variables

If you need to override colors or spacing beyond the YAML options, you can use CSS custom properties in a custom stylesheet:

```css
:root {
    --color-helios-primary: #8B5CF6;
    --color-helios-primary-hover: #7C3AED;
    --color-helios-accent: #EC4899;
}

.dark {
    --color-helios-primary: #A78BFA;
    --color-helios-primary-hover: #C4B5FD;
    --color-helios-accent: #F472B6;
}
```
