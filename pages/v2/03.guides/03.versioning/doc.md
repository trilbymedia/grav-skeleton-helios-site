---
title: Versioning
taxonomy:
    category: docs
---

# Versioning Guide

Helios supports folder-based documentation versioning, allowing you to maintain multiple versions of your documentation side by side.

## Folder Structure

Organize your documentation by version using folders:

```
user/pages/
├── docs/
│   ├── v1/
│   │   ├── getting-started/
│   │   ├── guides/
│   │   └── api/
│   └── v2/
│       ├── getting-started/
│       ├── guides/
│       └── api/
```

## Configuration

Enable versioning in your theme configuration:

```yaml
versioning:
  enabled: true
  root: docs              # Root folder containing versions
  default_version: v2     # Current/latest version
  show_badge: true        # Show version badge in header
```

## Version Switcher

When versioning is enabled, a dropdown appears in the sidebar header allowing users to switch between versions.

### How It Works

1. Helios scans the `root` folder for version folders (e.g., `v1`, `v2`)
2. The dropdown lists all discovered versions
3. When switching, Helios attempts to keep the user on the same page

### URL Preservation

When a user switches versions, Helios tries to find the equivalent page:

```
/docs/v1/guides/theming  ->  /docs/v2/guides/theming
```

If the page doesn't exist in the new version, the user lands on the version root.

## Version Naming

Version folders can use any naming convention:

```
# Semantic versions
v1.0/
v1.1/
v2.0/

# Simple versions
v1/
v2/

# Named versions
stable/
beta/
next/

# Date-based
2023/
2024/
```

## Default Version Redirect

Optionally redirect the root to the default version:

```yaml
# In your docs/default.md frontmatter
redirect: '/docs/v2'
```

Or create a docs/default.md that lists all versions:

```markdown
---
title: Documentation
template: chapter
---

# Documentation

Select a version:

- [Version 2 (Latest)](/docs/v2)
- [Version 1](/docs/v1)
```

## Version Badge

When `show_badge` is enabled, the current version appears in the header:

```yaml
versioning:
  show_badge: true
```

This helps users always know which version they're viewing.

## Version-Specific Configuration

Each version can have its own configuration by creating a version-specific config file:

```
user/config/themes/helios/
├── v1.yaml
└── v2.yaml
```

## Migration Guide Pattern

When releasing a new version, create a migration guide:

```
docs/v2/migration/
└── default.md
```

```markdown
---
title: Migrating from v1
---

# Migrating from v1 to v2

## Breaking Changes

- Feature X was removed
- API endpoint Y changed

## Upgrade Steps

1. Update configuration
2. Run migrations
3. Test functionality
```

## Best Practices

### 1. Keep Structure Consistent

Maintain the same page structure across versions when possible. This ensures the version switcher can find equivalent pages.

### 2. Document Deprecations

Clearly mark deprecated features in older versions:

```markdown
> [!WARNING]
> This feature is deprecated in v2. See the [Migration Guide](/docs/v2/migration).
```

### 3. Latest Version Default

Always set `default_version` to your latest stable release:

```yaml
versioning:
  default_version: v2
```

### 4. Archive Old Versions

For very old versions, consider archiving to a separate section:

```
docs/
├── v3/          # Current
├── v2/          # Previous
└── archived/
    ├── v1/
    └── v0/
```

### 5. Cross-Version Links

When linking between versions, use absolute paths:

```markdown
See the [v1 documentation](/docs/v1/guides/theming) for the old approach.
```
