# Task6--
1. Create the sales_data table
CREATE TABLE sales_data (
    order_id VARCHAR(50),
    order_date DATE,
    customer_name VARCHAR(100),
    product_name VARCHAR(100),
    quantity INT,
    unit_price DECIMAL(10,2),
    total_amount DECIMAL(10,2)
);

-- 2. Example INSERT query (repeat for all rows or import CSV if supported)
-- INSERT INTO sales_data VALUES (...);

-- 3. Sales Trend Analysis: Monthly Revenue and Order Volume
SELECT
    DATE_FORMAT(order_date, '%Y-%m') AS month,
    SUM(total_amount) AS revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM sales_data
GROUP BY month
ORDER BY month;
