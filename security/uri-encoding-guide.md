# URI Encoding & Decoding — Developer Guide

> 🛠️ **Interactive Version**: [URI Encode & Decode Tool →](https://smartformatter.com/tools/encodeuricomponent)

## What is URI Encoding?
URLs can only be sent over the internet using the ASCII character set. If a URL contains special characters (like spaces, emojis, or symbols like `&` or `=`), they must be converted into a valid format using a `%` followed by two hexadecimal digits. This is known as Percent-Encoding or URI Encoding.

*Example:* A space ` ` becomes `%20`. The `@` symbol becomes `%40`.

## JavaScript Encoding Functions

| Function | What it does | When to use it |
|----------|--------------|----------------|
| `encodeURI()` | Escapes characters except those that have special meaning in a full URL (like `://`, `?`, `&`, `=`, `#`). | When you are encoding an **entire, complete URL** string. |
| `encodeURIComponent()` | Escapes *everything* except standard alphanumeric characters and `- _ . ! ~ * ' ( )`. | When you are encoding a **single parameter value** that will be plugged into a URL query string. |
| `escape()` | ❌ *Deprecated.* | Never use this in modern applications. |

## Common Mistakes / Gotchas
1. **Using `encodeURI` for Query Parameters:** If your search query is `A&B shoes`, and you use `encodeURI()`, the `&` will *not* be escaped. When the server parses `?search=A&B shoes`, it will see `search=A` and `B shoes=` as a separate parameter. You must use `encodeURIComponent()` for values.
2. **Double Encoding:** Running an already encoded string through the encoder again (e.g., `%20` becomes `%2520` because `%` itself gets encoded).
3. **Form Data (application/x-www-form-urlencoded):** In HTML forms, spaces are historically encoded as `+` rather than `%20`. When writing APIs, be aware of which standard the client used to encode the data.

## When to Use This Tool
* Debugging broken links where the query parameters contain special characters or foreign languages.
* Safely preparing an email address or complex search term to be passed dynamically via a REST API URL.
* Decoding messy affiliate links or deep links to see exactly what tracking parameters are attached.

## Related Tools on Smart Formatter
* [Unicode Text Converter](https://smartformatter.com/tools/unicode-text-converter)
* [cURL to Axios & Fetch](https://smartformatter.com/tools/curl-to-axios-fetch)
