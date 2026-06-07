# GraphQL Query Formatter — Developer Cheatsheet

> 🛠️ **Interactive Version**: [GraphQL Query Formatter →](https://smartformatter.com/tools/graphql-query-formatter)

## What is GraphQL Formatting?
Unlike JSON, GraphQL queries have their own specific syntax that is not naturally valid in standard text parsers. Formatting a GraphQL query means adding the correct indentation, line breaks, and bracket alignments so that complex queries, mutations, and fragments are readable.

## Quick Reference: GraphQL Syntax

| Element | Syntax | Description |
|---------|--------|-------------|
| **Query** | `query { ... }` | Fetches data. `query` is optional if there are no variables. |
| **Mutation** | `mutation { ... }` | Modifies data on the server. |
| **Variables** | `query($id: ID!) { user(id: $id) }` | Passes dynamic arguments to the query. |
| **Fragments** | `fragment Name on Type { ... }` | Reusable chunks of a query. |
| **Aliases** | `aliasName: originalField` | Renames the returned key in the JSON response. |
| **Directives** | `@include(if: Boolean)` | Modifies the execution behavior (e.g., `@skip`). |

## Common Mistakes / Gotchas
1. **Commas:** While JSON requires commas between fields, GraphQL does not. A common mistake when copying JSON structures into GraphQL is leaving commas, which can cause parser warnings in some clients.
2. **Missing Braces:** Every field that returns an Object (rather than a scalar like a String or Int) *must* have a selection set (curly braces `{}`).
3. **Variable Definitions:** If you use a variable like `$id`, you must declare it in the operation definition: `query GetUser($id: ID!)`.

## Formatting Best Practices
* **One Field Per Line:** For readability, each requested field should be on its own line.
* **Capitalize Types/Operations:** Name your operations clearly (e.g., `query GetUserProfile`) using PascalCase.
* **Inline Fragments:** Use `... on TypeName { }` when querying interfaces or unions to keep the query clean.

## When to Use This Tool
* When you've copied a raw GraphQL query from a network tab or a minified string and need to make it readable.
* When writing documentation and you want your GraphQL examples to look perfectly structured.
* To quickly check if a query has mismatched brackets before pasting it into Apollo, Relay, or Postman.

## Related Tools on Smart Formatter
* [JSON Unescape & Escape](https://smartformatter.com/tools/json-unescape-escape)
* [JSON Path Finder](https://smartformatter.com/tools/json-path-finder)
