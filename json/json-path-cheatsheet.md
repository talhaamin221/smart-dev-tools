# JSONPath — Developer Cheatsheet

> 🛠️ **Interactive Version**: [JSON Path Finder Online →](https://smartformatter.com/tools/json-path-finder)

## What is JSONPath?
JSONPath is a query language for JSON, similar to how XPath is used for XML. It allows you to select and extract specific nodes, values, or objects from a complex JSON document without having to write iterative code.

## Quick Reference: JSONPath Syntax

| Operator | Description | Example |
|----------|-------------|---------|
| `$` | The root object/element | `$` |
| `.` or `[]` | Child operator | `$.store.book` or `$['store']['book']` |
| `..` | Recursive descent | `$..author` |
| `*` | Wildcard (all objects/elements) | `$.store.book[*].author` |
| `[]` | Subscript operator (index) | `$.store.book[0]` |
| `[,]` | Union operator | `$.store.book[0,1]` |
| `[start:end:step]` | Array slice operator | `$.store.book[0:2]` |
| `?()` | Filter expression | `$.store.book[?(@.price < 10)]` |
| `@` | The current node being processed by a filter | `@.price` |

## Key Concepts
1. **Filtering:** You can use logic inside `?()` to filter arrays. E.g., `$..book[?(@.category == 'fiction')]`
2. **Wildcards:** The `*` operator is incredibly useful when keys are dynamic but the structure underneath is known.
3. **Recursive Descent:** `..` will search the entire JSON tree for a specific key, regardless of how deep it is nested.

## Common Mistakes / Gotchas
* **Missing the Root:** Every JSONPath query must start with `$`.
* **String Filtering:** In filter expressions, string values must be enclosed in single quotes. E.g., `[?(@.color == 'red')]`.
* **Zero-Indexing:** Like JavaScript, JSON arrays are 0-indexed. The first item is `[0]`.

## When to Use This Tool
* Debugging large API responses where you only need to inspect a deeply nested value.
* Writing Kubernetes configurations, AWS Step Functions, or CI/CD pipelines that rely on JSONPath for data extraction.
* Building data transformations without writing custom parsing scripts.

## Related Tools on Smart Formatter
* [JSON Unescape & Escape](https://smartformatter.com/tools/json-unescape-escape)
* [JSON Minifier](https://smartformatter.com/tools/json-minifier)
