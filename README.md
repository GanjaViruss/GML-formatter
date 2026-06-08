# GML Formatter — Allman & K&R

> Format your GameMaker Language code properly. No more mess.

**by [GanjaViruss](https://github.com/GanjaViruss) & Claude Opus 4.8 & Sonnet 4.6**

---

🔗 **[Manual Formatter Live](https://ganjaviruss.github.io/GML-formatter/)**

🔗 **[GML Auto Formatter Live](https://ganjaviruss.github.io/GML-formatter/batch.html)**
---

## What it does

Paste your messy GML code → get clean, readable code back.

- **Brace style** — Allman (braces on their own line) or K&R (braces on same line), your pick
- **Keyword operators** — `and` → `&&`, `or` → `||`, `not` → `!`, `mod` → `%`, `xor` → `^^`, `<>` → `!=`
- **Condition fixer** — wraps bare `if x > 0 {` into `if (x > 0) {`, fixes `=` → `==` inside conditions
- **Variable cleanup** — removes duplicate `var` declarations in the same scope (fixes GM2044 "local variable already declared")
- **Comment stripping** — optionally remove `//` comments (keeps `///` JSDoc) and `/* */` block comments
- **Proper indentation** — configurable (default 4 spaces)
- **Inline comments preserved** — `x = 1; // comment` stays on one line
- **Switch/case formatting** — correct indentation for case bodies
- **Template strings safe** — `$"text {var}"` never broken
- **Missing semicolons** — handles GML code without `;` (auto-detects statement boundaries)
- **Drag & drop** — drop a `.gml` file onto the page to load it
- **Auto-format on paste** — paste code and it formats instantly
- **Remembers settings** — language, brace style and options persist between visits
- **Live stats** — shows how many operators, conditions, var duplicates and comments were fixed
- **Mobile friendly** — responsive layout
- **Idempotent** — format twice, get the same result

## Features

| Feature | Description |
|---|---|
| Zero dependencies | No CDN, no npm, one `.html` file |
| Works offline | Open the file locally, no internet needed |
| PL / EN | Polish and English UI |
| Download | Export formatted code as `.gml` file |
| Idempotent | Safe to run multiple times |

## Usage

**Manual Formatter**
Just open `index.html` in any browser. No install, no server.

1. Paste GML code on the left.
2. Click **FORMAT** (or `Ctrl+Enter`)
3. Copy the clean code from the right.

You can also drag & drop a `.gml` file onto the page, or paste code and it formats automatically.

**GML Auto Formatter**

**WARRING!!!**
⚠️ This overwrites your .gml files in place. Make a backup or commit to git first. Scan the folder, review the count, then format. Closing GameMaker before running is recommended.

1. Open `batch.html` in Opera/Chrome/Edge browser. No install, no server.
2. Choose MAIN project folder (where is project_name.yyp file)
3. Click `Scan` and next `Format & Save (in place)`
4. Wait a while :P
5. DONE!



## Before / After

**Before:**
```gml
if work_data == undefined exit;
if !work_available and not work_paused and regen_timer > 0 {
regen_timer--;
if regen_timer<=0{
work_available=true;
sprite_index=work_data.sprite_idle;
}
}
```

**After:**
```gml
if (work_data == undefined) exit;
if (!work_available && !work_paused && regen_timer > 0)
{
    regen_timer--;
    if (regen_timer <= 0)
    {
        work_available = true;
        sprite_index = work_data.sprite_idle;
    }
}
```

## Supports

- `if / else if / else`
- `while / do..until / repeat`
- `for` loops
- `switch / case / default`
- `with`
- `function` declarations and expressions
- Template strings `$"..."` and verbatim strings `@"..."`
- Hex literals `$FF`
- GML accessors `[? ]` `[# ]` `[| ]` `[@ ]`
- `#macro` / `#region` / `#endregion`
- Inline and block comments
- Ternary `? :`
- Struct literals `{ key: value }`

## Known limitation

Bare single-line if without braces (`if x > 5 exit;`) — the formatter won't add parens here because it can't safely detect where the condition ends and the body begins. Add braces or parens manually for these.

## Built with AI

This tool was built with Claude (Opus 4.8 & Sonnet 4.6). I use GML myself, there was no solid formatter for it, people kept asking for one, so I built it and released it as free open source. The engine is a custom tokenizer and pretty-printer written specifically for GML — not a generic JS beautifier hacked with regexes.

## Changelog

**v1.5**
- Handles GML without semicolons (auto statement-boundary detection) — fixes glued statements/structs
- Batch formatter: format an entire project folder in one click (`batch.html`)
- Fixed edge case with `toString` / `constructor` as variable names

**v1.4**
- Optional comment stripping: `//` (keeps `///` JSDoc docs) and `/* */` block comments

**v1.3**
- Live stats: operators / conditions / var fixes / comments removed counter
- Responsive layout for mobile
- Bigger built-in example

**v1.2**
- Brace style choice: Allman / K&R
- Drag & drop file loading
- Auto-format on paste
- Settings persist between visits

**v1.1**
- Duplicate `var` cleanup (fixes GM2044 errors)
- Download button to export as `.gml`
- English default UI

**v1.0**
- Initial release: Allman formatting, operator conversion, condition fixing

## License

MIT — do whatever you want with it.
