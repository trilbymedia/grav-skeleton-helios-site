---
title: 'Keep it current'
chapter: Writing
minutes: 9
paywall: members
outline:
    - 'Why docs go stale, and the signs that a page has'
    - 'Changing docs in the same change as the code'
    - 'Versioned docs, and when you need them'
    - 'Try it: a short review routine for every release'
---

A page that was right last year and is wrong today does more harm than no page at all. The reader follows it, it fails, and they stop trusting the rest of your docs too.

===

## How docs go stale

Docs rarely go wrong all at once. An option gets renamed, a default changes, a screen in the admin moves a button, and the page that describes it stays as it was. Signs that a page has drifted:

- Screenshots that don't match what readers see
- Examples that print warnings about something being deprecated
- Questions from readers about steps the page says are simple

## Change the docs with the code

The most reliable way to keep docs current is to change them in the same change as the code. When the docs live in the same repository, a reviewer can ask "where is the docs change?" the same way they ask for a test.

> [!TIP]
> Add a line to your pull request template: "Docs updated, or not needed because...". It costs nothing and catches most drift before it ships.

## Versioned docs

When readers run different major versions at the same time, give each version its own set of pages. Helios does this with a version switcher: each version lives in its own folder, and a reader picks theirs from the sidebar. Keep only the versions people still use, and say clearly which one is current.

## Try it

Write a five-minute routine to run before every release: search your docs for every option, command and screen the release changes, and update or remove what you find. Put it in the release checklist so it happens every time.
