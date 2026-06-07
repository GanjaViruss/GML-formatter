# GML Formatter — Allman & K&R

> Format your GameMaker Language code properly. No more mess.

**by [GanjaViruss](https://github.com/GanjaViruss) & Claude Opus 4.8 & Sonnet 4.6**

---

🔗 **[Live demo](https://ganjaviruss.github.io/GML-formatter/)**

---

## What it does

Paste your messy GML code → get clean, readable code back.

- **Brace style** — Allman (braces on their own line) or K&R (braces on same line), your pick
- **Keyword operators** — `and` → `&&`, `or` → `||`, `not` → `!`, `mod` → `%`, `xor` → `^^`, `<>` → `!=`
- **Condition fixer** — wraps bare `if x > 0 {` into `if (x > 0) {`, fixes `=` → `==` inside conditions
- **Variable cleanup** — removes duplicate `var` declarations in the same scope (fixes GM2044 "local variable already declared")
- **Proper indentation** — configurable (default 4 spaces)
- **Inline comments preserved** — `x = 1; // comment` stays on one line
- **Switch/case formatting** — correct indentation for case bodies
- **Template strings safe** — `$"text {var}"` never broken
- **Drag & drop** — drop a .gml file onto the page to load it
- **Auto-format on paste** — paste code and it formats instantly
- **Remembers settings** — language, brace style and options persist between visits
- **Live stats** — shows how many operators, conditions and var duplicates were fixed
- **Mobile friendly** — responsive layout
- **Idempotent** — format twice, get the same result

## Features

| Feature | Description |
|---|---|
| Zero dependencies | No CDN, no npm, one `.html` file |
| Works offline | Open the file locally, no internet needed |
| PL / EN | Polish and English UI |
| Download | Export formatted code as .gml file |
| Idempotent | Safe to run multiple times |

## Usage

Just open `gml-formatter.html` in any browser. No install, no server.

1. Paste GML code on the left
2. Click **FORMAT** (or `Ctrl+Enter`)
3. Copy the clean code from the right

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
- `function` declarations
- Template strings `$"..."` and verbatim strings `@"..."`
- Hex literals `$FF`
- GML accessors `[? ]` `[# ]` `[| ]` `[@ ]`
- `#macro` / `#region` / `#endregion`
- Inline and block comments
- Ternary `? :`
- Struct literals `{ key: value }`

## Known limitation

Bare single-line if without braces (`if x > 5 exit;`) — the formatter won't add parens here because it can't safely detect where the condition ends and the body begins. Add braces or parens manually for these.

## Changelog

**v1.3**
- Live stats: operators / conditions / var fixes counter
- Responsive layout for mobile
- Bigger built-in example

**v1.2**
- Added brace style choice: Allman / K&R
- Added drag & drop file loading
- Auto-format on paste
- Settings now persist between visits

**v1.1**
- Added duplicate `var` cleanup (fixes GM2044 errors)
- Added Download button to export as .gml
- English default UI

**v1.0**
- Initial release: Allman formatting, operator conversion, condition fixing

## License

MIT — do whatever you want with it.
