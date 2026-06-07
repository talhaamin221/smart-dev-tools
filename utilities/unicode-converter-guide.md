# Unicode Text Converter — Developer Guide

> 🛠️ **Interactive Version**: [Unicode Text Converter →](https://smartformatter.com/tools/unicode-text-converter)

## What is Unicode?
Unicode is a universal character encoding standard that assigns a unique number (Code Point) to every character, no matter the platform, program, or language. Before Unicode, different languages used different, conflicting encoding systems (like ASCII or ISO-8859-1).

## UTF-8 vs UTF-16 vs Code Points

| Term | Explanation | Example |
|------|-------------|---------|
| **Code Point** | The unique ID assigned to a character. Written as `U+XXXX`. | `A` = `U+0041` |
| **UTF-8** | Encodes characters using 1 to 4 bytes. Dominates the web. | `A` = `41` (Hex) |
| **UTF-16** | Encodes characters using 2 or 4 bytes. Used in JavaScript strings. | `A` = `0041` (Hex) |
| **JS Escape** | How to represent the character in a JavaScript string. | `\u0041` |

## Common Mistakes / Gotchas
1. **Emojis & Surrogate Pairs:** Emojis (like 🚀) require more than 16 bits. In JavaScript (which uses UTF-16 internally), an emoji is actually treated as *two* characters, known as a surrogate pair. This is why `'🚀'.length` returns `2`, not `1`.
2. **Mojibake:** This occurs when text is encoded in one format (e.g., UTF-8) but decoded in another (e.g., Windows-1252). The result is garbled characters like `Ã©` instead of `é`.
3. **The BOM (Byte Order Mark):** A hidden character (`U+FEFF`) sometimes placed at the very start of a file to indicate its encoding. It can cause invisible bugs in strict parsers (like JSON or CSV parsers) if not stripped out.

## When to Use This Tool
* Debugging weird characters showing up in a database after a user submitted a form.
* Figuring out the correct `\uXXXX` escape sequence to use in a CSS `content:` property or a JavaScript string.
* Converting special symbols (like math operators or foreign alphabets) into raw code points for cross-platform compatibility.

## Related Tools on Smart Formatter
* [JSON Unescape & Escape](https://smartformatter.com/tools/json-unescape-escape)
* [URI Encode & Decode](https://smartformatter.com/tools/encodeuricomponent)
