# Data-Manipulation-on-Sales

###### This code selects everything from the customers table in the sql_store database ordering the results by first name alphabetically.
```
USE sql_store;
SELECT *
FROM CUSTOMERS
ORDER BY first_name;
```
###### [points + 10] and [(points*10)+100] does not exist in the customers table. By writing this query, the results create a temporary column that displays the manipulated result of the [points] column.
```
SELECT last_name, first_name, points, points + 10
FROM CUSTOMERS;

SELECT last_name, first_name, points, (points*10)+100
FROM CUSTOMERS;
```
###### Now, Instead of creating a temporary column, I have created a permanent column that manipulates the [points] column into [(points + 10)*100] giving it the name of [discount_factor].
```
ALTER TABLE customers
ADD Column discount_factor INT;

UPDATE customers
SET discount_factor = (points + 10)*100;

SELECT last_name, first_name, points, discount_factor
FROM CUSTOMERS;
```
