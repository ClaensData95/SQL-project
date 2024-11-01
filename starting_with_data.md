Question 1: Return all the columns from the products table

SQL Queries:
```sql
SELECT*FROM products
```



Answer:This query returns the products table as a whole.



Question 2: Create a join between the products table and sales_report

SQL Queries:
```
SELECT sbs.productSku
FROM sales_by_sku sbs
JOIN products p ON p.sku = sbs.productSku
```
Answer:This query returns only the matching values between the two tables



Question 3: Return the Null values of the fullvisitorID column from the all_sessions table


SQL Queries:
```
SELECT*
FROM all_sessions
Where fullvisitorID IS NULL
```

Answer:This query returns all the rows  where fullvisitorID is NULL



Question 4: Return all rows that contain USA in the all_sessions table

SQL Queries:
```
SELECT*FROM all_sessions
WHERE country = 'United States'
```



Answer:Query returns all the rows that contain USA



Question 5: Identify Primary key in products table

SQL Queries:
```sql
SELECT count(sku) FROM products
GROUP BY sku
HAVING count(sku) > 1
```

Answer:product.sku is the unique identifier. 
