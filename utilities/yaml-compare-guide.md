# YAML Compare — Developer Cheatsheet

> 🛠️ **Interactive Version**: [YAML Compare Tool →](https://smartformatter.com/tools/yaml-compare)

## What is YAML?
YAML (YAML Ain't Markup Language) is a human-readable data serialization language. Because of its clean, minimalistic syntax (relying on indentation rather than brackets), it has become the standard for configuration files (Docker, Kubernetes, GitHub Actions, CI/CD).

## YAML vs JSON

| Feature | YAML | JSON |
|---------|------|------|
| **Structure** | Indentation-based | Bracket-based (`{}`, `[]`) |
| **Comments** | ✅ Supported (`#`) | ❌ Not Supported |
| **Data Types** | Auto-inferred (mostly) | Explicit (must quote strings) |
| **Advanced Features**| Anchors (`&`) and Aliases (`*`) | None |

## Semantic Comparison vs Text Comparison
If you use standard `git diff` on two YAML files, it compares them **line-by-line**. This causes false positives.
* If you change the order of keys in a dictionary, standard text diff highlights it as a massive change.
* **Semantic YAML Comparison** parses the YAML into memory objects and compares the actual data structure. Changing the order of keys in an object does not flag as a difference.

## Common Mistakes / Gotchas
1. **The "Norway Problem":** In YAML 1.1, the string `NO` (the country code for Norway) evaluates to a Boolean `false` unless explicitly put in quotes `"NO"`.
2. **Indentation Errors:** Using a mix of Tabs and Spaces will instantly crash a YAML parser. YAML strictly requires spaces for indentation (usually 2).
3. **Octal Numbers:** If a number starts with a zero (e.g., `0755`), YAML might interpret it as an octal value rather than a standard integer or string.

## When to Use This Tool
* Comparing your local `docker-compose.yml` against the production version to ensure no environment variables were missed.
* Checking complex Kubernetes deployment manifests before applying them to a cluster.
* Reviewing PRs where someone reformatted a massive YAML file, to verify they didn't accidentally change actual values.

## Related Tools on Smart Formatter
* [JSON Minifier](https://smartformatter.com/tools/json-minifier)
* [List Compare](https://smartformatter.com/tools/list-compare)
