# Types of Join in MySQL

<figure><img src=".gitbook/assets/Types of Join in MySQL.jpg" alt=""><figcaption></figcaption></figure>

A join in SQL is a powerful operation used to combine rows from two or more tables based on a related column. By using joins, we can retrieve data spread across multiple tables in a relational database. Joins include:

1. **Inner joins** (returning only matching rows)
2. **Outer joins** (left, right, and full join to include all rows from one or both tables, with NULLs where there is no match)
3. **Self joins** (compare rows within the same table)

## 1.) INNER JOIN

An **inner join** retrieves only the rows with match data in both tables. It is commonly used to get records that exist in both tables based on a related column.

```sql
-- SYNTAX of Inner Join
SELECT column(s) 
FROM tableA AS a 
INNER JOIN tableB AS b 
ON a.column_name = b.column_name;
```

<figure><img src=".gitbook/assets/INNER JOIN.png" alt=""><figcaption></figcaption></figure>

## 2.) **Outer Join**

### i.) LEFT JOIN

A LEFT JOIN returns all records from the left table (`tableA`), and the matched records from the right table (`tableB`). If there is no match, the result will contain `NULL` for the columns from `tableB`.

```sql
-- SYNTAX of Left Join
SELECT a.column1, a.column2, b.column3
FROM tableA AS a 
LEFT JOIN tableB AS b 
ON a.column_name = b.column_name;
```

<figure><img src=".gitbook/assets/LEFT JOIN.png" alt=""><figcaption></figcaption></figure>

### ii.) RIGHT JOIN

A RIGHT JOIN returns all records from the right table (`tableB`), and the matched records from the left table (`tableA`). If there is no match, the result will contain `NULL` for the columns from `tableA`.

```sql
-- SYNTAX of Right Join
SELECT a.column1, a.column2, b.column3
FROM tableA AS a
RIGHT JOIN tableB AS b 
ON a.column_name = b.column_name;
```

<figure><img src=".gitbook/assets/RIGHT JOIN.png" alt=""><figcaption></figcaption></figure>

### iii.) FULL OUTER JOIN

A FULL OUTER JOIN returns all records when there is a match in either table (`tableA` or `tableB`). Records that do not have a match will show `NULL` values for columns from the table without a match.

**Syntax:**

```sql
-- SYNTAX of Full Outer Join (By combining Left and Right Join)
SELECT a.column1, a.column2, b.column3
FROM tableA AS a
LEFT JOIN tableB AS b ON a.column_name = b.column_name;

UNION

SELECT a.column1, a.column2, b.column3
FROM tableA AS a
RIGHT JOIN tableB AS b ON a.column_name = b.column_name;

-- OR, SYNTAX of Full Outer Join (Doesn't work in my DBMS)
SELECT a.column1, a.column2, b.column3
FROM tableA AS a
FULL OUTER JOIN tableB AS b ON a.column_name = b.column_name;
```

<figure><img src=".gitbook/assets/FULL OUTER JOIN.png" alt=""><figcaption></figcaption></figure>

## 3.) Self Join





```sql
-- SYNTAX of Self Join
SELECT a.column1, a.column2, b.column3
FROM tableA AS a
LEFT JOIN tableA AS b ON a.column_name = b.column_name;
```

<figure><img src=".gitbook/assets/SELF JOIN.png" alt=""><figcaption></figcaption></figure>
