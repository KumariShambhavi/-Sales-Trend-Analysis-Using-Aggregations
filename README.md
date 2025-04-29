# -Sales-Trend-Analysis-Using-Aggregations
# Online Sales Dataset Analysis

## Overview
This project involves the creation of a database for online sales transactions, followed by analysis to determine key sales metrics over a specified period. The SQL script provided creates a table `sales` to store transaction data, loads it from a CSV file, and performs revenue and order analysis.

## Features
1. **Database Creation**:
    - The `online_sales_dataset` database is created to hold sales transaction data.

2. **Table Creation**:
    - The `sales` table is created with relevant columns like `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `UnitPrice`, `CustomerID`, `Country`, and others.
    - Each column represents specific sales information, such as product details, quantities, prices, and shipping information.

3. **Data Loading**:
    - Sales data is loaded from a CSV file located at `/path/to/your/online_sales_dataset.csv`.
    - The `LOAD DATA INFILE` command is used to import data into the `sales` table.
    - Fields are separated by commas, enclosed by double quotes, and rows are terminated by newline characters.
    - The first row of the CSV is ignored during the import.

4. **Sales Data Analysis**:
    - A SQL query is used to perform an analysis on sales data from January 1, 2010, to December 31, 2011.
    - The analysis includes the following:
        - **Order Year and Month**: Extracted from the `InvoiceDate`.
        - **Total Orders**: Counts distinct `InvoiceNo` (orders).
        - **Total Revenue**: Sum of `(Quantity * UnitPrice)` adjusted by the discount, excluding returns.
        - **Total Items Sold**: Counts total items sold for each order.
        - **Average Price Per Item**: Calculated as the average `UnitPrice` for each order.

5. **Results**:
    - The query groups data by `order_year` and `order_month`, providing a monthly breakdown of key sales metrics.
    - Results are ordered by year and month for easy analysis.

## How to Run
1. Ensure MySQL is installed and running on your machine.
2. Modify the file path in the `LOAD DATA INFILE` statement to point to your CSV file.
3. Run the script in your MySQL environment.

## Example Output
The final result includes a table with the following columns:
- `order_year`: The year of the sale.
- `order_month`: The month of the sale.
- `total_orders`: Number of distinct orders placed in that month.
- `total_revenue`: Total revenue generated after applying discounts.
- `total_items_sold`: Total number of items sold.
- `avg_price_per_item`: Average price per item sold in that month.

## Conclusion
This SQL script is useful for analyzing online sales data, extracting meaningful insights into revenue and orders across time, and identifying trends.
