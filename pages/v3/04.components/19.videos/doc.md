---
title: Videos
taxonomy:
    category: docs
---

# Videos

Responsive video embeds for YouTube, Vimeo, and local video files. Videos maintain their aspect ratio and scale to fill the available width.

## YouTube

Embed a YouTube video by providing the URL:

[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" title="Example YouTube Video"]

[raw]
```markdown
[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" title="Example YouTube Video"]
```
[/raw]

YouTube uses the privacy-enhanced `youtube-nocookie.com` embed domain by default.

### Supported YouTube URL Formats

All of these formats are recognized:

[raw]
```markdown
[doc-video url="https://www.youtube.com/watch?v=VIDEO_ID"]
[doc-video url="https://youtu.be/VIDEO_ID"]
[doc-video url="https://www.youtube.com/embed/VIDEO_ID"]
[doc-video url="https://www.youtube.com/shorts/VIDEO_ID"]
```
[/raw]

## Vimeo

Embed a Vimeo video:

[doc-video url="https://vimeo.com/76979871" title="Example Vimeo Video"]

[raw]
```markdown
[doc-video url="https://vimeo.com/76979871" title="Example Vimeo Video"]
```
[/raw]

## Aspect Ratios

Four aspect ratios are available. The default is `16:9`.

### 16:9 (default)

[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" ratio="16:9"]

### 4:3

[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" ratio="4:3"]

### 1:1

[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" ratio="1:1"]

[raw]
```markdown
[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" ratio="16:9"]
[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" ratio="4:3"]
[doc-video url="https://www.youtube.com/watch?v=dQw4w9WgXcQ" ratio="1:1"]
```
[/raw]

## Playback Options

Control autoplay, loop, and mute behavior:

[raw]
```markdown
[doc-video url="https://www.youtube.com/watch?v=VIDEO_ID" autoplay=true muted=true]
[doc-video url="https://www.youtube.com/watch?v=VIDEO_ID" loop=true]
[doc-video url="https://www.youtube.com/watch?v=VIDEO_ID" autoplay=true loop=true muted=true]
```
[/raw]

> [!NOTE]
> Most browsers require `muted=true` for autoplay to work.

## Local Video

For self-hosted video files, use the `src` parameter instead of `url`:

[raw]
```markdown
[doc-video src="video.mp4" title="Local Video"]
[doc-video src="video.mp4" autoplay=true loop=true muted=true]
```
[/raw]

Local videos render as a `<video>` element with native browser controls.

## Parameters

| Parameter  | Required | Default | Description |
|------------|----------|---------|-------------|
| `url`      | No*      | —       | YouTube or Vimeo URL |
| `src`      | No*      | —       | Local video file path |
| `title`    | No       | —       | Accessible title for the video |
| `ratio`    | No       | `16:9`  | Aspect ratio: `16:9`, `4:3`, `1:1`, `9:16` |
| `autoplay` | No       | `false` | Auto-start playback |
| `loop`     | No       | `false` | Loop the video |
| `muted`    | No       | `false` | Mute the audio |
| `classes`  | No       | —       | Extra CSS classes |

\* Either `url` or `src` is required.
