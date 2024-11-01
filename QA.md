What are your risk areas? Identify and describe them.
Risks we face include columns incomplete data, or columns we Null values, inconsistent format, duplicates and abnomalies(outliers)



QA Process:
Describe your QA process and include the SQL queries used to execute it.
We run a QA process to identify columns that have Null values, duplicates , foreign keys between the tables, run filtering test by dates.

```sql
-- check for Null values
SELECT * 
FROM all_sessions
WHERE fullVisitorId IS NULL OR visitId IS NULL;

-- Check for duplicate records 
SELECT fullVisitorId, visitId, COUNT(*)
FROM all_sessions
GROUP BY fullVisitorId, visitId
HAVING COUNT(*) > 1;

-- Verify that foreign keys exist 
SELECT sbs.productSku
FROM sales_by_sku sbs
LEFT JOIN products p ON p.sku = sbs.productSku
WHERE p.sku IS NULL;

--Filter test by date
SELECT *
FROM all_sessions
WHERE date::DATE BETWEEN '2016-01-01' AND '2017-12-31'
LIMIT 10;

