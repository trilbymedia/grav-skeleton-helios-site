---
title: 'Code Blocks'
taxonomy:
    category:
        - docs
sitemap:
    lastmod: '20-12-2025 21:15'
yetisearch-pro: {  }
---

# Server-Side Syntax Highlighting

[Codesh](https://github.com/trilbymedia/grav-plugin-codesh) for Grav is a plugin that provides server-side syntax highlighting for code blocks in your Grav site.

Codesh provides server-side syntax highlighting using [Phiki](https://phiki.dev), a PHP port of Shiki that uses TextMate grammars and VS Code themes. All highlighting happens on the server - no JavaScript required, faster page loads, and perfect SEO.

## Basic Syntax Highlighting

> [!TIP]
> View the markdown source for this page to see the raw syntax.

Use the `[raw][codesh][/raw]` shortcode with the language as a shorcode parameter rusulting in:

[codesh =javascript]
function greet(name) {
    return `Hello, ${name}!`;
}

const message = greet('World');
console.log(message);
[/codesh]
[codesh =python]
def greet(name):
    return f"Hello, {name}!"

message = greet("World")
print(message)
[/codesh]
[codesh =php]
<?php

function greet($name) {
    return "Hello, {$name}!";
}

$message = greet('World');
echo $message;
[/codesh]
## Wrapping Markdown Code Blocks

For compatibility with markdown editors, you can wrap standard fenced code blocks:

```rust
fn main() {
    println!("Hello, Rustaceans!");
}
```

## Supported Languages

Codesh supports 200+ languages via TextMate grammars, including:

| Language | Identifier |
| --- | --- |
| JavaScript | `javascript`, `js` |
| TypeScript | `typescript`, `ts` |
| Python | `python`, `py` |
| PHP | `php` |
| Ruby | `ruby`, `rb` |
| Go | `go` |
| Grav | `grav` |
| Rust | `rust`, `rs` |
| Shell/Bash | `bash`, `shell`, `sh` |
| SQL | `sql` |
| YAML | `yaml`, `yml` |
| JSON | `json` |
| HTML | `html` |
| CSS | `css` |
| Markdown | `markdown`, `md` |
| Swift | `swift` |
| Kotlin | `kotlin`, `kt` |
| And 180+ more... |  |

## Line Numbers

Enable line numbers with the `line-numbers` attribute:

[codesh lang="javascript" line-numbers="true"]
// This block has line numbers
const a = 1;
const b = 2;
const c = a + b;
console.log(c);
[/codesh]
### Custom Starting Line

Start from a specific line number:

[codesh lang="python" line-numbers="true" start="10"]
# Starting from line 10
def calculate(x, y):
    return x + y

result = calculate(5, 3)
[/codesh]
## Line Highlighting

Highlight specific lines to draw attention using `highlight` or `hl`:

[codesh lang="javascript" line-numbers="true" highlight="2,4-6"]
function processData(data) {
    const filtered = data.filter(item => item.active);

    const mapped = filtered.map(item => ({
        id: item.id,
        name: item.name.toUpperCase()
    }));

    return mapped;
}
[/codesh]
Syntax: `highlight="LINE_NUMBERS"` where LINE_NUMBERS can be:

- Single lines: `1,3,5`
- Ranges: `2-4`
- Combined: `1,3-5,8`

## Line Focus

Focus on specific lines by dimming non-focused lines:

[codesh lang="javascript" line-numbers="true" focus="3-5"]
function example() {
    // setup code
    const important = true;
    doSomething(important);
    return important;
    // cleanup code
}
[/codesh]
This is useful for drawing attention to the most important parts of longer code examples.

## Title/Filename Display

Show a filename or custom title in the header instead of the language:

[codesh lang="php" title="src/Controller/UserController.php"]
<?php

namespace App\Controller;

class UserController extends AbstractController
{
    public function index(): Response
    {
        return $this->render('user/index.html.twig');
    }
}
[/codesh]
## Hide Language Badge

Hide the language badge entirely with `hide-lang="true"`:

[codesh lang="bash" hide-lang="true"]
npm install
npm run build
[/codesh]
## Minimal Mode (No Header)

Hide the entire header bar for a super minimal look with `hide-header="true"`:

[codesh lang="javascript" hide-header="true"]
const minimal = true;
console.log('No header, just code');
[/codesh]
## Automatic Light/Dark Mode

Codesh automatically detects your theme's light/dark mode setting and uses the appropriate syntax theme. When you toggle the theme, the code blocks switch automatically.

- In **light mode**: Uses the `theme_light` setting (default: `helios-light`)
- In **dark mode**: Uses the `theme_dark` setting (default: `helios-dark`)

## Custom Themes

Override the default theme per code block:

### GitHub Dark (default)

[codesh lang="typescript" theme="github-dark"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### Dracula

[codesh lang="typescript" theme="dracula"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### Nord

[codesh lang="typescript" theme="nord"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### One Dark Pro

[codesh lang="typescript" theme="one-dark-pro"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### Tokyo Night

[codesh lang="typescript" theme="tokyo-night"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### Catppuccin Mocha

[codesh lang="typescript" theme="catppuccin-mocha"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### Rose Pine

[codesh lang="typescript" theme="rose-pine"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
### GitHub Light

[codesh lang="typescript" theme="github-light"]
interface User {
    id: number;
    name: string;
    email: string;
}
[/codesh]
## Available Themes

Codesh includes 70+ VS Code themes:

| Dark Themes | Light Themes |
| --- | --- |
| `github-dark`, `github-dark-dimmed` | `github-light` |
| `dracula`, `dracula-soft` | `one-light` |
| `nord` | `solarized-light` |
| `one-dark-pro` | `catppuccin-latte` |
| `monokai` | `vitesse-light` |
| `tokyo-night` | `min-light` |
| `catppuccin-mocha`, `catppuccin-macchiato` | `gruvbox-light-*` |
| `rose-pine`, `rose-pine-moon` | `rose-pine-dawn` |
| `material-theme-*` variants | `material-theme-lighter` |
| `vitesse-dark`, `vitesse-black` | `snazzy-light` |
| `ayu-dark` | `everforest-light` |
| `night-owl` |  |
| `poimandres` |  |
| `houston` |  |
| `synthwave-84` |  |
| `vesper` |  |

## Terminal Output

Use `bash` or `shell` for terminal commands:

[codesh =bash]
$ npm install codesh-plugin
+ codesh-plugin@1.0.0
added 10 packages in 2.1s

$ npm run build
> Building assets...
> Done in 1.2s
[/codesh]
## Diff Highlighting

Show code changes with diff (`diff=true`) syntax:

[codesh diff="true"]
- const greeting = 'Hello';
+ const greeting = 'Hello, World!';

function sayHello() {
-   console.log(greeting);
+   console.log(`${greeting} How are you?`);
}
[/codesh]

## Code Groups

Display multiple code examples in a tabbed interface. Perfect for showing the same functionality in different languages.

### Basic Code Group

[codesh-group]
[codesh lang="javascript" title="helloWorld.js"]
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet("World"));
[/codesh]
[codesh lang="python" title="hello_world.py"]
def greet(name):
    return f"Hello, {name}!"

print(greet("World"))
[/codesh]
[codesh lang="php" title="HelloWorld.php"]
<?php

function greet($name) {
    return "Hello, {$name}!";
}

echo greet("World");
[/codesh]

[/codesh-group]
### Synced Code Groups

Use the `sync` attribute to synchronize tab selection across multiple code groups on the same page. When you select a tab in one group, all groups with the same sync key switch to match.

**Variable Declaration:**

[codesh-group sync="lang"]
[codesh lang="javascript" title="JavaScript"]
const name = "World";
const greeting = `Hello, ${name}!`;
[/codesh]
[codesh lang="python" title="Python"]
name = "World"
greeting = f"Hello, {name}!"
[/codesh]
[codesh lang="php" title="PHP"]
$name = "World";
$greeting = "Hello, {$name}!";
[/codesh]

[/codesh-group]
**Output:**

[codesh-group sync="lang"]
[codesh lang="javascript" title="JavaScript"]
console.log(greeting);
// Output: Hello, World!
[/codesh]
[codesh lang="python" title="Python"]
print(greeting)
# Output: Hello, World!
[/codesh]
[codesh lang="php" title="PHP"]
echo $greeting;
// Output: Hello, World!
[/codesh]

[/codesh-group]
Tab selections are automatically persisted, so they survive page reloads.

## Why Codesh?

| Feature | Benefit |
| --- | --- |
| Server-side rendering | No JavaScript required, instant display |
| 200+ languages | Comprehensive language support |
| 70+ VS Code themes | Beautiful, familiar syntax themes |
| Built-in line highlighting | Highlight specific lines easily |
| Built-in line focus | Draw attention to key code sections |
| TextMate grammars | Accurate, industry-standard highlighting |
| SEO-friendly | Code is in the HTML, fully indexable |

## Shortcode Attributes Reference

| Attribute | Description | Example |
| --- | --- | --- |
| `lang` | Programming language | `lang="php"` |
| `theme` | Override syntax theme | `theme="dracula"` |
| `line-numbers` | Show line numbers | `line-numbers="true"` |
| `start` | Starting line number | `start="10"` |
| `highlight` / `hl` | Lines to highlight | `highlight="1,3-5"` |
| `focus` | Lines to focus | `focus="2-4"` |
| `title` | Filename or title to display | `title="config.yaml"` |
| `hide-lang` | Hide the language badge | `hide-lang="true"` |
| `hide-header` | Hide the header bar | `hide-header="true"` |
| `class` | Additional CSS class | `class="my-class"` |

### Code Group Attributes

| Attribute | Description | Example |
| --- | --- | --- |
| `sync` | Sync key for tab synchronization | `sync="lang"` |

## Configuration

Configure defaults in `user/config/plugins/codesh.yaml`:

[codesh =yaml]
enabled: true
active: true
theme_dark: github-dark     # Theme for dark mode
theme_light: github-light   # Theme for light mode
show_line_numbers: false    # Show line numbers by default
process_markdown: true      # Auto-highlight markdown code blocks
[/codesh]