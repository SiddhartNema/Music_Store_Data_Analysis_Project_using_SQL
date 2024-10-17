# # Music Store Data Analysis Project

This project involves analyzing a music store’s sales data to extract insights related to customer behavior, sales trends, and performance metrics using SQL for querying and reporting.

## Features
- **Sales Analysis**: Track music sales across various genres, albums, and artists.
- **Customer Insights**: Analyze customer purchasing behavior and identify top customers.
- **Trend Analysis**: Use SQL queries to identify sales trends and patterns over time.
  
## Technologies Used
- **SQL**: For data querying and analysis (PostgreSQL/MySQL).
- **Excel**: For visualization of the query results and insights.

## Project Setup
### Requirements
- SQL Database (e.g., PostgreSQL, MySQL, or SQLite)
- Excel or any visualization tool for presenting the results.

### Setup Instructions
1. Clone the repository:
    ```bash
    git clone https://github.com/SiddhartNema/Music_Store_Data_Analysis_Project_using_SQL.git
    ```

2. Import the dataset into your SQL database:
    - Import the provided `music_store.sql` file into your database.
    - Use the following command (PostgreSQL example):
    ```bash
    psql -U username -d database_name -f music_store.sql
    ```

3. Run the SQL queries from the `analysis_queries.sql` file to analyze data and generate insights.

## SQL Queries Overview
- **Sales by Genre**: Find out which music genres are performing the best in terms of sales.
- **Top Customers**: Identify the store’s most valuable customers based on their purchasing history.
- **Monthly Sales Trends**: Analyze the sales trends over time to understand peak seasons and downtimes.
- **Artist and Album Performance**: Evaluate which artists and albums are generating the most revenue.

## Example Queries
1. **Top Selling Genres**:
    ```sql
    SELECT genre, SUM(sales_amount) AS total_sales
    FROM sales
    GROUP BY genre
    ORDER BY total_sales DESC;
    ```

2. **Monthly Sales**:
    ```sql
    SELECT EXTRACT(MONTH FROM sales_date) AS month, SUM(sales_amount) AS total_sales
    FROM sales
    GROUP BY month
    ORDER BY month;
    ```

3. **Top 10 Customers**:
    ```sql
    SELECT customer_id, SUM(total_amount) AS total_spent
    FROM sales
    GROUP BY customer_id
    ORDER BY total_spent DESC
    LIMIT 10;
    ```

## How to Run
1. Ensure your SQL database is running and the dataset has been imported.
2. Run the SQL queries in your database client to extract insights.
3. Export the query results to Excel or any visualization tool for further analysis and presentation.

## Conclusion
This project offers insights into a music store’s performance, helping to drive decision-making around customer preferences, sales strategies, and inventory management based on data-driven findings.
