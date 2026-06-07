# PDF Stitcher / Merger — Developer Guide

> 🛠️ **Interactive Version**: [PDF Stitcher Online →](https://smartformatter.com/tools/pdf-stitcher)

## Client-Side vs Server-Side PDF Processing
Historically, merging PDFs required uploading the files to a remote server running Java or Python libraries (like PyPDF2), merging them, and downloading the result. 

Modern tools (like the Smart Formatter PDF Stitcher) use WebAssembly (WASM) and specialized JavaScript libraries (like `pdf-lib`) to manipulate the PDF binary format **entirely inside the browser**.

### The Privacy Advantage
Because financial documents, medical records, and legal contracts often contain Personally Identifiable Information (PII), client-side merging is vastly superior. The data never leaves the user's machine, eliminating data leak risks and the need for complex server compliance (like SOC2 or HIPAA) just to merge files.

## Common Mistakes / Gotchas
1. **Locked / Encrypted PDFs:** You cannot merge a PDF that is password-protected or digitally signed without first stripping the encryption. Attempting to stitch a signed PDF usually invalidates the cryptographic signature.
2. **Interactive Forms:** When merging PDFs with fillable form fields (AcroForms), if two fields in different documents have the exact same internal name, merging them can cause the fields to link (typing in page 1 fills out page 5). A good stitcher flattens forms before merging.
3. **Font Subset Issues:** If Document A uses a custom embedded font subset, and Document B uses a different subset of the same font name, merging them can sometimes cause text rendering glitches in older PDF readers.

## When to Use This Tool
* Combining monthly invoices, receipts, or tax forms into a single document for your accountant.
* Stitching together presentation slides exported from different tools (e.g., combining a Canva title slide with an Excel chart export).
* Merging scanned pages of a legal document into one continuous file securely without uploading it to a random third-party server.

## Related Tools on Smart Formatter
* [PPT Compressor](https://smartformatter.com/tools/ppt-compressor)
* [Base64 to PDF Converter](https://smartformatter.com/tools/base64-to-pdf)
