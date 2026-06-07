# Merge Excel Files — Developer Guide

> 🛠️ **Interactive Version**: [Merge Excel Files Online →](https://smartformatter.com/tools/merge-excel-files)

## Why Merge Excel Files?
Data rarely comes in a single perfect file. You might receive weekly sales reports across 52 files, or regional HR data from 10 different branches. Manually copy-pasting hundreds of files is error-prone. Merging automates the combination of multiple `.xlsx`, `.csv`, or `.tsv` files into one master dataset.

## Merging Strategies

### 1. Vertical Merging (Union / Append)
* **What it does:** Stacks files on top of each other.
* **Requirements:** Files must have the exact same column headers.
* **Result:** More rows, same number of columns.
* **Example:** Combining `Jan_Sales.xlsx` and `Feb_Sales.xlsx`.

### 2. Horizontal Merging (Join / VLOOKUP)
* **What it does:** Puts files side-by-side based on a common key (like `ID`).
* **Requirements:** Files must share a unique identifier column.
* **Result:** Same number of rows, more columns.

## Common Mistakes / Gotchas
* **Inconsistent Headers:** If File A has `FirstName` and File B has `First Name`, a vertical merge will create two separate columns with missing data. Always sanitize headers first.
* **Memory Limits:** Merging fifty 100MB files in Python/Pandas will crash if you run out of RAM. Client-side browser merging streams data to prevent memory crashes.
* **Data Type Corruption:** When merging CSVs into an Excel file, ensure zip codes (e.g., `01234`) don't get converted into integers (`1234`) losing the leading zero.

## When to Use This Tool
* Consolidating monthly or regional reports into a master annual workbook.
* Combining fragmented CSV exports from a SaaS platform (like Shopify or Stripe) before importing into a BI tool like Tableau.

## Related Tools on Smart Formatter
* [Excel/CSV to JSON](https://smartformatter.com/tools/excel-to-json)
* [List Compare](https://smartformatter.com/tools/list-compare)
