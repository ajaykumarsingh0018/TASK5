# TASK5
🎯 Objective

Learn how to combine data from multiple tables using different SQL join operations.

🛠 Tools

DB Browser for SQLite

MySQL Workbench


📌 Tables Used

Customers

customer_id	customer_name	city

1	Alice	Delhi
2	Bob	Mumbai
3	Charlie	Bangalore
4	David	Hyderabad


Orders

order_id	order_date	customer_id	amount

101	2025-09-01	1	500.00
102	2025-09-03	2	1500.00
103	2025-09-05	1	700.00
104	2025-09-07	3	1200.00



---

🔹 SQL Queries

1️⃣ INNER JOIN

Shows only customers who have placed orders.

SELECT Customers.customer_id, Customers.customer_name, Orders.order_id, Orders.amount
FROM Customers
INNER JOIN Orders
ON Customers.customer_id = Orders.customer_id;


---

2️⃣ LEFT JOIN

Shows all customers, even if they have no orders.

SELECT Customers.customer_id, Customers.customer_name, Orders.order_id, Orders.amount
FROM Customers
LEFT JOIN Orders
ON Customers.customer_id = Orders.customer_id;


---

3️⃣ RIGHT JOIN

Shows all orders, even if no matching customer exists.

SELECT Customers.customer_id, Customers.customer_name, Orders.order_id, Orders.amount
FROM Customers
RIGHT JOIN Orders
ON Customers.customer_id = Orders.customer_id;


---

4️⃣ FULL OUTER JOIN

Shows all customers and all orders (even if no match).
(MySQL/SQLite don’t support FULL JOIN, so we simulate using UNION.)

SELECT Customers.customer_id, Customers.customer_name, Orders.order_id, Orders.amount
FROM Customers
LEFT JOIN Orders
ON Customers.customer_id = Orders.customer_id
UNION
SELECT Customers.customer_id, Customers.customer_name, Orders.order_id, Orders.amount
FROM Customers
RIGHT JOIN Orders
ON Customers.customer_id = Orders.customer_id;


---

✅ Outcome

Created two related tables (Customers, Orders)

Practiced INNER, LEFT, RIGHT, FULL joins

Learned how to merge and analyze data across multiple tables
