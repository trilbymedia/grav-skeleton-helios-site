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
    - v3/
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

```grav
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

```grav
---
title: Regular Page
template: default
---
```

### Chapter Template

A section landing page that lists child pages:

```grav
---
title: Section Name
template: chapter
icon: folder-open   # Optional icon from SVG Icons plugin
description: Overview of this section  # Optional description
---

# Section Name

Introduction to this section...
```

### API Endpoint Template

For API documentation with method badges and parameter tables:

```grav
---
title: Create User
template: api-endpoint
api:
  method: POST
  path: /users
  description: Creates a new user account
  parameters:
    - name: email
      type: string
      required: true
      description: User's email address
    - name: name
      type: string
      required: true
      description: User's display name
  request_example: |
    {
      "email": "user@example.com",
      "name": "John Doe"
    }
  response_example: |
    {
      "id": "usr_123",
      "email": "user@example.com",
      "name": "John Doe",
      "created_at": "2024-01-15T10:30:00Z"
    }
  response_codes:
    - code: 201
      description: User created successfully
    - code: 400
      description: Invalid request body
    - code: 409
      description: Email already exists
---
```

> [!TIP]
> Use the **API Doc Import** plugin to automatically generate API endpoint pages from OpenAPI/Swagger specifications.

## Adding Content

### Headings

Use markdown headings. They automatically appear in the on-page TOC:

```grav
## Main Section

### Subsection

#### Sub-subsection
```

### Code Blocks

Helios supports code blocks using either standard markdown or the Codesh plugin for enhanced syntax highlighting.

#### Markdown Code Blocks

Use fenced code blocks with a language identifier:

    ```javascript
    function hello() {
        console.log('Hello, World!');
    }
    ```

#### Codesh Shortcodes

For advanced features like line highlighting, filenames, and tabbed groups, use the Codesh shortcode:

[raw]
```grav
[codesh lang="javascript" filename="hello.js" highlight="2"]
function hello() {
    console.log('Hello, World!');
}
[/codesh]
```
[/raw]

Create tabbed code groups for multiple languages:

[raw]
```grav
[codesh-group sync="package-manager"]
[codesh lang="bash" title="npm"]
npm install my-package
[/codesh]
[codesh lang="bash" title="yarn"]
yarn add my-package
[/codesh]
[codesh lang="bash" title="pnpm"]
pnpm add my-package
[/codesh]
[/codesh-group]
```
[/raw]

See the [Code Blocks](/v3/components/code-blocks) page for all Codesh features.

### Callouts

Use GitHub-flavored markdown alerts for callout boxes:

```grav
> [!NOTE]
> This is an informational note.

> [!WARNING]
> This is a warning message.

> [!TIP]
> This is a helpful tip.
```

See the [Callouts](/v3/components/callouts) page for all available types.

## Testing Your Site

Start the Grav development server:

```bash
bin/grav server
```

This uses the Symfony CLI if installed, otherwise falls back to PHP's built-in server. Then open `http://localhost:8000` in your browser.

> [!NOTE]
> On first run, you may need to make the script executable: `chmod +x bin/grav`

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

- Explore the [Guides](/v3/guides) for in-depth tutorials
- Check out the [Components](/v3/components) for available UI elements
- See the [API Reference](/v3/api-reference) for API documentation examples
