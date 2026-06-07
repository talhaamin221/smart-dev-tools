# JSON to Excel/CSV — Developer Guide

> 🛠️ **Interactive Version**: [JSON to Excel/CSV Converter →](https://smartformatter.com/tools/json-to-excel)

## Why Convert JSON to Tabular Data?
JSON is the standard for APIs because it handles deeply nested, hierarchical data perfectly. However, non-technical stakeholders (finance, marketing, ops) rely on Excel (.xlsx) and CSV files. Converting JSON to tabular data bridges the gap between raw API data and business analysis.

## Key Concepts in Conversion

### 1. Flattening
Excel and CSV are 2-dimensional grids (rows and columns). JSON is multi-dimensional. To convert JSON to Excel, nested objects must be "flattened". 
* **Example JSON:** `{"user": {"name": "Alice", "age": 30}}`
* **Flattened Header:** `user.name`, `user.age`

### 2. Arrays to Rows
The ideal JSON structure for conversion is an array of objects: `[{...}, {...}]`. Each object becomes a row, and its keys become the column headers.

## Common Mistakes / Gotchas
* **Inconsistent Keys:** If the first JSON object in an array is missing a key that appears in the second object, a basic parser might miss that column. A robust converter scans the entire array to build a complete header row.
* **Arrays inside Arrays:** If a JSON property contains an array (e.g., `"tags": ["new", "sale"]`), it usually gets serialized as a string `"[new, sale]"` in Excel, which makes it hard to filter.
* **Date Formats:** JSON stores dates as ISO 8601 strings or Unix timestamps. Excel might treat these as raw text unless the converter or the user formats the column correctly.

## When to Use This Tool
* Exporting user lists, sales data, or logs from a MongoDB database for a business team.
* Converting API endpoint responses directly into spreadsheets for quick data analysis.
* Preparing data for import into legacy CRM or ERP systems that only accept CSV files.

## Related Tools on Smart Formatter
* [Excel/CSV to JSON](https://smartformatter.com/tools/excel-to-json)
* [Parquet Viewer Online](https://smartformatter.com/tools/parquet-viewer-online)
