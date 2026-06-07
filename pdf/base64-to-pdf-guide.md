# Base64 to PDF — Developer Guide

> 🛠️ **Interactive Version**: [Base64 to PDF Converter →](https://smartformatter.com/tools/base64-to-pdf)

## Why Base64 Encode PDFs?
Base64 is a way to represent binary data (like a PDF or an image) using only safe ASCII text characters (A-Z, a-z, 0-9, +, /). 

APIs (like DocuSign, Stripe, or banking APIs) cannot easily send raw binary files inside a JSON response. Instead, they encode the PDF into a Base64 string and embed it inside the JSON. 

## The Anatomy of a Base64 String
Often, a Base64 string will come with a "Data URI Scheme" prefix.

`data:application/pdf;base64,JVBERi0xLjQKJcOkw7zDtsOfCjIgMC...`

*   `data:` tells the browser this is an inline file.
*   `application/pdf;` defines the MIME type.
*   `base64,` indicates the encoding method.
*   The rest is the actual file payload.

## Common Mistakes / Gotchas
1. **Payload Size Increase:** Base64 encoding increases the file size by about **33%**. A 10MB PDF will become a ~13.3MB text string. This can cause unexpected timeouts or max-payload errors on API gateways (like AWS API Gateway's 10MB limit).
2. **Corrupted Strings:** If a Base64 string is sent in a URL query parameter without proper URI encoding, the `+` characters will be interpreted as spaces, corrupting the file completely upon decoding.
3. **Missing Padding:** Base64 strings must have a length that is a multiple of 4. They are often padded with `=` or `==` at the end. Removing these equals signs can break strict decoders.

## When to Use This Tool
* When you receive an API response containing an invoice or shipping label as a Base64 string and you need to view it immediately without writing a decoding script.
* Debugging file upload/download flows in your application to verify the Base64 generation logic isn't corrupting the file headers.

## Related Tools on Smart Formatter
* [PDF Stitcher](https://smartformatter.com/tools/pdf-stitcher)
* [URI Encode & Decode](https://smartformatter.com/tools/encodeuricomponent)
