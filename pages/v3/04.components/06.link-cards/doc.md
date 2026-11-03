---
title: Link Cards
taxonomy:
    category: docs
---

# Link Cards

Link preview cards for external resources, further reading, or related pages. Each card displays a title, optional description, and an arrow indicator.

## Basic Link Card

[doc-link-card href="https://getgrav.org" title="Grav CMS" description="Modern open-source flat-file CMS"]

[raw]
```markdown
[doc-link-card href="https://getgrav.org" title="Grav CMS" description="Modern open-source flat-file CMS"]
```
[/raw]

## With Icon

Add an icon to make link cards more recognizable:

[doc-link-card href="https://github.com" title="GitHub" description="Where the world builds software" icon="tabler/brand-github.svg"]

[raw]
```markdown
[doc-link-card href="https://github.com" title="GitHub" description="Where the world builds software" icon="tabler/brand-github.svg"]
```
[/raw]

## Without Description

Link cards work with just a title:

[doc-link-card href="https://learn.getgrav.org" title="Grav Documentation"]

[raw]
```markdown
[doc-link-card href="https://learn.getgrav.org" title="Grav Documentation"]
```
[/raw]

## Internal Links

Use internal paths and disable new tab for in-site navigation:

[doc-link-card href="/v3/getting-started/installation" title="Installation Guide" description="Get up and running with Helios" icon="tabler/download.svg" new-tab=false]

[raw]
```markdown
[doc-link-card href="/v3/getting-started/installation" title="Installation Guide" description="Get up and running with Helios" icon="tabler/download.svg" new-tab=false]
```
[/raw]

## Multiple Link Cards

Stack link cards for a "further reading" section:

[doc-link-card href="https://getgrav.org/downloads" title="Downloads" description="Get the latest version of Grav" icon="tabler/download.svg"]

[doc-link-card href="https://getgrav.org/premium" title="Premium" description="Explore premium plugins and themes" icon="tabler/star.svg"]

[doc-link-card href="https://discord.gg/grav" title="Community" description="Join the Grav community on Discord" icon="tabler/messages.svg"]

[raw]
```markdown
[doc-link-card href="https://getgrav.org/downloads" title="Downloads" description="Get the latest version of Grav" icon="tabler/download.svg"]

[doc-link-card href="https://getgrav.org/premium" title="Premium" description="Explore premium plugins and themes" icon="tabler/star.svg"]

[doc-link-card href="https://discord.gg/grav" title="Community" description="Join the Grav community on Discord" icon="tabler/messages.svg"]
```
[/raw]

## Parameters

| Parameter     | Required | Default | Description |
|---------------|----------|---------|-------------|
| `href`        | Yes      | —       | URL to link to |
| `title`       | Yes      | —       | Card title |
| `description` | No       | —       | Short description text |
| `icon`        | No       | —       | Icon path (e.g., `tabler/star.svg`) |
| `new-tab`     | No       | `true`  | Open link in new tab |
