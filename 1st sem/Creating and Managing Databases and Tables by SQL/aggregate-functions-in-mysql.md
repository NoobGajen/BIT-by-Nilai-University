---
description: >-
  Aggregate functions in MySQL allow us to perform calculations on multiple rows
  of a table's column and return a value. These are useful for
  calculating/summarizing data.
---

# Aggregate Functions in MySQL

**Selecting a Database**

```sql
USE sakila;
```

### Common Aggregate Functions

#### A. `AVG()`

Calculates the average value of a numeric column.

```sql
SELECT AVG(amount) AS average_payment FROM payment;
```

#### B. `COUNT()`

Counts the number of rows or non-NULL values in a column.

```sql
SELECT COUNT(*) AS total_payments FROM payment;
```

#### C. `MAX()`

Returns the maximum value in a column.

```sql
SELECT MAX(amount) AS highest_payment FROM payment;
```

#### D. `MIN()`

Returns the minimum value in a column.

```sql
SELECT MIN(amount) AS lowest_payment FROM payment;
```

#### E. `STDDEV()`

Calculates the standard deviation of the values in a column.

```sql
SELECT STDDEV(amount) AS payment_stddev FROM payment;
```

#### F. `SUM()`

Returns the sum of all values in a column.

```sql
SELECT SUM(amount) AS total_payment FROM payment;
```

#### G. `DISTINCT()`

Removes duplicate values in a result set.

```sql
SELECT DISTINCT(customer_id) FROM payment;
```

**Counting Unique Rentals**

```sql
SELECT COUNT(DISTINCT(rental_id)) AS unique_rentals FROM rental;
```

* `COUNT(DISTINCT(rental_id)) AS unique_rentals`: Counts the number of unique rental IDs in the `rental` table.

#### Using Multiple Aggregate Functions in One Query

We can use multiple aggregate functions in a single query to get different types of summaries.

```sql
SELECT
  COUNT(*) AS num_payments,
  SUM(amount) AS total_payment,
  AVG(amount) AS avg_payment,
  MAX(amount) AS max_payment,
  MIN(amount) AS min_payment,
  STDDEV(amount) AS payment_stddev,
  VARIANCE(amount) AS payment_variance
FROM payment;
```

* This query returns the number of payments, total payment amount, average payment, maximum payment, minimum payment, standard deviation, and variance of payments.

#### Using Subqueries with Aggregate Functions

Subqueries can be used within aggregate functions to derive complex summaries.

```sql
SELECT MAX(avg_amount)
FROM (
    SELECT AVG(amount) AS avg_amount
    FROM payment
) AS avg_subquery;
```

* `MAX(avg_amount)`: Finds the highest average payment amount.
* `SELECT AVG(amount) AS avg_amount FROM payment`: The inner subquery calculates the average payment amount.
* `AS avg_subquery`: Aliases the subquery result set for use in the outer query.

### 1. Using Aggregate Functions with `GROUP BY`

#### Counting Rentals Per Day

**Using `DATE_FORMAT()`**

```sql
SELECT DATE_FORMAT(rental_date, '%Y-%m-%d') AS date, COUNT(*) AS rent_count
FROM rental
GROUP BY date;
```

* **`DATE_FORMAT(rental_date, '%Y-%m-%d')`**: Converts `rental_date` to a string in `YYYY-MM-DD` format.
* **`COUNT(*)`**: Counts the number of rentals for each date.
* **`GROUP BY date`**: Groups the results by the formatted date.

**Using `DATE()`**

```sql
SELECT DATE(rental_date) AS rent_date, COUNT(*) AS rent_count
FROM rental
GROUP BY rent_date;
```

* **`DATE(rental_date)`**: Extracts the date part of `rental_date`, ignoring the time.
* **`COUNT(*)`**: Counts the number of rentals for each extracted date.
* **`GROUP BY rent_date`**: Groups the results by the extracted date.

#### **Counting Rentals within a Date Range**

```sql
SELECT DATE_FORMAT(rental_date, '%Y-%m-%d') AS date, COUNT(*) AS rent_count
FROM rental
WHERE rental_date BETWEEN '2005-07-05' AND '2005-07-30'
GROUP BY date;

-- OR, 
SELECT DATE_FORMAT(rental_date, '%Y-%m-%d') AS date, COUNT(*) AS rent_count
FROM rental
WHERE rental_date >= '2005-07-05' AND rental_date <= '2005-07-30'
GROUP BY date;
```

* `DATE_FORMAT(rental_date, '%Y-%m-%d') AS date`: Converts `rental_date` to a string in `YYYY-MM-DD` format.
* `COUNT(*) AS rent_count`: Counts the number of rentals for each date.
* `WHERE rental_date BETWEEN '2005-07-05' AND '2005-07-30'`: Filters rentals to those between July 5, 2005, and July 30, 2005.
* `WHERE rental_date >= '2005-07-05' AND rental_date <= '2005-07-30'`: Filters rentals to those between July 5, 2005, and July 30, 2005.
* `GROUP BY date`: Groups the results by the formatted date.

#### Summing Payments Per Customer

```sql
SELECT customer_id, SUM(amount) AS total_payment
FROM payment
GROUP BY customer_id
LIMIT 10;
```

* **`SUM(amount)`**: Calculates the total payment amount for each customer.
* **`GROUP BY customer_id`**: Groups the results by `customer_id`.
* **`LIMIT 10`**: Limits the results to the first 10 customers.

### 2. Using the `HAVING` Clause

#### Finding Customers with Total Payments Less Than 125

```sql
SELECT customer_id, SUM(amount) AS total_payment
FROM payment
GROUP BY customer_id
HAVING SUM(amount) < 125
LIMIT 10;
```

* **`SUM(amount)`**: Calculates the total payment amount for each customer.
* **`GROUP BY customer_id`**: Groups the results by `customer_id`.
* **`HAVING SUM(amount) < 125`**: Filters the groups to include only those with a total payment less than 125.
* **`LIMIT 10`**: Limits the results to the first 10 customers.

### 3. Using Other Aggregate Functions

#### Finding the Maximum Average Payment Amount

```sql
SELECT MAX(avg_amount) AS max_avg_amount
FROM (
    SELECT AVG(amount) AS avg_amount
    FROM payment
    GROUP BY customer_id
) AS avg_subquery;
```

* **Subquery**:
  * **`AVG(amount)`**: Calculates the average payment amount for each customer.
  * **`GROUP BY customer_id`**: Groups the results by `customer_id`.
* **Outer Query**:
  * **`MAX(avg_amount)`**: Finds the maximum average payment amount from the subquery results.

#### Finding the Minimum Payment Amount Per Customer

```sql
SELECT customer_id, MIN(amount) AS min_payment
FROM payment
GROUP BY customer_id
LIMIT 10;
```

* **`MIN(amount)`**: Finds the minimum payment amount for each customer.
* **`GROUP BY customer_id`**: Groups the results by `customer_id`.
* **`LIMIT 10`**: Limits the results to the first 10 customers.

#### Finding the Minimum Payment Amount  is not equal to 0.99 Per Customer

```sql
SELECT customer_id, MIN(amount) AS min_payment
FROM payment
GROUP BY customer_id
HAVING MIN(amount) <> 0.99;

-- OR,
SELECT customer_id, MIN(amount) AS min_payment
FROM payment
GROUP BY customer_id
HAVING MIN(amount) != 0.99;

-- OR,
SELECT customer_id, MIN(amount) AS min_payment
FROM payment
GROUP BY customer_id
HAVING NOT MIN(amount) = 0.99;
```

* **`MIN(amount)`**: Finds the minimum payment amount for each customer.
* **`GROUP BY customer_id`**: Groups the results by `customer_id`.
* **`HAVING MIN(amount) <> 0.99`**: Filters the groups to include only those where the minimum payment amount is not equal to 0.99.
* **`HAVING MIN(amount) != 0.99`**: Another way to filter the groups to include only those where the minimum payment amount is not equal to 0.99.
* **`HAVING NOT MIN(amount) = 0.99`**: Another way to filter the groups to include only those where the minimum payment amount is not equal to 0.99, using the `NOT` keyword.

#### Finding the Average Payment Amount Per Customer

```sql
SELECT customer_id, AVG(amount) AS avg_payment
FROM payment
GROUP BY customer_id
LIMIT 10;
```

* **`AVG(amount)`**: Calculates the average payment amount for each customer.
* **`GROUP BY customer_id`**: Groups the results by `customer_id`.
* **`LIMIT 10`**: Limits the results to the first 10 customers.

### Summary

* **`COUNT()`**: Counts the number of rows or non-NULL values in each group.
* **`SUM()`**: Calculates the sum of values in each group.
* **`AVG()`**: Computes the average value in each group.
* **`MAX()`**: Finds the maximum value in each group.
* **`MIN()`**: Finds the minimum value in each group.
* **`STDDEV()`**: Calculates the standard deviation of values in each group, measuring the amount of variation or dispersion.
* **`VARIANCE()`**: Computes the variance of values in each group, indicating the spread of values from the mean.
* **`GROUP BY`**: Groups rows with the same values into summary rows, allowing aggregate functions to be applied to each group.
* **`HAVING`**: Filters results based on conditions applied to the results of aggregate functions, often used in conjunction with `GROUP BY`.
