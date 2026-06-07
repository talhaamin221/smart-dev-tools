# JSON Escape & Unescape — Developer Cheatsheet

> 🛠️ **Interactive Version**: [JSON Unescape & Escape Tool →](https://smartformatter.com/tools/json-unescape-escape)

## What is JSON Escaping?
JSON escaping is the process of converting special characters within a string into an "escape sequence" so the JSON remains structurally valid. Unescaping (or decoding) is the reverse process: turning those escape sequences back into their original characters.

## Quick Reference: JSON Escape Sequences

| Character | Name | Escape Sequence | Description |
|:---:|---|:---:|---|
| `"` | Double Quote | `\"` | Prevents the string from prematurely ending. |
| `\` | Backslash | `\\` | Escapes a literal backslash. |
| `/` | Forward Slash | `\/` | Optional in JSON, but useful to prevent `</script>` issues. |
| `Backspace` | Backspace | `\b` | Moves the cursor back one space. |
| `Form Feed` | Form Feed | `\f` | Forces a page break. |
| `New Line` | New Line | `\n` | Drops to the next line. |
| `Carr. Ret.` | Carriage Return | `\r` | Returns to the start of the line. |
| `Tab` | Horizontal Tab | `\t` | Inserts a tab space. |

## The "Double-Stringified" JSON Problem
A common issue in API development is receiving a JSON payload where a property contains *another* JSON string that has been encoded twice.

**Example of stringified JSON:**
```json
{
  "event_id": 1234,
  "payload": "{\"user_id\": 99, \"status\": \"active\"}"
}
```
In order to parse `payload`, it must first be unescaped. 

## Common Mistakes / Gotchas
1. **Single Quotes:** JSON strictly requires double quotes `"`. You cannot use single quotes `'` for strings, nor can you escape them like `\'`.
2. **Trailing Commas:** Standard JSON does not allow trailing commas after the last element in an array or object.
3. **Newline Characters in Strings:** Real line breaks inside a string will break JSON. They must be escaped as `\n`.

## When to Use This Tool
* Debugging API responses where payloads are returned as heavily escaped strings.
* Preparing JSON configurations to be embedded within environment variables, shell scripts, or HTML attributes.
* Cleaning up malformed logs that dumped stringified objects.

## Related Tools on Smart Formatter
* [JSON Minifier](https://smartformatter.com/tools/json-minifier)
* [JSON Path Finder](https://smartformatter.com/tools/json-path-finder)
