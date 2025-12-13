---
title: Tabs
taxonomy:
    category: docs
---

# Tabs

Tabs help organize related content into switchable panels, reducing page length and improving navigation.

## Basic Tabs

Use the `[tabs]` shortcode to create tabbed content:

[tabs]
[tab title="macOS"]
### Installing on macOS

```bash
brew install grav
```

Or download the DMG from our website.
[/tab]
[tab title="Windows"]
### Installing on Windows

Download the installer from our website and run it.

Or use Chocolatey:

```bash
choco install grav
```
[/tab]
[tab title="Linux"]
### Installing on Linux

Use your package manager:

**Ubuntu/Debian:**
```bash
sudo apt install grav
```

**Fedora:**
```bash
sudo dnf install grav
```
[/tab]
[/tabs]

### Syntax

```markdown
[tabs]
[tab title="Tab 1"]
Content for tab 1...
[/tab]
[tab title="Tab 2"]
Content for tab 2...
[/tab]
[/tabs]
```

## Named Tab Groups

When you have multiple tab groups on a page, they operate independently:

**Database Setup:**

[tabs]
[tab title="MySQL"]
```sql
CREATE DATABASE myapp;
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL ON myapp.* TO 'user'@'localhost';
```
[/tab]
[tab title="PostgreSQL"]
```sql
CREATE DATABASE myapp;
CREATE USER myuser WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE myapp TO myuser;
```
[/tab]
[tab title="SQLite"]
```bash
touch database.sqlite
```

No additional setup required for SQLite.
[/tab]
[/tabs]

## Synced Tabs

Add a `name` attribute to sync tab selection across groups. When a user selects "Python" in one group, all groups with the same name switch to Python:

[tabs name="language"]
[tab title="JavaScript"]
**JavaScript Example:**
```javascript
console.log("Hello from JavaScript!");
```
[/tab]
[tab title="Python"]
**Python Example:**
```python
print("Hello from Python!")
```
[/tab]
[/tabs]

Another synced group:

[tabs name="language"]
[tab title="JavaScript"]
```javascript
const http = require('http');
http.createServer((req, res) => {
    res.end('Hello World');
}).listen(3000);
```
[/tab]
[tab title="Python"]
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return 'Hello World'
```
[/tab]
[/tabs]

### Sync Syntax

```markdown
[tabs name="my-sync-group"]
[tab title="Option A"]...content...[/tab]
[tab title="Option B"]...content...[/tab]
[/tabs]
```

## Default Tab

Set which tab is active by default:

[tabs]
[tab title="Basic"]
Basic configuration options.
[/tab]
[tab title="Advanced" default=true]
This tab is shown by default.

Advanced configuration options for power users.
[/tab]
[/tabs]

```markdown
[tab title="Advanced" default=true]
```

## Vertical Tabs

Use vertical tabs for longer content or when you have many options:

[tabs vertical=true]
[tab title="Overview"]
### Overview

A brief introduction to the feature.
[/tab]
[tab title="Installation"]
### Installation

Step-by-step installation instructions.
[/tab]
[tab title="Configuration"]
### Configuration

Detailed configuration options.
[/tab]
[tab title="Troubleshooting"]
### Troubleshooting

Common issues and solutions.
[/tab]
[/tabs]

## Tabs with Icons

Add icons to tab titles (requires SVG Icons plugin):

[tabs]
[tab title="Dashboard" icon="home"]
Dashboard content...
[/tab]
[tab title="Settings" icon="cog"]
Settings content...
[/tab]
[tab title="Users" icon="users"]
User management content...
[/tab]
[/tabs]

```markdown
[tab title="Dashboard" icon="home"]
```

## Nesting Content

Tabs can contain any markdown content, including:

[tabs]
[tab title="Tables"]
| Feature | Status |
|---------|--------|
| Dark Mode | Supported |
| Versioning | Supported |
| Search | Supported |
[/tab]
[tab title="Lists"]
- Item one
- Item two
  - Nested item
  - Another nested
- Item three
[/tab]
[tab title="Callouts"]
[notice]
This is a callout inside a tab!
[/notice]
[/tab]
[/tabs]

## Best Practices

1. **Keep tab titles short** - Use 1-3 words for tab titles
2. **Use synced tabs** - For language/OS selection across the page
3. **Order logically** - Put the most common option first
4. **Don't overuse** - If content isn't related, use separate sections instead
