# cURL to Axios & Fetch — Developer Guide

> 🛠️ **Interactive Version**: [cURL to Axios & Fetch Converter →](https://smartformatter.com/tools/curl-to-axios-fetch)

## What is cURL?
cURL (Client URL) is a command-line tool used to transfer data over network protocols (HTTP, FTP, etc.). Because it is universal across Linux/macOS, API documentation (like Stripe, Twilio, AWS) almost exclusively uses cURL for code examples.

## Quick Reference: cURL Flags to JavaScript

| cURL Flag | Meaning | Fetch Equivalent | Axios Equivalent |
|-----------|---------|------------------|------------------|
| `-X POST` | HTTP Method | `method: 'POST'` | `axios.post()` |
| `-H "Auth: Bearer"` | Header | `headers: { 'Auth': 'Bearer' }` | `headers: { 'Auth': 'Bearer' }` |
| `-d '{"a":1}'` | JSON Body | `body: JSON.stringify({"a":1})` | `data: { a: 1 }` |
| `--data-urlencode` | Form URL Encoded | `body: new URLSearchParams()` | `data: 'a=1'` |
| `-u user:pass` | Basic Auth | `headers: { 'Authorization': 'Basic ...' }` | `auth: { username, password }` |
| `-i` | Include Headers | Responds via `response.headers` | Responds via `res.headers` |

## Axios vs Fetch: Which to use?

* **Fetch:** The modern native browser standard. Requires no dependencies. However, you must manually parse JSON (`res.json()`) and handle HTTP errors manually (Fetch doesn't throw on 404s/500s).
* **Axios:** A popular npm library. It automatically parses JSON, automatically throws errors on 400/500 status codes, and handles timeout configurations elegantly.

## Common Mistakes / Gotchas
1. **JSON Stringification in Fetch:** When copying a `-d` JSON payload to Fetch, developers often forget to wrap the object in `JSON.stringify()`. Axios handles this automatically.
2. **Missing Content-Type:** If you send JSON but forget `-H "Content-Type: application/json"`, the server will likely reject the request.
3. **Escaping Quotes:** cURL examples often use single quotes around the JSON body (e.g., `-d '{"key":"value"}'`). When pasting into JS, these must be formatted into proper JS objects.

## When to Use This Tool
* Translating API documentation examples into usable frontend code for your React/Vue/Node.js app.
* Taking a copied "Copy as cURL" command from the Chrome Network tab and converting it into an Axios request for automated testing.

## Related Tools on Smart Formatter
* [JSON Unescape & Escape](https://smartformatter.com/tools/json-unescape-escape)
* [URI Encode & Decode](https://smartformatter.com/tools/encodeuricomponent)
