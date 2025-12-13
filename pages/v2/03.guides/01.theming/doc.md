---
title: Theming
taxonomy:
    category: docs
---

# Theming Guide

Helios is built on Tailwind CSS 4, making it highly customizable through CSS variables and configuration.

## Color Customization

### Using CSS Variables

The easiest way to customize colors is through the theme configuration:

```yaml
# user/config/themes/helios.yaml
colors:
  primary: '#8B5CF6'      # Purple
  primary_light: '#A78BFA'
  primary_dark: '#7C3AED'
```

These map to CSS variables that Tailwind uses throughout the theme:

```css
--helios-color-primary: #8B5CF6;
--helios-color-primary-light: #A78BFA;
--helios-color-primary-dark: #7C3AED;
```

### Color Presets

Helios includes several pre-built color presets:

| Preset | Primary Color | Description |
|--------|---------------|-------------|
| `default` | Blue | Clean, professional blue |
| `ocean` | Teal | Cool ocean tones |
| `forest` | Green | Natural, earthy greens |
| `sunset` | Orange | Warm, vibrant orange |
| `midnight` | Indigo | Deep, sophisticated indigo |

Set a preset in your configuration:

```yaml
preset: ocean
```

## Dark Mode

### Configuration Options

```yaml
appearance:
  default: system    # system, light, or dark
  allow_toggle: true # Show toggle in header
```

### How It Works

Helios uses the `dark` class on the `<html>` element for dark mode:

```html
<html class="dark">
```

All Tailwind dark: variants automatically respond to this class.

### Customizing Dark Mode Colors

Override dark mode colors in your custom CSS:

```css
.dark {
    --helios-color-primary: #60A5FA;
    --helios-sidebar-bg-dark: #1a1a2e;
}
```

## Typography

### Fonts

Helios uses Inter for body text and JetBrains Mono for code:

```yaml
fonts:
  sans: 'Inter var'
  mono: 'JetBrains Mono'
```

### Customizing Typography

The theme uses Tailwind's Typography plugin. Customize prose styles in your CSS:

```css
.prose {
    --tw-prose-body: #374151;
    --tw-prose-headings: #111827;
}

.dark .prose {
    --tw-prose-body: #d1d5db;
    --tw-prose-headings: #f3f4f6;
}
```

## Layout Customization

### Sidebar Width

Adjust the sidebar width via CSS variables:

```css
@theme {
    --spacing-sidebar: 300px;  /* Default is 280px */
}
```

### Table of Contents Width

Similarly for the TOC:

```css
@theme {
    --spacing-toc: 260px;  /* Default is 240px */
}
```

## Custom CSS

### Adding Custom Styles

Create a custom CSS file and import it in your theme configuration or add it to your pages:

```yaml
# In page frontmatter
assets:
  css:
    - 'theme://css/custom/my-styles.css'
```

### Overriding Theme Styles

For significant customizations, you can override the theme's CSS files:

1. Copy the file from `themes/helios/css/custom/` to `themes/helios-child/css/custom/`
2. Modify as needed
3. Rebuild with `npm run build`

## Building Custom CSS

If you modify the Tailwind configuration or CSS source files:

```bash
cd user/themes/helios
npm install
npm run build    # Production build
npm run dev      # Development with watch
```

The compiled CSS goes to `css/site.min.css`.
