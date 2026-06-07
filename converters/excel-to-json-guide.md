# Excel/CSV to JSON — Developer Guide

> 🛠️ **Interactive Version**: [Excel/CSV to JSON Converter →](https://smartformatter.com/tools/excel-to-json)

## Why Convert Spreadsheets to JSON?
While business teams work in Excel or CSV, modern applications, web frameworks, and NoSQL databases operate on JSON. Converting tabular data into an array of JSON objects is a crucial step in data ingestion and ETL (Extract, Transform, Load) pipelines.

## The Conversion Output
When you convert a spreadsheet, the standard output is a JSON Array containing Objects. 
* **Row 1 (Headers)** becomes the JSON keys.
* **Row 2+ (Data)** becomes the JSON values.

**Example CSV:**
```csv
id,name,role
1,Alice,Admin
2,Bob,User
```

**Resulting JSON:**
```json
[
  {"id": 1, "name": "Alice", "role": "Admin"},
  {"id": 2, "name": "Bob", "role": "User"}
]
```

## Common Mistakes / Gotchas
1. **Type Inference:** A naive converter will output all CSV values as strings (e.g., `"id": "1"`). A smart converter will detect numbers and booleans and type them correctly in JSON (`"id": 1, "active": true`).
2. **Empty Cells:** In CSV, an empty cell might become an empty string `""` or `null`. Ensure you know how your downstream API handles these.
3. **Header Cleaning:** Excel column headers often contain spaces or special characters (e.g., `First Name`). In JSON, keys with spaces require bracket notation to access (`obj["First Name"]`). It's often best to convert headers to camelCase or snake_case before generating the JSON.

## When to Use This Tool
* Seeding a database (like MongoDB or Firebase) with initial data provided by a client in Excel.
* Creating mock API endpoints from static data files.
* Converting exported analytics or marketing data into a format that a JavaScript frontend can easily map over and render.

## Related Tools on Smart Formatter
* [JSON to Excel/CSV](https://smartformatter.com/tools/json-to-excel)
* [Merge Excel Files](https://smartformatter.com/tools/merge-excel-files)
