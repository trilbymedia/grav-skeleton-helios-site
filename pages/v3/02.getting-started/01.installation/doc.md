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
| Github Markdown Alerts | Recommended | Required for callout support |
| Codesh | Recommended | Server-side syntax highlighting with 200+ languages and VS Code themes |
| Page TOC | Recommended | Generates table of contents from headings |
| API Doc Import | Optional | Import OpenAPI/Swagger specs as API documentation pages |

Install the recommended plugins via GPM:

```bash
bin/gpm install simplesearch shortcode-core svg-icons github-markdown-alerts codesh page-toc
```

For API documentation features, also install:

```bash
bin/gpm install api-doc-import
```

## Skeleton Packages

Looking for Helios demo skeleton packages to get you started? You can [download them directly from GitHub](https://github.com/trilbymedia/grav-skeleton-helios-site?target=_blank) and follow the instructions in the [README.md](https://github.com/trilbymedia/grav-skeleton-helios-site/blob/develop/README.md) file of the repository.

The quickest way to download the files is to simply click the green **Code** button then click the **Download ZIP**.

## Next Steps

Once installed, proceed to [Configuration](/v3/getting-started/configuration) to customize your theme.
