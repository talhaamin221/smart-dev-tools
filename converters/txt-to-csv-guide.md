# TXT to CSV — Developer Guide

> 🛠️ **Interactive Version**: [TXT to CSV Converter →](https://smartformatter.com/tools/txt-to-csv)

## Understanding Text Delimiters
A CSV (Comma-Separated Values) file is just a text file. The difference between a generic `.txt` file and a `.csv` file is the presence of a consistent delimiter (a character that separates columns). 

When converting `.txt` to `.csv`, the goal is to identify how the text is structured and standardize it.

### Common Delimiters in TXT files:
* **Pipe (`|`)**: Very common in legacy healthcare and banking systems.
* **Semicolon (`;`)**: Common in European datasets where the comma is used as a decimal separator.
* **Tab (`\t`)**: (See our specific TSV to CSV guide).
* **Space (` `)**: Used in raw server logs or terminal outputs.

## The RFC 4180 Standard
To be a valid CSV, the output should ideally adhere to RFC 4180:
1. Records are separated by line breaks (CRLF).
2. Fields are separated by commas.
3. Fields containing commas, line breaks, or double quotes must be enclosed in double quotes.
4. Double quotes inside a quoted field must be escaped with another double quote (`""`).

## Common Mistakes / Gotchas
* **Inconsistent Delimiters:** If your TXT file uses spaces as a delimiter, but the actual data contains spaces (e.g., `John Doe 35`), a simple parser will break "John" and "Doe" into two columns.
* **Encoding Issues:** TXT files from older systems might be encoded in Windows-1252 or ISO-8859-1. When converting, ensure the output is saved as UTF-8 to preserve special characters.

## When to Use This Tool
* Converting raw server logs into a spreadsheet-readable format.
* Ingesting data from legacy mainframe systems that export pipe-delimited text files.
* Standardizing data dumps before importing them into a SQL database.

## Related Tools on Smart Formatter
* [TSV to CSV](https://smartformatter.com/tools/tsv-to-csv)
* [Excel/CSV to JSON](https://smartformatter.com/tools/excel-to-json)
