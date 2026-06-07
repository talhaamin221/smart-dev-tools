# Apache Parquet — Developer Cheatsheet

> 🛠️ **Interactive Version**: [Parquet Viewer Online →](https://smartformatter.com/tools/parquet-viewer-online)

## What is Apache Parquet?
Parquet is an open-source, column-oriented data file format designed for efficient data storage and retrieval. It is the standard format used in Hadoop, Spark, Snowflake, and modern Data Lakes.

Unlike CSV (which is row-oriented and plain text), Parquet is highly compressed, strongly typed, and stores data by column, making analytical queries incredibly fast.

## Row-Oriented (CSV) vs Column-Oriented (Parquet)

| Metric | CSV (Row) | Parquet (Column) |
|--------|-----------|------------------|
| **Best For** | Human readability, sequential writes | Analytics, reading specific columns |
| **Compression** | Poor (text-based) | Excellent (Snappy, Gzip, Brotli) |
| **Schema** | None (inferred) | Embedded in the file metadata |
| **Query Speed (Aggregating 1 column)** | Slow (scans entire file) | Fast (only reads the needed column) |

## Key Concepts
1. **Embedded Schema:** The schema (data types, column names) is stored in the file footer. You never have to guess if a column is a String or an Integer.
2. **Predicate Pushdown:** Because Parquet tracks min/max statistics for chunks of data, query engines can skip entire chunks if the data doesn't match a `WHERE` clause without even reading it.
3. **Dictionary Encoding:** If a column has repeating values (e.g., "Country" column), Parquet stores the string once and uses small integers to reference it, saving massive amounts of space.

## Common Mistakes / Gotchas
* **Trying to read it in a text editor:** Parquet is a binary format. If you open it in VS Code or Notepad, you will just see gibberish and weird symbols. You must use a parser.
* **Small Files Problem:** Writing thousands of 10KB Parquet files defeats the compression and dictionary encoding benefits. Parquet works best with large files (typically 128MB to 1GB).

## When to Use This Tool
* When a data engineer sends you a `.parquet` file via Slack or email and you need to see what's inside without writing a Python/Pandas script.
* To quickly verify the schema and column data types before writing an ETL pipeline.
* To convert a small subset of Parquet data into CSV for a non-technical stakeholder.

## Related Tools on Smart Formatter
* [JSON to Excel/CSV](https://smartformatter.com/tools/json-to-excel)
