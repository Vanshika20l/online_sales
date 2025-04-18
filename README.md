# online_sales

### Sample Data
![Screenshot 2025-04-18 092210](https://github.com/user-attachments/assets/0c7f1bbe-6953-42cd-81a3-78044f39f7b2)


 for Online Sales Analysis**

```markdown
# Online Sales Analysis

## Overview
This repository contains a SQL script and sample dataset for analyzing online sales data. The analysis focuses on monthly revenue and order volume trends based on sales data from the first quarter of 2023.

## Dataset
The dataset consists of sales records with the following fields:
- **order_date**: The date when the order was placed (data type: DATE).
- **amount**: The revenue generated from the order (data type: DECIMAL).
- **product_id**: A unique identifier for each product (data type: INTEGER).

### Sample Data
| order_date | amount | product_id |
|------------|--------|------------|
| 2023-01-15 | 150.00 | 101        |
| 2023-01-20 | 200.00 | 102        |
| 2023-02-10 | 300.00 | 103        |
| 2023-02-15 | 250.00 | 101        |
| 2023-03-05 | 400.00 | 104        |
| 2023-03-20 | 350.00 | 105        |

## Setup Instructions

1. **Database Setup**:
   - Choose a database management system (e.g., PostgreSQL, MySQL, SQLite).
   - Create a new database for the analysis.

2. **Create the Table**:
   - Execute the following SQL command to create the `online_sales` table:
     ```sql
     CREATE TABLE online_sales (
         order_date DATE,
         amount DECIMAL(10, 2),
         product_id INT
     );
     ```

3. **Insert Sample Data**:
   - Insert the provided sample data into the `online_sales` table:
     ```sql
     INSERT INTO online_sales (order_date, amount, product_id) VALUES
     ('2023-01-15', 150.00, 101),
     ('2023-01-20', 200.00, 102),
     ('2023-02-10', 300.00, 103),
     ('2023-02-15', 250.00, 101),
     ('2023-03-05', 400.00, 104),
     ('2023-03-20', 350.00, 105);
     ```

4. **Analyze Monthly Revenue and Order Volume**:
   - Use the following SQL query to analyze the data:
     ```sql
     SELECT 
         EXTRACT(YEAR FROM order_date) AS year,
         EXTRACT(MONTH FROM order_date) AS month,
         SUM(amount) AS total_revenue,
         COUNT(DISTINCT product_id) AS order_volume
     FROM 
         online_sales
     WHERE 
         order_date >= '2023-01-01' AND order_date < '2023-04-01'
     GROUP BY 
         year, month
     ORDER BY 
         year, month;
     ```

## Results
- The results of the analysis will provide insights into the total revenue and order volume for each month in the specified period.
![Screenshot 2025-04-18 091028](https://github.com/user-attachments/assets/3a1bb2d9-ef22-44c6-a37b-f0e0fd900bd3)





