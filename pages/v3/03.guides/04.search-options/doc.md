---
title: Search Options
taxonomy:
    category: docs
---

# Search Options

Helios supports two search providers: **SimpleSearch** (built-in) and **YetiSearch Pro** (advanced). This guide covers configuration and features for both.

## Choosing a Search Provider

Configure your search provider in `user/config/themes/helios.yaml`:

[codesh lang="yaml"]
search:
  enabled: true
  provider: simplesearch    # or 'yetisearch-pro'
  keyboard_shortcut: true   # Enable Cmd+K / Ctrl+K
  placeholder: 'Search documentation...'
  min_chars: 2
[/codesh]

| Provider | Best For |
|----------|----------|
| `simplesearch` | Small to medium sites, quick setup, no indexing required |
| `yetisearch-pro` | Large sites, fuzzy search, advanced features, chunked results |

---

## SimpleSearch

SimpleSearch is the default Grav search plugin. It performs real-time searches through your content without requiring an index.

### Installation

[codesh lang="bash"]
bin/gpm install simplesearch
[/codesh]

### Configuration

Create or edit `user/config/plugins/simplesearch.yaml`:

[codesh lang="yaml"]
enabled: true
built_in_css: false           # Helios provides its own styling
built_in_js: false            # Helios handles the search UI
display_button: false
min_query_length: 2
route: /search
template: simplesearch_results
filters:
  category: docs              # Only search pages with this taxonomy
search_content: rendered      # 'rendered' or 'raw'
[/codesh]

### Excluding Pages from SimpleSearch

To exclude a page from SimpleSearch results, add to the page frontmatter:

[codesh lang="yaml"]
simplesearch:
  process: false
[/codesh]

Or exclude pages by taxonomy in the plugin config:

[codesh lang="yaml"]
filters:
  category: docs
ignore_taxonomy:
  category: internal
[/codesh]

---

## YetiSearch Pro

YetiSearch Pro is an advanced local search engine with fuzzy matching, chunked indexing, and relevance scoring.

### Installation

YetiSearch Pro is a premium plugin. Once installed, enable it:

[codesh lang="yaml"]
# user/config/plugins/yetisearch-pro.yaml
enabled: true

engine:
  storage_dir: 'user://data/yetisearch-pro'
  index_prefix: 'docs_'

indexes:
  pages:
    strategy: per_language    # or 'single'
    options:
      fuzzy: true
      typo_tolerance: 2
[/codesh]

Then configure Helios to use it:

[codesh lang="yaml"]
# user/config/themes/helios.yaml
search:
  provider: yetisearch-pro
[/codesh]

### Indexing Content

YetiSearch Pro requires content to be indexed before searching. Use the CLI to build the index:

[codesh lang="bash" title="Index all content"]
bin/plugin yetisearch-pro index --index pages
[/codesh]

[codesh lang="bash" title="Flush and rebuild index"]
bin/plugin yetisearch-pro index --index pages --flush
[/codesh]

[codesh lang="bash" title="Index specific language/version"]
bin/plugin yetisearch-pro index --index pages --lang v3 --flush
[/codesh]

> [!TIP]
> Run indexing after significant content changes or set up a scheduled task for automatic reindexing.

### Realtime Indexing

YetiSearch Pro can automatically update the index when pages are saved in the Admin panel:

[codesh lang="yaml"]
# user/config/plugins/yetisearch-pro.yaml
_yetisearch_indexing:
  realtime: true              # Auto-index on page save
  smart_indexing: true        # Skip unchanged documents
[/codesh]

### Admin Dashboard

YetiSearch Pro provides an admin dashboard for monitoring index status and triggering reindexing. Access it via **Admin > YetiSearch Pro**.

From the dashboard you can:
- View index statistics (document count, size, last updated)
- Trigger manual reindexing
- Clear and rebuild indexes
- Browse indexed documents

---

## Excluding Content from YetiSearch Pro

YetiSearch Pro provides flexible options for excluding content from the search index.

### Page-Level Exclusion

To completely exclude a page from the search index, add to the page frontmatter:

[codesh lang="yaml"]
yetisearch:
  ignore: true
[/codesh]

Alternatively, use the toggle syntax:

[codesh lang="yaml"]
yetisearch:
  index-page: false
[/codesh]

Both achieve the same result. Use whichever feels more intuitive.

### Excluding Child Pages

To prevent all child pages of a section from being indexed:

[codesh lang="yaml"]
yetisearch:
  index-children: false
[/codesh]

This is useful for excluding entire sections like internal notes or draft content.

### Content-Level Exclusion

To exclude specific content within a page while indexing the rest, use the `[raw][yetisearch=ignore][/raw]` shortcode:

[yetisearch=ignore]
This content will NOT appear in search results. Use this for sensitive information, admin notes,
or content that shouldn't be discoverable via search. keyword to search for: Flibbertigibbet
[/yetisearch]

[codesh lang="markdown"]
This paragraph will be indexed and searchable.

[yetisearch=ignore]
This content will NOT appear in search results.
Use this for sensitive information, admin notes,
or content that shouldn't be discoverable via search.
[/yetisearch]

This paragraph will also be indexed.
[/codesh]

The excluded content still renders normally on the page—it's only hidden from search results.

> [!NOTE]
> The `[raw][yetisearch=ignore][raw]` shortcode requires the `shortcode-core` plugin to be installed.

### Admin UI

You can also control indexing via the Admin panel. Edit any page and look for the **Search Controls** tab to toggle indexing options.

---

## Search Query Tuning (YetiSearch Pro)

YetiSearch Pro supports advanced query configuration for fine-tuning relevance:

[codesh lang="yaml"]
indexes:
  pages:
    query_defaults:
      per_page: 10
      fields: [title, headers, content, excerpt, tags]
      boost:
        title: 5.0           # Boost title matches
        headers: 3.0         # Boost header matches
        tags: 2.5            # Boost tag matches
        excerpt: 2.0
        content: 1.0
[/codesh]

### Fuzzy Search

Enable fuzzy matching to find results even with typos:

[codesh lang="yaml"]
indexes:
  pages:
    options:
      fuzzy: true
      typo_tolerance: 2      # Allow up to 2 character mistakes
[/codesh]

---

## CLI Query Testing (YetiSearch Pro)

Test searches directly from the command line:

[codesh lang="bash" title="Basic search"]
bin/plugin yetisearch-pro query --q "installation guide" --index pages
[/codesh]

[codesh lang="bash" title="Fuzzy search with filters"]
bin/plugin yetisearch-pro query --q "configration" --fuzzy --index pages
[/codesh]

[codesh lang="bash" title="JSON output for debugging"]
bin/plugin yetisearch-pro query --q "theme" --index pages --raw
[/codesh]

---

## Comparison

| Feature | SimpleSearch | YetiSearch Pro |
|---------|--------------|------------|
| Setup complexity | Low | Medium |
| Indexing required | No | Yes |
| Fuzzy/typo tolerance | No | Yes |
| Chunked results | No | Yes |
| Relevance scoring | Basic | Advanced |
| Large site performance | Slower | Fast |
| Admin dashboard | No | Yes |
| Content-level exclusion | No | Yes |
| Realtime updates | Automatic | Configurable |

---

## Troubleshooting

### Search not returning results

**SimpleSearch:**
- Check that pages have the correct taxonomy (e.g., `category: docs`)
- Verify `search_content` is set to `rendered` if using shortcodes

**YetiSearch Pro:**
- Ensure the index has been built: `bin/plugin yetisearch-pro index --index pages`
- Check that pages aren't excluded via `yetisearch.ignore: true`
- Verify the index exists in `user/data/yetisearch-pro/`

### YetiSearch Pro index out of date

Rebuild the index after major content changes:

[codesh lang="bash"]
bin/plugin yetisearch-pro index --index pages --flush
[/codesh]

Or enable realtime indexing for automatic updates.

### Keyboard shortcut not working

Ensure keyboard shortcuts are enabled in the theme config:

[codesh lang="yaml"]
search:
  keyboard_shortcut: true
[/codesh]

The shortcut is `Cmd+K` (Mac) or `Ctrl+K` (Windows/Linux).
