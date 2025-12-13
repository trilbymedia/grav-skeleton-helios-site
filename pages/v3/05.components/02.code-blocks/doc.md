---
title: Code Blocks
taxonomy:
    category: docs
---

# Code Blocks

Helios provides beautiful syntax highlighting for code blocks with additional features like copy buttons and line highlighting.

## Basic Syntax Highlighting

Specify the language after the opening backticks:

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

const message = greet('World');
console.log(message);
```

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("World")
print(message)
```

```php
<?php

function greet($name) {
    return "Hello, {$name}!";
}

$message = greet('World');
echo $message;
```

## Supported Languages

Helios supports 100+ languages via Prism.js, including:

| Language | Identifier |
|----------|------------|
| JavaScript | `javascript`, `js` |
| TypeScript | `typescript`, `ts` |
| Python | `python`, `py` |
| PHP | `php` |
| Ruby | `ruby`, `rb` |
| Go | `go` |
| Rust | `rust` |
| Shell/Bash | `bash`, `shell` |
| SQL | `sql` |
| YAML | `yaml` |
| JSON | `json` |
| HTML | `html` |
| CSS | `css` |
| Markdown | `markdown`, `md` |

## Copy Button

All code blocks include a copy button in the top-right corner. Click it to copy the code to your clipboard.

This feature is enabled by default:

```yaml
code:
  copy_button: true
```

## Line Numbers

Enable line numbers globally or per-block:

```yaml
code:
  line_numbers: true
```

```javascript {.line-numbers}
// This block has line numbers
const a = 1;
const b = 2;
const c = a + b;
console.log(c);
```

## Line Highlighting

Highlight specific lines to draw attention:

```javascript {highlight="2,4-6"}
function processData(data) {
    const filtered = data.filter(item => item.active);  // Highlighted

    const mapped = filtered.map(item => ({              // Highlighted
        id: item.id,                                     // Highlighted
        name: item.name.toUpperCase()                    // Highlighted
    }));

    return mapped;
}
```

Syntax: `{highlight="LINE_NUMBERS"}` where LINE_NUMBERS can be:
- Single lines: `1,3,5`
- Ranges: `2-4`
- Combined: `1,3-5,8`

## Inline Code

Use single backticks for inline code: `const x = 1;`

Inline code is styled with a subtle background:

```markdown
Use the `greet()` function to say hello.
```

Result: Use the `greet()` function to say hello.

## Code Tabs

Show the same code in multiple languages:

[codetabs]
```bash
curl -X POST https://api.example.com/users \
  -H "Authorization: Bearer TOKEN" \
  -d '{"name": "John"}'
```

```javascript
const response = await fetch('https://api.example.com/users', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer TOKEN',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ name: 'John' })
});
```

```python
import requests

response = requests.post(
    'https://api.example.com/users',
    headers={'Authorization': 'Bearer TOKEN'},
    json={'name': 'John'}
)
```

```php
$response = Http::withToken('TOKEN')
    ->post('https://api.example.com/users', [
        'name' => 'John'
    ]);
```
[/codetabs]

## Diff Highlighting

Show code changes with diff syntax:

```diff
- const greeting = 'Hello';
+ const greeting = 'Hello, World!';

function sayHello() {
-   console.log(greeting);
+   console.log(`${greeting} How are you?`);
}
```

## Terminal Output

Use the `bash` or `shell` language for terminal commands and output:

```bash
$ npm install helios-theme
+ helios-theme@2.1.0
added 42 packages in 3.2s

$ npm run build
> Building CSS...
> Done in 1.5s
```

## Configuration

Customize code block behavior in your theme configuration:

```yaml
code:
  theme: github-dark        # Prism theme name
  copy_button: true         # Enable copy button
  line_numbers: false       # Show line numbers by default
  highlight_lines: true     # Enable line highlighting
```
