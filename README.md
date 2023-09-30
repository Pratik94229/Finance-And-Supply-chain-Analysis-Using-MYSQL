# Finance and Supply Chain Analysis Repository

This repository contains code for finance and supply chain analytics, designed to perform various financial and sales analysis tasks. The code comprises SQL queries, functions, reports, stored procedures, triggers, events, and user management for analyzing finance and supply chain data.

## Finance Analytics

### A. Customer Codes for Croma India

The first SQL query retrieves customer codes for the Croma India market from the `dim_customer` table.

### B. Sales Transaction Data for Croma India in Fiscal Year 2021

The second SQL query retrieves all the sales transaction data from the `fact_sales_monthly` table for the customer (Croma: 90002002) in the fiscal year 2021.

### C. Creating a Function 'get_fiscal_year'

A user-defined function named `get_fiscal_year` is created to get the fiscal year by passing a date.

### D. Replacing the Function in the Query

The third SQL query replaces the function created in step C and retrieves sales transaction data using the new function.

### Gross Sales Reports

1. **Monthly Product Transactions**

   Joins product information from the `dim_product` table with sales data from the `fact_sales_monthly` table for Croma India in fiscal year 2021.

2. **Total Sales Amount**

   Generates a monthly gross sales report for Croma India for all years, aggregating the sales data from the `fact_sales_monthly` and `fact_gross_price` tables.

### Stored Procedures

- **get_monthly_gross_sales_for_customer**

  Generates a monthly gross sales report for any customer by passing customer codes as input.

- **get_market_badge**

  Retrieves the market badge (Gold or Silver) based on the total sold quantity for a given market and fiscal year.

### Yearly Report for Croma India

Generates a yearly report for Croma India, showing two columns:

- Fiscal Year
- Total Gross Sales amount in that year from Croma

## Supply Chain Analytics

### Creating fact_act_est Table

This part of the code creates a new `fact_act_est` table, which combines data from the `fact_sales_monthly` and `fact_forecast_monthly` tables.

### Database Triggers

Two triggers are created:

- **fact_sales_monthly_AFTER_INSERT**

  Automatically inserts records into the `fact_act_est` table whenever an insertion occurs in the `fact_sales_monthly` table.

- **fact_forecast_monthly_AFTER_INSERT**

  Automatically inserts records into the `fact_act_est` table whenever an insertion occurs in the `fact_forecast_monthly` table.

### Events

- **e_daily_log_purge**

  A daily event to delete logs that are more than 5 days old from the `session_logs` table.

### Temporary Tables and Forecast Accuracy Report

This section demonstrates the use of temporary tables and stored procedures to generate a forecast accuracy report for a given fiscal year.

### User Accounts and Privileges

This section deals with user management and grants certain privileges to a new user 'thor' for the 'gdb0041' database.
