# TSV to CSV — Developer Guide

> 🛠️ **Interactive Version**: [TSV to CSV Converter →](https://smartformatter.com/tools/tsv-to-csv)

## TSV vs CSV
TSV (Tab-Separated Values) and CSV (Comma-Separated Values) are twins. They serve the exact same purpose—storing tabular data in plain text—but they use different delimiters.

| Feature | TSV (Tab-Separated) | CSV (Comma-Separated) |
|---------|---------------------|-----------------------|
| **Delimiter** | Tab (`\t`) | Comma (`,`) |
| **Quoting rules** | Rarely needed (tabs rarely appear in data) | Strictly needed (commas often appear in data) |
| **Primary Use** | Bioinformatics, Database dumps, clipboard pastes | General business use, Excel, Finance |

## Why Convert TSV to CSV?
Excel and Google Sheets *can* open TSV files, but it often requires going through a "Text Import Wizard". Double-clicking a CSV file opens it instantly formatted correctly. Converting TSV to CSV removes friction for end-users.

## Common Mistakes / Gotchas
1. **The "Copy/Paste" Trap:** When you copy a table from an HTML page or Excel and paste it into a text editor, it pastes as TSV (tabs separate the columns). If you save this as a `.csv` file without replacing the tabs with commas, it will open as one giant column in Excel.
2. **Escaping Values:** When converting TSV to CSV, you must check if the values themselves contain commas. If a TSV value is `Hello, World`, it must become `"Hello, World"` in the CSV to prevent it from splitting into two columns.

## When to Use This Tool
* Sharing database dumps (which are often exported as TSV by default, like from MySQL `INTO OUTFILE`) with a non-technical team.
* Standardizing a data pipeline where some vendors provide TSV and others provide CSV.

## Related Tools on Smart Formatter
* [TXT to CSV](https://smartformatter.com/tools/txt-to-csv)
* [Merge Excel Files](https://smartformatter.com/tools/merge-excel-files)
