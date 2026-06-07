# GML Formatter — Allman Style

> Format your GameMaker Language code properly. No more mess.

**by [GanjaViruss](https://github.com/GanjaViruss) & Claude Sonnet 4.6 & Opus 4.8**

---

## What it does

Paste your messy GML code → get clean, readable code back.

- **Allman brace style** — braces on their own line, always
- **Keyword operators** — `and` → `&&`, `or` → `||`, `not` → `!`, `mod` → `%`, `xor` → `^^`, `<>` → `!=`
- **Condition fixer** — wraps bare `if x > 0 {` into `if (x > 0) {`, fixes `=` → `==` inside conditions
- **Proper indentation** — configurable (default 4 spaces)
- **Inline comments preserved** — `x = 1; // comment` stays on one line
- **Switch/case formatting** — correct indentation for case bodies
- **Template strings safe** — `$"text {var}"` never broken
- **Idempotent** — format twice, get the same result

## Features

| Feature | Description |
|---|---|
| Zero dependencies | No CDN, no npm, one `.html` file |
| Works offline | Open the file locally, no internet needed |
| PL / EN | Polish and English UI |
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

## License

MIT — do whatever you want with it.
