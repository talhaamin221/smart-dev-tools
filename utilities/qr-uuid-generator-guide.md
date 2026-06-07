# QR Code & UUID Generator — Developer Guide

> 🛠️ **Interactive Version**: [QR Code & UUID Generator →](https://smartformatter.com/tools/random-qr-code-generator)

## Section 1: UUIDs (Universally Unique Identifiers)
A UUID is a 128-bit number used to identify information in computer systems. It is practically unique across space and time without requiring a central database to assign it.

### UUID v4 vs UUID v7

| Version | How it's generated | Best Use Case | Drawbacks |
|---------|--------------------|---------------|-----------|
| **v4** | Completely random (cryptographically secure). | Standard primary keys, session tokens. | Bad for database indexing (causes index fragmentation because values are scattered). |
| **v7** | Time-ordered (timestamp + random data). | Primary keys in relational databases (PostgreSQL/MySQL). | Slightly less "random" looking. |

## Section 2: QR Codes
QR (Quick Response) codes are two-dimensional barcodes that can store large amounts of data (up to 4,296 alphanumeric characters).

### QR Code Error Correction
QR codes can sustain damage and still be scanned. Higher error correction allows you to embed logos inside the QR code.
* **L (Low):** 7% of data can be restored.
* **M (Medium):** 15% of data can be restored.
* **Q (Quartile):** 25% of data can be restored.
* **H (High):** 30% of data can be restored.

## Common Mistakes / Gotchas
* **UUIDs as Passwords:** While UUIDv4 is random, it is not designed to be a cryptographic secret. Don't use a UUID as a secure password or an API signing key.
* **QR Codes too Dense:** If you encode a massive URL or a huge JSON object into a QR code, the dots become incredibly small. Older smartphone cameras will struggle to scan it. Use a URL shortener first.
* **Low Contrast QR Codes:** QR scanners rely on contrast. A light grey QR code on a white background will often fail to scan. Always ensure dark foregrounds on light backgrounds.

## When to Use This Tool
* Generating fresh UUIDs for testing database inserts or mocking API payloads.
* Creating quick, secure QR codes for Wi-Fi networks, event check-ins, or sharing URLs without typing.
* Specifically generating UUIDv7 keys to optimize database insert performance in PostgreSQL.

## Related Tools on Smart Formatter
* [MD5 & SHA Checksum](https://smartformatter.com/tools/md5-sha256-checksum)
* [cURL to Axios & Fetch](https://smartformatter.com/tools/curl-to-axios-fetch)
