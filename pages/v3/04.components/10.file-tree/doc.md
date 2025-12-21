---
title: File Tree
taxonomy:
    category: docs
---

# File Tree

The file tree component displays directory structures with appropriate file icons. It's useful for showing project layouts, explaining folder organization, or documenting file hierarchies.

## Basic Usage

Use markdown list syntax inside the [raw]`[doc-file-tree]`[/raw] shortcode. Use **4-space indentation** for nested items (standard markdown list nesting):

[doc-file-tree]
- themes
    - helios
        - css
            - site.css
        - templates
            - default.html.twig
            - partials
                - header.html.twig
                - footer.html.twig
        - helios.php
        - helios.yaml
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
- themes
    - helios
        - css
            - site.css
        - templates
            - default.html.twig
            - partials
                - header.html.twig
                - footer.html.twig
        - helios.php
        - helios.yaml
[/doc-file-tree]
```
[/raw]

## Highlighting Files

Wrap filenames in `**bold**` to highlight important files:

[doc-file-tree]
- user
    - config
        - **system.yaml**
        - site.yaml
    - pages
        - **default.md**
- **composer.json**
- README.md
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
- user
    - config
        - **system.yaml**
        - site.yaml
    - pages
        - **default.md**
- **composer.json**
- README.md
[/doc-file-tree]
```
[/raw]

## Adding Comments

Add descriptive text after filenames:

[doc-file-tree]
- src
    - config.js your site configuration
    - content/ markdown content files
- .env environment variables (do not commit!)
- package.json project dependencies
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
- src
    - config.js your site configuration
    - content/ markdown content files
- .env environment variables (do not commit!)
- package.json project dependencies
[/doc-file-tree]
```
[/raw]

## Placeholders

Use `...` to indicate additional files that aren't shown:

[doc-file-tree]
- user
    - plugins
        - admin/
        - shortcode-core/
        - ...
    - pages
        - 01.home/
        - 02.docs/
        - ...
- ...
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
- user
    - plugins
        - admin/
        - shortcode-core/
        - ...
    - pages
        - 01.home/
        - 02.docs/
        - ...
- ...
[/doc-file-tree]
```
[/raw]

## Directory Notation

Directories are auto-detected, but you can explicitly mark them with a trailing `/`:

[doc-file-tree]
- assets/
- backup/
- cache/
- images/
- logs/
- user/
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
- assets/
- backup/
- cache/
- images/
- logs/
- user/
[/doc-file-tree]
```
[/raw]

## Complete Example

A typical Grav project structure:

[doc-file-tree]
- user
    - accounts/
    - config
        - **site.yaml** main site configuration
        - system.yaml
        - themes/
    - data/
    - pages
        - 01.home
            - default.md
        - 02.about
            - default.md
        - ...
    - plugins/
    - themes
        - **helios** your active theme
            - css/
            - js/
            - templates/
            - helios.php
            - helios.yaml
- .htaccess
- index.php
- ...
[/doc-file-tree]

## CLI Tree Format

You can also paste output directly from the `tree` command. The shortcode automatically detects the ASCII tree characters (`├──`, `└──`, `│`) and parses them:

[doc-file-tree]
.
├── assets
│   ├── page-toc-anchors.css
│   ├── page-toc-anchors.js
│   └── page-toc.png
├── blueprints
│   └── page-toc.yaml
├── classes
│   └── PageToc.php
├── blueprints.yaml
├── CHANGELOG.md
└── page-toc.php
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
.
├── assets
│   ├── page-toc-anchors.css
│   ├── page-toc-anchors.js
│   └── page-toc.png
├── blueprints
│   └── page-toc.yaml
├── classes
│   └── PageToc.php
├── blueprints.yaml
├── CHANGELOG.md
└── page-toc.php
[/doc-file-tree]
```
[/raw]

Symlinks are automatically detected and shown as comments:

[doc-file-tree]
├── admin -> /Projects/grav/grav-plugin-admin
├── flex-objects -> /Projects/grav/grav-plugin-flex-objects
└── login -> /Projects/grav/grav-plugin-login
[/doc-file-tree]

[raw]
```markdown
[doc-file-tree]
├── admin -> /Projects/grav/grav-plugin-admin
├── flex-objects -> /Projects/grav/grav-plugin-flex-objects
└── login -> /Projects/grav/grav-plugin-login
[/doc-file-tree]
```
[/raw]

## Syntax Reference

| Syntax | Description |
|--------|-------------|
| `- filename.ext` | Regular file |
| `- foldername` | Directory (auto-detected) |
| `- foldername/` | Explicit directory |
| `- **filename**` | Highlighted file |
| `- filename comment text` | File with comment |
| `- ...` | Placeholder for more files |
| 4-space indent | Nested items (standard markdown) |
| `├──`, `└──`, `│` | CLI tree format (auto-detected) |
| `name -> target` | Symlink (CLI tree format) |

## Supported File Icons

The component automatically assigns icons based on file extensions:

| Type | Extensions |
|------|------------|
| JavaScript | `.js`, `.mjs`, `.jsx` |
| TypeScript | `.ts`, `.tsx` |
| PHP | `.php` |
| Python | `.py` |
| HTML | `.html`, `.htm` |
| CSS | `.css`, `.scss`, `.sass` |
| Markdown | `.md`, `.mdx` |
| JSON/YAML | `.json`, `.yaml`, `.yml` |
| Images | `.svg`, `.png`, `.jpg`, `.gif` |
| Config | `.env`, `.ini`, `.toml` |
