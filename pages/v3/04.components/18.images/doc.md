---
title: Images
taxonomy:
    category: docs
---

# Images

Styled images with optional borders, shadows, captions, and a click-to-zoom lightbox. The `doc-image` shortcode wraps images in a `<figure>` element with consistent styling.

## Basic Image

A simple image with lightbox enabled by default (click to zoom):

[doc-image src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop" alt="Code on a laptop screen"]

[raw]
```markdown
[doc-image src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop" alt="Code on a laptop screen"]
```
[/raw]

## With Caption

Add a caption below the image:

[doc-image src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800&h=400&fit=crop" alt="Monitor showing code" caption="A developer's workspace with code on screen"]

[raw]
```markdown
[doc-image src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800&h=400&fit=crop" alt="Monitor showing code" caption="A developer's workspace with code on screen"]
```
[/raw]

## Border & Shadow

Add a border, shadow, or both for visual emphasis:

### Border Only

[doc-image src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800&h=400&fit=crop" alt="Laptop with code" border=true]

### Shadow Only

[doc-image src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800&h=400&fit=crop" alt="Laptop with code" shadow=true]

### Border + Shadow

[doc-image src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800&h=400&fit=crop" alt="Laptop with code" border=true shadow=true]

[raw]
```markdown
[doc-image src="image.jpg" border=true]
[doc-image src="image.jpg" shadow=true]
[doc-image src="image.jpg" border=true shadow=true]
```
[/raw]

## Constrained Width

Limit the image width with the `width` parameter:

[doc-image src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop" alt="Code example" width="400px" border=true caption="Image constrained to 400px"]

[raw]
```markdown
[doc-image src="image.jpg" width="400px" caption="Image constrained to 400px"]
```
[/raw]

## Without Lightbox

Disable the click-to-zoom behavior:

[doc-image src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=800&h=400&fit=crop" alt="Decorative image" lightbox=false]

[raw]
```markdown
[doc-image src="image.jpg" lightbox=false]
```
[/raw]

## Full Example

Combining multiple options:

[doc-image src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&h=400&fit=crop" alt="Complete example" caption="A fully styled image with all options" border=true shadow=true width="600px"]

[raw]
```markdown
[doc-image src="image.jpg" alt="Complete example" caption="A fully styled image with all options" border=true shadow=true width="600px"]
```
[/raw]

## Lightbox Controls

When clicking an image with lightbox enabled:
- **Click** the image to open the lightbox
- **Click** outside the image or the close button to dismiss
- Press **Escape** to close
- The lightbox works with HTMX page navigation

## Parameters

| Parameter  | Required | Default | Description |
|------------|----------|---------|-------------|
| `src`      | Yes      | —       | Image source path or URL |
| `alt`      | No       | —       | Alternative text for accessibility |
| `caption`  | No       | —       | Caption text displayed below the image |
| `border`   | No       | `false` | Show a border around the image |
| `shadow`   | No       | `false` | Add a shadow to the image |
| `lightbox` | No       | `true`  | Enable click-to-zoom lightbox |
| `width`    | No       | —       | Max width (e.g., `400px`, `50%`) |
| `classes`  | No       | —       | Extra CSS classes |
