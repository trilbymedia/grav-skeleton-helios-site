---
title: Installation
taxonomy:
    category: docs
---

# Installation

There are several ways to install the Helios theme for Grav.

## GPM Installation (Preferred)

The simplest way to install this theme is via the [Grav Package Manager (GPM)](https://learn.getgrav.org/cli-console/grav-cli-gpm) through your system's terminal:

```bash
bin/gpm install helios
```

This will install the Helios theme into your `/user/themes/helios` directory.

## Manual Installation

To install this theme manually:

1. Download the zip version of this repository
2. Unzip it under `/your/site/grav/user/themes`
3. Rename the folder to `helios`

You should now have all the theme files under:

```
/your/site/grav/user/themes/helios
```

## Required Plugins

Helios works best with the following plugins:

| Plugin | Required | Description |
|--------|----------|-------------|
| SimpleSearch | Yes | Powers the search functionality |
| Shortcode Core | Recommended | Enables shortcode syntax for callouts and tabs |
| SVG Icons | Recommended | Provides icon support throughout the theme |

Install them via GPM:

```bash
bin/gpm install simplesearch shortcode-core svg-icons
```

## Skeleton Installation

For a complete demo installation, you can use the Helios Skeleton:

```bash
# Download and extract the skeleton
wget https://getgrav.org/download/skeletons/helios-site/latest
unzip helios-site-*.zip -d my-docs-site
```

This gives you a ready-to-use documentation site with example content.

## Next Steps

Once installed, proceed to [Configuration](/getting-started/configuration) to customize your theme.
