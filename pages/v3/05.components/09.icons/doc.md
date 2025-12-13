---
title: Icons
taxonomy:
    category: docs
---

# Icons

The Helios theme includes access to over 30,000 SVG icons through the svg-icons plugin. Icons can be used in content via shortcodes or in templates via Twig functions.

## Available Icon Sets

| Set | Icons | Description |
|-----|-------|-------------|
| `tabler` | 5,736 | Default set - clean, consistent icons |
| `heroicons/outline` | 324 | Outline style icons |
| `heroicons/solid` | 324 | Solid style icons |
| `bootstrap` | 2,059 | Bootstrap icon set |
| `brands` | 3,256 | Popular brand logos |
| `lucide` | 1,704 | Fork of Feather icons |
| `iconsax/outline` | 1,792 | Outline variant |
| `iconsax/bold` | 1,792 | Bold variant |
| `social` | 6 | Social networking icons |

## Shortcode Usage

Use the `[svg-icon]` shortcode to add icons in your content.

### Basic Usage

[svg-icon=star /] Using the default Tabler icon set

[raw]
```markdown
[svg-icon=star /]
```
[/raw]

### With Explicit Icon Name

[svg-icon icon="heart" /] Heart icon

[raw]
```markdown
[svg-icon icon="heart" /]
```
[/raw]

### Specifying Icon Set

[svg-icon icon="github" set="brands" class="w-6 h-6" /] GitHub brand icon

[raw]
```markdown
[svg-icon icon="github" set="brands" /]
```
[/raw]

### With Custom Classes

Use Tailwind classes to control size and color:

[svg-icon icon="rocket" class="w-8 h-8 text-primary" /] Large primary colored icon

[raw]
```markdown
[svg-icon icon="rocket" class="w-8 h-8 text-primary" /]
```
[/raw]

### Different Sizes

[svg-icon icon="settings" class="w-4 h-4" /] Small (16px)
[svg-icon icon="settings" class="w-6 h-6" /] Medium (24px)
[svg-icon icon="settings" class="w-8 h-8" /] Large (32px)
[svg-icon icon="settings" class="w-12 h-12" /] Extra large (48px)

[raw]
```markdown
[svg-icon icon="settings" class="w-4 h-4" /]   <!-- 16px -->
[svg-icon icon="settings" class="w-6 h-6" /]   <!-- 24px -->
[svg-icon icon="settings" class="w-8 h-8" /]   <!-- 32px -->
[svg-icon icon="settings" class="w-12 h-12" /] <!-- 48px -->
```
[/raw]

### Colors

[svg-icon icon="circle-check" class="w-6 h-6 text-green-500" /] Success
[svg-icon icon="alert-triangle" class="w-6 h-6 text-amber-500" /] Warning
[svg-icon icon="circle-x" class="w-6 h-6 text-red-500" /] Error
[svg-icon icon="info-circle" class="w-6 h-6 text-blue-500" /] Info

[raw]
```markdown
[svg-icon icon="circle-check" class="w-6 h-6 text-green-500" /]
[svg-icon icon="alert-triangle" class="w-6 h-6 text-amber-500" /]
[svg-icon icon="circle-x" class="w-6 h-6 text-red-500" /]
[svg-icon icon="info-circle" class="w-6 h-6 text-blue-500" /]
```
[/raw]

## Icon Set Examples

### Tabler Icons (Default)

[svg-icon icon="home" class="w-6 h-6" /]
[svg-icon icon="user" class="w-6 h-6" /]
[svg-icon icon="settings" class="w-6 h-6" /]
[svg-icon icon="search" class="w-6 h-6" /]
[svg-icon icon="bell" class="w-6 h-6" /]
[svg-icon icon="mail" class="w-6 h-6" /]
[svg-icon icon="calendar" class="w-6 h-6" /]
[svg-icon icon="folder" class="w-6 h-6" /]

### Hero Icons

[svg-icon icon="check-circle" set="heroicons/solid" class="w-6 h-6" /]
[svg-icon icon="x-circle" set="heroicons/solid" class="w-6 h-6" /]
[svg-icon icon="exclamation-triangle" set="heroicons/solid" class="w-6 h-6" /]
[svg-icon icon="information-circle" set="heroicons/solid" class="w-6 h-6" /]

### Brand Icons

[svg-icon icon="github" set="brands" class="w-6 h-6" /]
[svg-icon icon="twitter" set="brands" class="w-6 h-6" /]
[svg-icon icon="discord" set="brands" class="w-6 h-6" /]
[svg-icon icon="youtube" set="brands" class="w-6 h-6" /]

## Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `icon` | Yes | — | Icon name (without extension) |
| `set` | No | `tabler` | Icon set to use |
| `class` | No | — | CSS classes for sizing and color |

## Twig Function

For use in templates, use the `svg_icon()` function:

```twig
{{ svg_icon('tabler/star', 'w-6 h-6 text-primary')|raw }}
{{ svg_icon('heroicons/solid/check-circle', 'w-5 h-5 text-green-500')|raw }}
{{ svg_icon('brands/github', 'w-8 h-8')|raw }}
```

> [!NOTE]
> The `|raw` filter is required to output the SVG HTML correctly.

## Finding Icons

Browse the icon sets online:

- [Tabler Icons](https://tabler-icons.io/)
- [Hero Icons](https://heroicons.com/)
- [Bootstrap Icons](https://icons.getbootstrap.com/)
- [Simple Icons (Brands)](https://simpleicons.org/)
- [Lucide Icons](https://lucide.dev/)
- [Iconsax](https://iconsax.io/)
