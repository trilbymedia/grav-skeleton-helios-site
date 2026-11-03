---
title: 'Examples that run'
chapter: Writing
minutes: 11
paywall: members
outline:
    - 'What makes an example runnable, and what makes it fail'
    - 'Showing the output, so a reader knows it worked'
    - 'Placeholders a reader will actually notice'
    - 'Try it: test every example on your page from a clean start'
---

Readers trust examples more than prose. Many of them skip straight to the first code block, paste it, and only read the words around it when it fails. That makes the example the most important part of the page, and the part most worth testing.

===

## What makes an example run

An example runs when a reader can paste it into a fresh setup and get the result you promised. Most broken examples fail for one of a few reasons:

- **A missing step.** The example depends on something done earlier that the page never says, like a folder that has to exist.
- **Invented values.** A path, a name or a version that only exists on the writer's machine.
- **Partial code.** Three lines from the middle of a file, with no word on where they go.

Give every example everything it needs, or say plainly where it goes:

```yaml
# user/config/system.yaml
cache:
  enabled: true
  check:
    method: file
```

The comment on the first line tells the reader which file this is. Without it they have to guess.

## Show what happens next

After a command, show what the reader should see. It tells them it worked, and when it didn't, the difference between your output and theirs is often the answer.

```bash
bin/grav clearcache
```

```text
Clearing cache

Cleared:  /cache/*
Cleared:  /images/*

Touched: /user/config/system.yaml
```

## Placeholders a reader will notice

When a reader has to put in their own value, make it impossible to miss. `your-site-name` in angle brackets or capitals stands out. `example` does not, and people paste it as it is.

> [!WARNING]
> Never use a real-looking value as a placeholder for something secret, like an API key. Someone will paste it into production and spend an afternoon working out why nothing connects.

## Try it

Make a new, empty setup and follow your page from the top, pasting every example exactly as written. Fix each place you had to know something the page didn't tell you.
