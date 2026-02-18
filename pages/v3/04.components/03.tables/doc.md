---
title: Tables
taxonomy:
    category: docs
---

# Tables

Helios provides clean, responsive table styling for presenting data in your documentation.

## Basic Tables

Use standard markdown table syntax:

| Feature | Description | Status |
|---------|-------------|--------|
| Dark Mode | System preference with manual toggle | Available |
| Search | Full-text search with keyboard shortcuts | Available |
| Versioning | Folder-based documentation versions | Available |
| API Docs | Method badges and parameter tables | Available |

```markdown
| Feature | Description | Status |
|---------|-------------|--------|
| Dark Mode | System preference with manual toggle | Available |
| Search | Full-text search with keyboard shortcuts | Available |
```

## Column Alignment

Control column alignment with colons in the separator:

| Left-aligned | Center-aligned | Right-aligned |
|:-------------|:--------------:|--------------:|
| Text | Text | Text |
| More text | More text | More text |
| Even more | Even more | Even more |

```markdown
| Left-aligned | Center-aligned | Right-aligned |
|:-------------|:--------------:|--------------:|
```

## Wide Tables

Wide tables automatically scroll horizontally on small screens:

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `email` | string | Yes | - | User's email address |
| `name` | string | Yes | - | Display name |
| `password` | string | Yes | - | Password (min 8 chars) |
| `role` | string | No | `user` | User role (admin, user, viewer) |
| `team_id` | string | No | `null` | Team to assign user to |
| `send_invite` | boolean | No | `true` | Send invitation email |

## Striped Tables

Add the striped class for alternating row colors:

[div class="table-striped"]

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/users` | List all users |
| GET | `/users/{id}` | Get single user |
| POST | `/users` | Create user |
| PUT | `/users/{id}` | Update user |
| DELETE | `/users/{id}` | Delete user |

[/div]

## Compact Tables

Use the compact class for denser tables:

[div class="table-compact"]

| Code | Status | Meaning |
|------|--------|---------|
| 200 | OK | Request succeeded |
| 201 | Created | Resource created |
| 400 | Bad Request | Invalid input |
| 401 | Unauthorized | Invalid credentials |
| 404 | Not Found | Resource not found |
| 500 | Server Error | Internal error |

[/div]

## Tables with Code

Tables can contain inline code:

| Option | Type | Example |
|--------|------|---------|
| `enabled` | boolean | `true` |
| `debug` | boolean | `false` |
| `theme` | string | `"default"` |
| `port` | number | `3000` |

## Complex Tables

For more complex tables, use HTML:

<table>
<thead>
<tr>
<th>Feature</th>
<th>Free</th>
<th>Pro</th>
<th>Enterprise</th>
</tr>
</thead>
<tbody>
<tr>
<td>Users</td>
<td>5</td>
<td>50</td>
<td>Unlimited</td>
</tr>
<tr>
<td>Storage</td>
<td>1 GB</td>
<td>100 GB</td>
<td>Unlimited</td>
</tr>
<tr>
<td>API Requests</td>
<td>1,000/day</td>
<td>50,000/day</td>
<td>Unlimited</td>
</tr>
<tr>
<td>Support</td>
<td>Community</td>
<td>Email</td>
<td>24/7 Priority</td>
</tr>
</tbody>
</table>

## Responsive Behavior

On mobile devices, wide tables become horizontally scrollable. The table header remains visible while scrolling.

Test this by resizing your browser window.

## Styling Tables

Customize table styles in your CSS:

```css
/* Custom table styling */
.prose table {
    @apply text-sm;
}

.prose th {
    @apply bg-primary text-white;
}

.prose td {
    @apply border-gray-200 dark:border-gray-700;
}
```

## Best Practices

1. **Keep it simple** - Use tables for tabular data, not layout
2. **Align numbers right** - Makes comparison easier
3. **Use consistent formatting** - Same data types should look the same
4. **Add headers** - Always include a header row
5. **Keep cells concise** - Long content should be in paragraphs, not tables
