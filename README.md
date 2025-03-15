```markdown
# Blinkit Data Analysis - SQL Project

This project focuses on analyzing sales data from Blinkit using SQL. The dataset contains information about sales, item types, fat content, outlet details, and more. The goal of this project is to clean the data, calculate key performance indicators (KPIs), and generate insights through various SQL queries.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Cleaning](#data-cleaning)
3. [Key Performance Indicators (KPIs)](#key-performance-indicators-kpis)
4. [Sales Analysis](#sales-analysis)
5. [Usage](#usage)
6. [Queries](#queries)

---

## Project Overview

The dataset used in this project is named `blinkit_data`. It contains the following fields:
- `Item_Fat_Content`: Fat content of items (e.g., Low Fat, Regular).
- `Item_Type`: Type of item (e.g., Dairy, Snacks).
- `Total_Sales`: Total sales for each item.
- `Outlet_Location_Type`: Location type of the outlet.
- `Outlet_Establishment_Year`: Year the outlet was established.
- `Outlet_Size`: Size of the outlet (e.g., Small, Medium, Large).
- `Outlet_Type`: Type of outlet (e.g., Supermarket, Grocery Store).
- `Rating`: Customer rating for the outlet.
- `Item_Visibility`: Visibility of the item in the outlet.

The SQL queries in this project perform data cleaning, calculate KPIs, and analyze sales data across different dimensions.

---

## Data Cleaning

The `Item_Fat_Content` field had inconsistent values (e.g., "LF", "low fat", "reg"). The following query standardizes these values to "Low Fat" and "Regular":

```sql
UPDATE blinkit_data
SET Item_Fat_Content =
CASE
    WHEN Item_Fat_Content IN ('LF', 'low fat') THEN 'Low Fat'
    WHEN Item_Fat_Content = 'reg' THEN 'Regular'
    ELSE Item_Fat_Content
END;
```

---

## Key Performance Indicators (KPIs)

The following KPIs were calculated:

1. **Total Sales**: Total sales in millions.
2. **Average Sales**: Average sales per item.
3. **Number of Items**: Total number of items sold.
4. **Average Rating**: Average customer rating.

Example query for Total Sales:
```sql
SELECT CAST(SUM(Total_Sales) / 1000000.0 AS DECIMAL(10,2)) AS Total_Sales_Million
FROM blinkit_data;
```

---

## Sales Analysis

The project includes several analyses to understand sales patterns:

1. **Total Sales by Fat Content**: Breakdown of sales by fat content (Low Fat vs. Regular).
2. **Total Sales by Item Type**: Sales distribution across different item types.
3. **Fat Content by Outlet for Total Sales**: Pivot table showing sales by fat content for each outlet location.
4. **Total Sales by Outlet Establishment Year**: Sales trends based on the year the outlet was established.
5. **Percentage of Sales by Outlet Size**: Contribution of each outlet size to total sales.
6. **Sales by Outlet Location**: Sales distribution across different outlet locations.
7. **All Metrics by Outlet Type**: Comprehensive metrics (total sales, average sales, number of items, average rating, and item visibility) grouped by outlet type.

---

## Usage

To use the SQL queries in this project:

1. Ensure you have a SQL environment set up (e.g., MySQL, PostgreSQL, SQL Server).
2. Import the `blinkit_data` dataset into your database.
3. Run the SQL queries provided in the `queries.sql` file to perform the analysis.

---

## Queries

Below is a summary of the queries included:

1. **Data Cleaning**:
   - Standardize `Item_Fat_Content`.

2. **KPIs**:
   - Total Sales, Average Sales, Number of Items, Average Rating.

3. **Sales Analysis**:
   - Total Sales by Fat Content.
   - Total Sales by Item Type.
   - Fat Content by Outlet for Total Sales.
   - Total Sales by Outlet Establishment Year.
   - Percentage of Sales by Outlet Size.
   - Sales by Outlet Location.
   - All Metrics by Outlet Type.

---

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request. Please ensure your changes are well-documented and tested.

---

## License

This project is open-source and available under the [MIT License](LICENSE).

---

## Contact

For any questions or feedback, please reach out to parvejakhter8461@gmail.com.

```

