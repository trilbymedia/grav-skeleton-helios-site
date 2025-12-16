---
title: Quick Start
taxonomy:
    category: docs
---

# Quick Start

Get your documentation site up and running in minutes.

## Page Structure

Helios uses Grav's standard page structure. Documentation pages are organized in numbered folders:

[doc-file-tree]
- user/pages/
    - v1/
        - 01.home/
            - default.md
            - 02.getting-started/
                - chapter.md
                - 01.installation/
                    - doc.md
                - 02.configuration/
                    - doc.md
            - 03.guides/
                - chapter.md
[/doc-file-tree]

The numeric prefixes control the order in the sidebar navigation.

## Creating a Documentation Page

Create a new markdown file with YAML frontmatter:

```markdown
---
title: My Page Title
taxonomy:
    category: docs
---

# My Page Title

Your content goes here...
```

## Page Templates

Helios includes several templates:

### Default Template

The standard documentation page with sidebar, content, and TOC:

```markdown
---
title: Regular Page
template: default
---
```

### Chapter Template

A section landing page that lists child pages:

```markdown
---
title: Section Name
template: chapter
---

# Section Name

Introduction to this section...
```

### API Endpoint Template

For API documentation with method badges and parameter tables:

```markdown
---
title: Create User
template: api-endpoint
api:
  method: POST
  path: /users
  description: Creates a new user
  parameters:
    - name: email
      type: string
      required: true
---
```

## Adding Content

### Headings

Use markdown headings. They automatically appear in the on-page TOC:

```markdown
## Main Section

### Subsection

#### Sub-subsection
```

### Code Blocks

Specify the language for syntax highlighting:

    ```javascript
    function hello() {
        console.log('Hello, World!');
    }
    ```

### Callouts

Use GitHub-flavored markdown alerts for callout boxes:

```markdown
> [!NOTE]
> This is an informational note.

> [!WARNING]
> This is a warning message.
```

See the [Callouts](/v1/components/callouts) page for all available types.

## Testing Your Site

Start the built-in PHP server:

```bash
cd /path/to/your/grav
php -S localhost:8000 system/router.php
```

Then open `http://localhost:8000` in your browser.

## Building CSS

If you make changes to the theme's CSS, rebuild with:

```bash
cd user/themes/helios
npm install
npm run build
```

For development with hot reload:

```bash
npm run dev
```

## Next Steps

- Explore the [Guides](/guides) for in-depth tutorials
- Check out the [Components](/components) for available UI elements
- See the [API Reference](/api-reference) for API documentation examples
