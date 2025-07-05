# Task 7: Basic Sales Summary with Python and SQLite

## Project Overview

This repository contains the solution for Task 7 of the Data Analyst Internship, focusing on leveraging SQL within Python to perform basic sales data analysis and visualization. The primary objective was to connect to a simple SQLite database, execute SQL queries to retrieve sales information, display the results, and visualize them using a basic bar chart.

## Task Objective

The main goals for this task were to:
* Learn how to write basic SQL queries.
* Practice importing SQL data into Python.
* Perform simple data summaries (like total quantity sold and total revenue).
* Create a first sales chart using `matplotlib`.

## Dataset

For this task, a small SQLite database file named `sales_data.db` was created. This database contains a single table, `sales`, with the following schema:
* `product` (TEXT)
* `quantity` (INTEGER)
* `price` (REAL)

This table was populated with sample sales data to simulate a basic e-commerce scenario.

## Tools Used

* **Python:** The core programming language for scripting.
* **`sqlite3`:** Python's built-in module for interacting with SQLite databases.
* **`pandas`:** A powerful Python library used for data manipulation and analysis, particularly for handling tabular data (DataFrames).
* **`matplotlib`:** A widely used Python library for creating static, interactive, and animated visualizations.

## Solution Overview

The Python script (`sales_analysis.py` or equivalent) performs the following steps:

1.  **Database Creation and Population:**
    * A SQLite database file (`sales_data.db`) is created programmatically using `sqlite3`.
    * A `sales` table is defined within this database.
    * Sample sales records are inserted into the `sales` table.
    *(Note: This database creation/population part is designed to run only once to set up the environment.)*

2.  **Database Connection:**
    * A connection is established to the `sales_data.db` file using `sqlite3.connect()`.

3.  **SQL Query Execution:**
    * An SQL query is defined as a multi-line string to calculate `total_quantity_sold` and `total_revenue` for each product, grouped by `product` and ordered by `total_revenue`.
    * This SQL query is executed via `pandas.read_sql_query()`, which automatically fetches the results and loads them into a pandas DataFrame.

4.  **Result Display:**
    * The generated DataFrame containing the product sales summary is printed to the console in a clear, formatted (Markdown) table.

5.  **Data Visualization:**
    * A bar chart is created using `matplotlib`'s plotting capabilities (accessed through `pandas.DataFrame.plot()`).
    * The chart visualizes `total_revenue` for each `product`, providing a quick overview of sales performance.
    * Labels, title, and proper x-axis tick rotation are applied for readability.

6.  **Database Connection Closure:**
    * The connection to the SQLite database is properly closed using `conn.close()` to release resources.

## Key Learnings

By completing this task, I gained practical experience in:
* Connecting Python to a relational database (SQLite).
* Executing SQL queries from within a Python script.
* Importing query results into pandas DataFrames for further analysis.
* Performing simple data aggregations (`SUM()`, `GROUP BY`).
* Creating basic data visualizations using `matplotlib` and pandas plotting functions.

## Deliverables

* `sales_analysis.py`: The Python script containing all the code for database interaction, querying, and visualization.
* `sales_data.db`: The SQLite database file created by the script, containing the `sales` table and sample data.
* (Optional) `sales_chart.png`: An image file of the generated bar chart (if the `plt.savefig()` line was uncommented and used).

---
