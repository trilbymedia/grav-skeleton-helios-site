---
title: Home
icon: tabler/home-2.svg
body_classes: 'title-center title-h1h2'
---

# Helios Documentation Theme

A modern, feature-rich documentation theme for Grav CMS built on **Tailwind CSS 4** and **Alpine.js**.

[doc-grid]
[doc-card title="Getting Started" icon="tabler/rocket.svg" link="/v3/getting-started/installation"]
Install and configure Helios in minutes with our step-by-step guide.
[/doc-card]
[doc-card title="Explore Components" icon="tabler/components.svg" link="/v3/components"]
Discover callouts, cards, tabs, code blocks, and more.
[/doc-card]
[/doc-grid]

---

## Core Features

[doc-grid columns=3]
[doc-card title="Three-Column Layout" icon="tabler/layout-columns.svg"]
Sidebar navigation, content area, and on-page table of contents with configurable widths.
[/doc-card]
[doc-card title="Dark & Light Mode" icon="tabler/sun-moon.svg"]
System preference detection with manual toggle. Remembers user choice.
[/doc-card]
[doc-card title="Responsive Design" icon="tabler/devices.svg"]
Optimized for desktop, tablet, and mobile with collapsible navigation.
[/doc-card]
[/doc-grid]

## Appearance & Theming

[doc-grid columns=3]
[doc-card title="5 Color Presets" icon="tabler/palette.svg"]
Default, Ocean, Forest, Sunset, and Midnight — or define your own custom colors.
[/doc-card]
[doc-card title="8 Font Choices" icon="tabler/typography.svg"]
Inter, Open Sans, Nunito Sans, Work Sans, Public Sans, Ubuntu, Poppins, Quicksand.
[/doc-card]
[doc-card title="Configurable Sizing" icon="tabler/adjustments.svg"]
Small, medium, or large font sizes. Adjustable sidebar, content, and TOC widths.
[/doc-card]
[/doc-grid]

## Search

[doc-grid]
[doc-card title="SimpleSearch" icon="tabler/search.svg"]
Built-in real-time full-text search with keyboard shortcuts (Cmd+K / Ctrl+K).
[/doc-card]
[doc-card title="YetiSearch Pro" icon="tabler/search-code.svg"]
Advanced fuzzy matching, chunked indexing, and relevance scoring for larger sites.
[/doc-card]
[/doc-grid]

## Code Blocks

Powered by the **Codesh** plugin with server-side syntax highlighting.

[doc-grid columns=3]
[doc-card title="200+ Languages" icon="tabler/code.svg"]
JavaScript, Python, PHP, Ruby, Go, Rust, SQL, YAML, and many more.
[/doc-card]
[doc-card title="70+ Themes" icon="tabler/brush.svg"]
GitHub, Dracula, Nord, One Dark Pro, Tokyo Night, Catppuccin, and more.
[/doc-card]
[doc-card title="Line Features" icon="tabler/list-numbers.svg"]
Line numbers, highlighting, focus mode, and diff visualization.
[/doc-card]
[doc-card title="Code Groups" icon="tabler/folders.svg"]
Synced tabs for multi-file examples that stay in sync across the page.
[/doc-card]
[doc-card title="Filename Display" icon="tabler/file-code.svg"]
Show file context in the header with optional language badges.
[/doc-card]
[doc-card title="Auto Theme Switch" icon="tabler/toggle-right.svg"]
Automatically adapts to light or dark mode.
[/doc-card]
[/doc-grid]

## Documentation Components

[doc-grid columns=3]
[doc-card title="Callouts" icon="tabler/alert-circle.svg" link="/v3/components/callouts"]
Note, Tip, Important, Warning, and Caution alerts using GitHub syntax.
[/doc-card]
[doc-card title="Cards & Grids" icon="tabler/layout-grid.svg" link="/v3/components/cards"]
Flexible card layouts with icons and links in responsive grids.
[/doc-card]
[doc-card title="Synced Tabs" icon="tabler/folders.svg" link="/v3/components/synced-tabs"]
Persistent tab selection across pages — perfect for OS or language selectors.
[/doc-card]
[doc-card title="Steps" icon="tabler/list-check.svg" link="/v3/components/steps"]
Numbered task lists with visual timeline for tutorials and guides.
[/doc-card]
[doc-card title="File Trees" icon="tabler/folder-tree.svg" link="/v3/components/file-tree"]
Auto-detected icons, CLI tree format support, and symlink display.
[/doc-card]
[doc-card title="30,000+ Icons" icon="tabler/icons.svg" link="/v3/components/icons"]
Tabler, Heroicons, Bootstrap, Lucide, and more icon sets available.
[/doc-card]
[/doc-grid]

## API Documentation

[doc-grid]
[doc-card title="Endpoint Templates" icon="tabler/api.svg" link="/v3/api-reference"]
Method badges (GET, POST, PUT, DELETE), endpoint paths, and parameter tables.
[/doc-card]
[doc-card title="Request & Response" icon="tabler/code-dots.svg"]
JSON-formatted examples with syntax highlighting and response code documentation.
[/doc-card]
[/doc-grid]

## Versioning

[doc-grid]
[doc-card title="Folder-Based Versions" icon="tabler/git-branch.svg" link="/v3/guides/versioning"]
Organize docs by version (v1/, v2/, v3/) with automatic detection or manual configuration.
[/doc-card]
[doc-card title="Smart Switching" icon="tabler/switch-horizontal.svg"]
Version dropdown in sidebar with URL preservation when switching between versions.
[/doc-card]
[/doc-grid]

## Navigation & Structure

[doc-grid columns=3]
[doc-card title="Auto Sidebar" icon="tabler/layout-sidebar.svg"]
Generated from folder hierarchy with numeric ordering and collapsible sections.
[/doc-card]
[doc-card title="Scroll Spy TOC" icon="tabler/list-tree.svg"]
Right-side table of contents with active section highlighting as you scroll.
[/doc-card]
[doc-card title="Breadcrumbs" icon="tabler/bread.svg"]
Full navigation path display with configurable separators.
[/doc-card]
[/doc-grid]

## Additional Features

[doc-grid columns=3]
[doc-card title="GitHub Integration" icon="tabler/brand-github.svg"]
Edit links to your repository with customizable text and branch settings.
[/doc-card]
[doc-card title="HTMX Navigation" icon="tabler/bolt.svg"]
Optional SPA-like experience with XHR content loading.
[/doc-card]
[doc-card title="Prev/Next Links" icon="tabler/arrows-left-right.svg"]
Navigate between pages at the bottom of each content area.
[/doc-card]
[/doc-grid]

---

## Quick Start

```bash
# Install the theme
bin/gpm install helios

# Set as active theme
bin/grav theme helios
```

Or manually download and extract to your `user/themes/helios` folder.

---

## Support

Need help? Check out these resources:

[doc-grid columns=3]
[doc-card title="Grav Documentation" icon="tabler/book.svg" link="https://learn.getgrav.org"]
Official Grav CMS documentation and learning resources.
[/doc-card]
[doc-card title="Grav Discord" icon="tabler/brand-discord.svg" link="https://chat.getgrav.org"]
Join the community for help and discussion.
[/doc-card]
[doc-card title="GitHub Issues" icon="tabler/brand-github.svg" link="https://github.com/getgrav/grav/issues"]
Report bugs or request features.
[/doc-card]
[/doc-grid]
