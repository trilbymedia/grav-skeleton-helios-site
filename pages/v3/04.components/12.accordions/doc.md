---
title: Accordions
taxonomy:
    category: docs
---

# Accordions

Accordions let you organize content into collapsible sections. They're ideal for FAQs, long reference lists, and any content where users need to scan headings before diving into details.

## Basic Accordion

By default, only one item can be open at a time. Clicking a new item closes the previous one:

[doc-accordion]
[doc-accordion-item title="What is Grav?"]
Grav is a modern, flat-file CMS that doesn't require a database. It uses simple folder and file structures to manage content, making it fast, flexible, and easy to deploy.
[/doc-accordion-item]
[doc-accordion-item title="How do I install Grav?"]
Download the latest release from [getgrav.org](https://getgrav.org), extract it to your web server, and you're ready to go. No database setup or complex configuration required.
[/doc-accordion-item]
[doc-accordion-item title="Can I use Grav for documentation?"]
Absolutely! Grav excels at documentation sites. With themes like Helios, you get navigation, search, versioning, and component shortcodes out of the box.
[/doc-accordion-item]
[/doc-accordion]

[raw]
```markdown
[doc-accordion]
[doc-accordion-item title="What is Grav?"]
Grav is a modern, flat-file CMS that doesn't require a database...
[/doc-accordion-item]
[doc-accordion-item title="How do I install Grav?"]
Download the latest release from [getgrav.org](https://getgrav.org)...
[/doc-accordion-item]
[doc-accordion-item title="Can I use Grav for documentation?"]
Absolutely! Grav excels at documentation sites...
[/doc-accordion-item]
[/doc-accordion]
```
[/raw]

## First Item Open

Use `open="0"` to have the first item expanded by default (0-indexed):

[doc-accordion open="0"]
[doc-accordion-item title="Getting Started"]
Begin by installing Grav and choosing a theme. The Helios theme provides a complete documentation experience with built-in components, search, and version support.
[/doc-accordion-item]
[doc-accordion-item title="Configuration"]
All configuration is done through YAML files. The main site config lives in `user/config/system.yaml`, and theme settings are in `user/config/themes/helios.yaml`.
[/doc-accordion-item]
[doc-accordion-item title="Deployment"]
Deploy by copying files to your server, using Git, or with a CI/CD pipeline. Since there's no database, deployments are simple file syncs.
[/doc-accordion-item]
[/doc-accordion]

[raw]
```markdown
[doc-accordion open="0"]
[doc-accordion-item title="Getting Started"]
Begin by installing Grav and choosing a theme...
[/doc-accordion-item]
[doc-accordion-item title="Configuration"]
All configuration is done through YAML files...
[/doc-accordion-item]
[doc-accordion-item title="Deployment"]
Deploy by copying files to your server...
[/doc-accordion-item]
[/doc-accordion]
```
[/raw]

## Multiple Items Open

Add `independent=true` to allow multiple items to be open simultaneously:

[doc-accordion independent=true open="all"]
[doc-accordion-item title="Markdown Support"]
Grav uses full **Markdown** and **Markdown Extra** syntax. Write bold, italic, lists, tables, code blocks, and more using simple text formatting.
[/doc-accordion-item]
[doc-accordion-item title="Shortcode Support"]
[raw]Extend Markdown with shortcodes like `[doc-accordion]`, `[doc-tabs]`, `[doc-steps]`, and more. Shortcodes let you add rich components without writing HTML.[/raw]
[/doc-accordion-item]
[doc-accordion-item title="Twig Templating"]
Grav's template engine is Twig. Create custom layouts, partials, and macros to control every aspect of your site's presentation.
[/doc-accordion-item]
[/doc-accordion]

[raw]
```markdown
[doc-accordion independent=true open="all"]
[doc-accordion-item title="Markdown Support"]
Grav uses full **Markdown** and **Markdown Extra** syntax...
[/doc-accordion-item]
[doc-accordion-item title="Shortcode Support"]
Extend Markdown with shortcodes...
[/doc-accordion-item]
[doc-accordion-item title="Twig Templating"]
Grav's template engine is Twig...
[/doc-accordion-item]
[/doc-accordion]
```
[/raw]

## Rich Content

Accordion items can contain any Markdown content including code blocks, lists, and tables:

[doc-accordion open="0"]
[doc-accordion-item title="Code Example"]
Install dependencies and start the development server:

```bash
bin/grav install
bin/grav server
```

Your site will be available at `http://localhost:8000`.
[/doc-accordion-item]
[doc-accordion-item title="Configuration Options"]
| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `title` | string | — | Page title displayed in navigation |
| `taxonomy` | object | — | Categories and tags for the page |
| `visible` | boolean | `true` | Whether the page appears in navigation |
| `published` | boolean | `true` | Whether the page is publicly accessible |
[/doc-accordion-item]
[doc-accordion-item title="Nested Lists"]
Key features of Grav:

- **Performance** — No database means fast page loads
- **Flexibility** — Supports multiple content types
    - Documentation
    - Blogs
    - Landing pages
- **Developer-friendly** — CLI tools, Twig templating, plugin API
[/doc-accordion-item]
[/doc-accordion]

## FAQ Example

A common use case for accordions is an FAQ section:

[doc-accordion]
[doc-accordion-item title="Is Helios free to use?"]
Helios is a premium theme for Grav CMS. Check the official site for licensing details and pricing information.
[/doc-accordion-item]
[doc-accordion-item title="Does Helios support dark mode?"]
Yes! Helios includes full dark mode support that respects the user's system preference. Users can also toggle between light and dark mode manually using the theme switcher.
[/doc-accordion-item]
[doc-accordion-item title="Can I customize the colors?"]
Helios uses CSS custom properties for theming. You can override `--color-primary` and related variables to match your brand colors without modifying the theme source.
[/doc-accordion-item]
[doc-accordion-item title="Does it work with Grav plugins?"]
Helios is designed to work with the Grav ecosystem. It integrates with popular plugins like shortcode-core, page-toc, and search plugins out of the box.
[/doc-accordion-item]
[/doc-accordion]

[raw]
```markdown
[doc-accordion]
[doc-accordion-item title="Is Helios free to use?"]
Helios is a premium theme for Grav CMS...
[/doc-accordion-item]
[doc-accordion-item title="Does Helios support dark mode?"]
Yes! Helios includes full dark mode support...
[/doc-accordion-item]
[doc-accordion-item title="Can I customize the colors?"]
Helios uses CSS custom properties for theming...
[/doc-accordion-item]
[doc-accordion-item title="Does it work with Grav plugins?"]
Helios is designed to work with the Grav ecosystem...
[/doc-accordion-item]
[/doc-accordion]
```
[/raw]

## Parameters

### `doc-accordion`

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `open` | No | `none` | Which item(s) to open initially: `none`, `all`, or a 0-indexed number |
| `independent` | No | `false` | Allow multiple items to be open at the same time |

### `doc-accordion-item`

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `title` | Yes | — | The heading text displayed in the clickable trigger |
