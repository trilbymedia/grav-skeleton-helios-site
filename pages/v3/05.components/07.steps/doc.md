---
title: Steps
taxonomy:
    category: docs
---

# Steps

Steps display a numbered list of tasks or instructions with a visual timeline connecting them.

## Basic Steps

[doc-steps]
[doc-step]
Create a new Grav project:

```bash
bin/gpm install helios
```
[/doc-step]
[doc-step]
Configure your site settings in `user/config/site.yaml`.
[/doc-step]
[doc-step]
Start adding content to the `user/pages` directory.
[/doc-step]
[/doc-steps]

[raw]
```markdown
[doc-steps]
[doc-step]
Create a new Grav project:
bin/gpm install helios
[/doc-step]
[doc-step]
Configure your site settings in `user/config/site.yaml`.
[/doc-step]
[doc-step]
Start adding content to the `user/pages` directory.
[/doc-step]
[/doc-steps]
```
[/raw]

## Rich Content in Steps

Steps support full markdown including code blocks, lists, and more:

[doc-steps]
[doc-step]
**Install dependencies**

Choose your preferred package manager:

```bash
npm install
# or
yarn install
```
[/doc-step]
[doc-step]
**Configure the theme**

Create or edit `user/config/themes/helios.yaml`:

```yaml
appearance:
  mode: system
  color_preset: blue
navigation:
  sidebar_width: 280
  toc_enabled: true
```
[/doc-step]
[doc-step]
**Create your first page**

Add a new file at `user/pages/01.home/doc.md`:

```markdown
---
title: Home
---

# Welcome

Your documentation starts here.
```
[/doc-step]
[doc-step]
**Build and preview**

Run the development server:

```bash
bin/grav server
```

Open [http://localhost:8000](http://localhost:8000) to see your site.
[/doc-step]
[/doc-steps]

## Use Cases

Steps work great for:

- Installation guides
- Tutorial walkthroughs
- Setup instructions
- Multi-part processes
- Onboarding flows

## Styling

Steps automatically:
- Number each step sequentially
- Connect steps with a vertical timeline
- Highlight step numbers with your theme's primary color
- Support dark mode
