# JWT (JSON Web Token) — Developer Cheatsheet

> 🛠️ **Interactive Version**: [JWT Decoder & Parser →](https://smartformatter.com/tools/jwt-decoder)

## What is a JWT?
A JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact, URL-safe way of representing claims to be transferred between two parties. It is heavily used for stateless authentication in modern web apps and APIs.

## Anatomy of a JWT
A JWT is a string divided into three parts, separated by dots (`.`):
`xxxxx.yyyyy.zzzzz`

1. **Header (`xxxxx`):** Contains the algorithm used (e.g., HS256, RS256) and token type (JWT).
2. **Payload (`yyyyy`):** Contains the claims (the actual data, like user ID, roles, expiry).
3. **Signature (`zzzzz`):** A cryptographic hash of the Header and Payload, signed with a secret key. This proves the token hasn't been tampered with.

*Note: The Header and Payload are just Base64Url encoded. **They are NOT encrypted.** Anyone can decode and read them.*

## Standard Registered Claims

| Claim | Full Name | Purpose |
|-------|-----------|---------|
| `iss` | Issuer | Who created and signed the token (e.g., Auth0, your server). |
| `sub` | Subject | Who the token refers to (usually the User ID). |
| `aud` | Audience | Who the token is intended for (e.g., your API URL). |
| `exp` | Expiration Time | Unix timestamp of when the token expires and becomes invalid. |
| `nbf` | Not Before | Unix timestamp before which the token must NOT be accepted. |
| `iat` | Issued At | Unix timestamp of when the token was created. |

## Common Mistakes / Gotchas
1. **Putting Secrets in the Payload:** Because JWTs are only Base64 encoded (not encrypted), putting passwords, SSNs, or API keys inside the payload is a massive security risk. Anyone with the token can decode it.
2. **Ignoring Expiration (`exp`):** Always validate the `exp` claim. Storing a non-expiring JWT in localStorage means if it's stolen via XSS, the attacker has permanent access.
3. **The `alg: none` Vulnerability:** If a server doesn't strictly enforce which algorithms it accepts, an attacker can modify the header to `"alg": "none"`, strip the signature, and bypass authentication.

## When to Use This Tool
* Debugging authentication issues (checking if the token actually contains the correct User ID or Role).
* Verifying if a token has expired by translating the Unix `exp` timestamp into a human-readable date.
* Inspecting OAuth2 tokens from providers like Google, Auth0, or AWS Cognito.

## Related Tools on Smart Formatter
* [MD5 & SHA256 Checksum](https://smartformatter.com/tools/md5-sha256-checksum)
* [Base64 to PDF Converter](https://smartformatter.com/tools/base64-to-pdf)
