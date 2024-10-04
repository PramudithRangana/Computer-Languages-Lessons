# SQL TUTORIAL


### **1. Create a Database**

**Explanation:**
To create a new database in SQL, use the `CREATE DATABASE` statement. This sets up a new database where tables, views, stored procedures, and other database objects can be stored.

**Syntax:**
```sql
CREATE DATABASE database_name;
```

**Example:**
```sql
CREATE DATABASE my_database;
```

---

### **2. Activate the Database**

**Explanation:**
Once a database is created, it needs to be selected as the active database to perform operations within it. Use the `USE` statement to activate a database.

**Syntax:**
```sql
USE database_name;
```

**Example:**
```sql
USE my_database;
```

---

### **3. Alter the Database**

**Explanation:**
The `ALTER DATABASE` statement allows you to modify an existing database's properties, like changing the character set or collation.

**Syntax:**
```sql
ALTER DATABASE database_name 
MODIFY PROPERTY value;
```

**Example:**
```sql
ALTER DATABASE my_database 
CHARACTER SET utf8mb4 
COLLATE utf8mb4_unicode_ci;
```

**Example 2 :**
```sql
ALTER DATABASE my_DB READ ONLY = 1;
```

---

### **4. Create a Table**

**Explanation:**
The `CREATE TABLE` statement is used to create a new table in the database.

**Syntax:**
```sql
CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);
```

**Example:**
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    position VARCHAR(50),
    salary DECIMAL(10, 2)
);
```

---

### **5. Describe the Table**

**Explanation:**
The `DESCRIBE` statement (or `SHOW COLUMNS`) is used to get the structure of a table, including columns, their types, and constraints.

**Syntax:**
```sql
DESCRIBE table_name;
```

**Example:**
```sql
DESCRIBE employees;
```

---

### **6. Rename the Table**

**Explanation:**
The `RENAME TABLE` statement allows you to rename an existing table.

**Syntax:**
```sql
RENAME TABLE old_table_name TO new_table_name;
```

**Example:**
```sql
RENAME TABLE employees TO staff;
```

---

### **7. Add a New Column to the Table**

**Explanation:**
The `ALTER TABLE` statement is used to add a new column to an existing table.

**Syntax:**
```sql
ALTER TABLE table_name
ADD column_name datatype constraints;
```

**Example:**
```sql
ALTER TABLE employees
ADD hire_date DATE;
```

---

### **8. Delete a Column from the Table**

**Explanation:**
You can remove a column from a table using the `ALTER TABLE` statement with the `DROP COLUMN` clause.

**Syntax:**
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

**Example:**
```sql
ALTER TABLE employees
DROP COLUMN hire_date;
```

---

### **9. Modify a Column of the Table**

**Explanation:**
To modify an existing column's datatype or constraints, use the `ALTER TABLE` statement with the `MODIFY` clause.

**Syntax:**
```sql
ALTER TABLE table_name
MODIFY COLUMN column_name new_datatype new_constraints;
```

**Example:**
```sql
ALTER TABLE employees
MODIFY COLUMN salary DECIMAL(12, 2);
```

---

### **10. Rename a Column of the Table**

**Explanation:**
To rename an existing column, use the `ALTER TABLE` statement with the `CHANGE` clause.

**Syntax:**
```sql
ALTER TABLE table_name
CHANGE old_column_name new_column_name datatype constraints;
```

**Example:**
```sql
ALTER TABLE employees
CHANGE position job_title VARCHAR(50);
```

---

### **11. Change the Position of a Column**

**Explanation:**
You can change the position of a column in a table using the `ALTER TABLE` statement with `AFTER` or `FIRST` keywords.

**Syntax:**
```sql
ALTER TABLE table_name
MODIFY COLUMN column_name datatype constraints
AFTER another_column;

ALTER TABLE table_name
MODIFY COLUMN column_name datatype constraints
FIRST;
```

**Example:**
```sql
ALTER TABLE employees
MODIFY COLUMN job_title VARCHAR(50) AFTER name;

ALTER TABLE employees
MODIFY COLUMN id INT FIRST;
```

---

### **12. IS NULL**

**Explanation:**
The `IS NULL` condition is used to test for empty (NULL) values.

**Syntax:**
```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```

**Example:**
```sql
SELECT name
FROM employees
WHERE salary IS NULL;
```

---

### **13. IS NOT NULL**

**Explanation:**
The `IS NOT NULL` condition is used to test for non-empty (non-NULL) values.

**Syntax:**
```sql
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

**Example:**
```sql
SELECT name
FROM employees
WHERE salary IS NOT NULL;
```

---

### **14. Make Unique Column**

**Explanation:**
A unique constraint ensures that all values in a column are different.

**Syntax:**
```sql
ALTER TABLE table_name
ADD CONSTRAINT constraint_name UNIQUE (column_name);
```

**Example:**
```sql
ALTER TABLE employees
ADD CONSTRAINT unique_email UNIQUE (email);
```

---

### **15. Add Primary Key to the Table**

**Explanation:**
The primary key constraint uniquely identifies each record in a table. It implies `NOT NULL` and `UNIQUE`.

**Syntax:**
```sql
ALTER TABLE table_name
ADD PRIMARY KEY (column_name);
```

**Example:**
```sql
ALTER TABLE employees
ADD PRIMARY KEY (id);
```

---

### **16. Delete Primary Key from the Table**

**Explanation:**
The primary key constraint can be removed using the `ALTER TABLE` statement.

**Syntax:**
```sql
ALTER TABLE table_name
DROP PRIMARY KEY;
```

**Example:**
```sql
ALTER TABLE employees
DROP PRIMARY KEY;
```

---

### **17. Add Foreign Key to the Table**

**Explanation:**
A foreign key is a field (or collection of fields) in one table that uniquely identifies a row of another table. It creates a relationship between two tables.

**Syntax:**
```sql
ALTER TABLE table_name
ADD CONSTRAINT fk_name
FOREIGN KEY (column_name)
REFERENCES parent_table_name(parent_column_name);
```

**Example:**
```sql
ALTER TABLE employees
ADD CONSTRAINT fk_department
FOREIGN KEY (department_id)
REFERENCES departments(id);
```

---

### **18. SET fk_check = 0;**

**Explanation:**
This command disables foreign key checks in SQL, allowing operations that would normally violate foreign key constraints.

**Syntax:**
```sql
SET FOREIGN_KEY_CHECKS = 0;
```

**Example:**
```sql
SET FOREIGN_KEY_CHECKS = 0;
```

---

### **19. SET fk_check = 1;**

**Explanation:**
This command re-enables foreign key checks after they have been disabled.

**Syntax:**
```sql
SET FOREIGN_KEY_CHECKS = 1;
```

**Example:**
```sql
SET FOREIGN_KEY_CHECKS = 1;
```

---

### **20. Delete Foreign Key from the Table**

**Explanation:**
To remove a foreign key constraint from a table, use the `ALTER TABLE` statement with the `DROP FOREIGN KEY` clause.

**Syntax:**
```sql
ALTER TABLE table_name
DROP FOREIGN KEY fk_name;
```

**Example:**
```sql
ALTER TABLE employees
DROP FOREIGN KEY fk_department;
```

---

### **21. Add Composite Primary Key to the Table**

**Explanation:**
A composite primary key is a primary key that consists of multiple columns.

**Syntax:**
```sql
ALTER TABLE table_name
ADD PRIMARY KEY (column1, column2, ...);
```

**Example:**
```sql
ALTER TABLE employees
ADD PRIMARY KEY (id, department_id);
```

---

### **22. Delete Composite Primary Key from the Table**

**Explanation:**
To remove a composite primary key, use the `ALTER TABLE` statement.

**Syntax:**
```sql
ALTER TABLE table_name
DROP PRIMARY KEY;
```

**Example:**
```sql
ALTER TABLE employees
DROP PRIMARY KEY;
```

---

### **23. ON DELETE CASCADE**

**Explanation:**
The `ON DELETE CASCADE` option ensures that when a record in the parent table is deleted, the corresponding records in the child table are also deleted.

**Syntax:**
```sql
ALTER TABLE child_table
ADD CONSTRAINT fk_name
FOREIGN KEY (column_name)
REFERENCES parent_table(column_name)
ON DELETE CASCADE;
```

**Example:**
```sql
ALTER TABLE employees
ADD CONSTRAINT fk_department
FOREIGN KEY (department_id)
REFERENCES departments(id)
ON DELETE CASCADE;
```

---

### **24. ON DELETE SET NULL**

**Explanation:**
The `ON DELETE SET NULL` option sets the foreign key value to `NULL` if the corresponding record in the parent table is deleted.

**Syntax:**
```sql
ALTER TABLE child_table
ADD CONSTRAINT fk_name
FOREIGN KEY (column_name)
REFERENCES parent_table(column_name)
ON DELETE SET NULL;
```

**Example:**
```sql
ALTER TABLE employees
ADD CONSTRAINT fk_department
FOREIGN KEY (department_id)
REFERENCES departments(id)
ON DELETE SET NULL;
```
---

### **25. Default Values**

**Explanation:**
The `DEFAULT` keyword is used to set a default value for a column when no value is specified during insertion.

**Syntax:**
```sql
CREATE TABLE table_name (
    column_name datatype DEFAULT default_value
);
```

**Example:**
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    position VARCHAR(50),
    salary DECIMAL(10, 2) DEFAULT 50000.00
);
```

---

### **26. Auto Increment**

**Explanation:**
The `AUTO_INCREMENT` attribute is used to automatically generate unique values for a column, typically for the primary key.

**Syntax:**
```sql
CREATE TABLE table_name (
    column_name INT AUTO_INCREMENT,
    PRIMARY KEY(column_name)
);
```

**Example:**
```sql
CREATE TABLE employees (
    id INT AUTO_INCREMENT,
    name VARCHAR(100),
    PRIMARY KEY(id)
);
```
---
### **27. Change the Start Number of Auto Increment**

**Explanation:**
To start the `AUTO_INCREMENT` sequence at a specific number, use the `ALTER TABLE` statement.

**Syntax:**
```sql
ALTER TABLE table_name AUTO_INCREMENT = start_value;
```

**Example:**
```sql
ALTER TABLE employees AUTO_INCREMENT = 1000;
```

---

### **28. SET AUTOCOMMIT = OFF;**

**Explanation:**
This command disables automatic commit of transactions. Changes made will not be saved until a `COMMIT` is issued.

**Syntax:**
```sql
SET AUTOCOMMIT = 0;
```

**Example:**
```sql
SET AUTOCOMMIT = OFF;
```

---

### **29. SET AUTOCOMMIT = ON;**

**Explanation:**
This command re-enables automatic commit, where each SQL statement is immediately committed.

**Syntax:**
```sql
SET AUTOCOMMIT = 1;
```

**Example:**
```sql
SET AUTOCOMMIT = ON;
```

---

### **30. COMMIT;**

**Explanation:**
The `COMMIT` statement is used to save all changes made in the current transaction to the database.

**Syntax:**
```sql
COMMIT;
```

**Example:**
```sql
UPDATE employees SET salary = 55000 WHERE id = 1;
COMMIT;
```

---
### **31. ROLLBACK;**

**Explanation:**
The `ROLLBACK` statement is used to undo changes made in the current transaction.

**Syntax:**
```sql
ROLLBACK;
```

**Example:**
```sql
UPDATE employees SET salary = 55000 WHERE id = 1;
ROLLBACK;
```

---

### **32. Insert Data into the Table**

**Explanation:**
The `INSERT INTO` statement is used to add new records into a table.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

**Example:**
```sql
INSERT INTO employees (name, position, salary)
VALUES ('John Doe', 'Manager', 60000);
```

---

### **33. Update Data of the Table**

**Explanation:**
The `UPDATE` statement is used to modify existing records in a table.

**Syntax:**
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

**Example:**
```sql
UPDATE employees
SET salary = 65000
WHERE name = 'John Doe';
```

---

### **34. Delete Data from the Table**

**Explanation:**
The `DELETE` statement is used to remove records from a table.

**Syntax:**
```sql
DELETE FROM table_name
WHERE condition;
```

**Example:**
```sql
DELETE FROM employees
WHERE id = 1;
```

---

### **35. Read Data from the Table**

**Explanation:**
The `SELECT` statement is used to query and retrieve data from a table.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT name, salary
FROM employees
WHERE position = 'Manager';
```

---

### **36. Add CHECK Statement**

**Explanation:**
The `CHECK` constraint is used to limit the value range that can be placed in a column.

**Syntax:**
```sql
ALTER TABLE table_name
ADD CONSTRAINT constraint_name CHECK (condition);
```

**Example:**
```sql
ALTER TABLE employees
ADD CONSTRAINT check_salary CHECK (salary >= 0);
```

---

### **37. Delete the CHECK Statement**

**Explanation:**
The `CHECK` constraint can be removed using the `ALTER TABLE` statement.

**Syntax:**
```sql
ALTER TABLE table_name
DROP CONSTRAINT constraint_name;
```

**Example:**
```sql
ALTER TABLE employees
DROP CONSTRAINT check_salary;
```

---

### **38. Logical Operators (AND, OR, NOT, BETWEEN, IN)**

**Explanation:**
Logical operators are used to combine multiple conditions in SQL.

**Examples:**

- **AND:**
  ```sql
  SELECT * FROM employees
  WHERE position = 'Manager' AND salary > 50000;
  ```

- **OR:**
  ```sql
  SELECT * FROM employees
  WHERE position = 'Manager' OR position = 'Engineer';
  ```

- **NOT:**
  ```sql
  SELECT * FROM employees
  WHERE NOT salary < 50000;
  ```

- **BETWEEN:**
  ```sql
  SELECT * FROM employees
  WHERE salary BETWEEN 40000 AND 60000;
  ```

- **IN:**
  ```sql
  SELECT * FROM employees
  WHERE position IN ('Manager', 'Engineer');
  ```

---

### **39. Comparison Operators (<, >, <=, >=, !=, =)**

**Explanation:**
Comparison operators are used to compare two values.

**Examples:**

- **<:**
  ```sql
  SELECT * FROM employees
  WHERE salary < 50000;
  ```

- **>:**
  ```sql
  SELECT * FROM employees
  WHERE salary > 50000;
  ```

- **<=:**
  ```sql
  SELECT * FROM employees
  WHERE salary <= 60000;
  ```

- **>=:**
  ```sql
  SELECT * FROM employees
  WHERE salary >= 40000;
  ```

- **!= (or <>):**
  ```sql
  SELECT * FROM employees
  WHERE salary != 50000;
  ```

- **=:**
  ```sql
  SELECT * FROM employees
  WHERE salary = 50000;
  ```

---

### **40. Create Indexes**

**Explanation:**
Indexes are used to speed up the retrieval of data from a table.

**Syntax:**
```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

**Example:**
```sql
CREATE INDEX idx_name
ON employees (name);
```

---

### **41. Show Indexes**

**Explanation:**
To view the indexes on a table, use the `SHOW INDEX` statement.

**Syntax:**
```sql
SHOW INDEX FROM table_name;
```

**Example:**
```sql
SHOW INDEX FROM employees;
```

---

### **42. Delete Indexes**

**Explanation:**
To remove an index from a table, use the `DROP INDEX` statement.

**Syntax:**
```sql
DROP INDEX index_name ON table_name;
```

**Example:**
```sql
DROP INDEX idx_name ON employees;
```

---

### **43. LIMIT**

**Explanation:**
The `LIMIT` clause is used to specify the number of records to return.

**Syntax:**
```sql
SELECT column_names
FROM table_name
LIMIT number;
```

**Example:**
```sql
SELECT * FROM employees
LIMIT 5;
```

---

### **44. DISTINCT**

**Explanation:**
The `DISTINCT` keyword is used to return only distinct (different) values.

**Syntax:**
```sql
SELECT DISTINCT column_name
FROM table_name;
```

**Example:**
```sql
SELECT DISTINCT position
FROM employees;
```

---

### **45. GROUP BY**

**Explanation:**
The `GROUP BY` statement groups rows that have the same values in specified columns into summary rows.

**Syntax:**
```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name;
```

**Example:**
```sql
SELECT position, COUNT(*)
FROM employees
GROUP BY position;
```

---

### **46. HAVING**

**Explanation:**
The `HAVING` clause is used to filter records that are aggregated by the `GROUP BY` clause.

**Syntax:**
```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Example:**
```sql
SELECT position, COUNT(*)
FROM employees
GROUP BY position
HAVING COUNT(*) > 1;
```

---

### **47. ORDER BY**

**Explanation:**
The `ORDER BY` clause is used to sort the result-set in ascending or descending order.

**Syntax:**
```sql
SELECT column_name
FROM table_name
ORDER BY column_name ASC|DESC;
```

**Example:**
```sql
SELECT * FROM employees
ORDER BY salary DESC;
```

---

### **48. ROLLUP**

**Explanation:**
The `ROLLUP` operator is used in SQL to generate subtotals and grand totals in the result set. It's typically used in conjunction with the `GROUP BY` clause. The `ROLLUP` operator creates a hierarchical grouping, starting from the most detailed level of grouping and progressively aggregating at higher levels.

**Syntax:**
```sql
SELECT column_name(s), aggregate_function(column_name)
FROM table_name
GROUP BY ROLLUP (column_name1, column_name2, ...);
```

**Example:**
Suppose you have a `sales` table with columns `region`, `product`, and `sales_amount`. You want to calculate the total sales for each product within each region, and also the total sales for each region and overall.

```sql
SELECT region, product, SUM(sales_amount) AS total_sales
FROM sales
GROUP BY ROLLUP (region, product);
```

**Explanation of the Result:**

- The result will first group by `region` and `product` to show the total sales for each product within each region.
- Next, it will show the subtotal for each `region` (across all products in that region).
- Finally, it will show the grand total (across all regions and all products).

**Sample Output:**
```plaintext
| Region  | Product  | Total_Sales |
|---------|----------|-------------|
| North   | A        | 5000        |
| North   | B        | 3000        |
| North   | NULL     | 8000        | -- Subtotal for North region
| South   | A        | 4000        |
| South   | B        | 2000        |
| South   | NULL     | 6000        | -- Subtotal for South region
| NULL    | NULL     | 14000       | -- Grand total
```

**Key Points:**

- **NULL values** in the result indicate the summary rows generated by `ROLLUP`.
- The hierarchy of `ROLLUP` is determined by the order of columns in the `GROUP BY` clause. The most detailed grouping is listed first, with higher-level groupings following.

`ROLLUP` is especially useful for reports where you need summaries at various levels of aggregation, such as sales by product, by region, and overall.
---


---

### **49. Functions**

#### **a. COUNT()**

**Explanation:**
The `COUNT()` function returns the number of rows that match a specified condition.

**Syntax:**
```sql
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT COUNT(*)
FROM employees
WHERE salary > 50000;
```

---

#### **b. AVG()**

**Explanation:**
The `AVG()` function returns the average value of a numeric column.

**Syntax:**
```sql
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT AVG(salary)
FROM employees;
```

---

#### **c. SUM()**

**Explanation:**
The `SUM()` function returns the total sum of a numeric column.

**Syntax:**
```sql
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT SUM(salary)
FROM employees;
```

---

#### **d. MAX()**

**Explanation:**
The `MAX()` function returns the maximum value in a numeric column.

**Syntax:**
```sql
SELECT MAX(column_name)
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT MAX(salary)
FROM employees;
```

---

#### **e. MIN()**

**Explanation:**
The `MIN()` function returns the minimum value in a numeric column.

**Syntax:**
```sql
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT MIN(salary)
FROM employees;
```

---

#### **f. CONCAT()**

**Explanation:**
The `CONCAT()` function is used to concatenate two or more strings into one.

**Syntax:**
```sql
SELECT CONCAT(string1, string2, ...) AS alias_name;
```

**Example:**
```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name
FROM employees;
```

---

### **50. Wildcard**

#### **a. LIKE**

**Explanation:**
The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

**Syntax:**
```sql
SELECT column_name
FROM table_name
WHERE column_name LIKE pattern;
```

**Example:**
```sql
SELECT name
FROM employees
WHERE name LIKE 'J%'; -- Names starting with 'J'
```

---

### **51. UNION**

**Explanation:**
The `UNION` operator is used to combine the result sets of two or more `SELECT` statements. It removes duplicate values.

**Syntax:**
```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

**Example:**
```sql
SELECT name FROM employees
UNION
SELECT name FROM managers;
```

---

### **52. JOIN**

**Explanation:**
The `JOIN` clause is used to combine rows from two or more tables, based on a related column between them.

**Syntax:**

- **INNER JOIN:**
  ```sql
  SELECT columns
  FROM table1
  INNER JOIN table2
  ON table1.column = table2.column;
  ```

- **LEFT JOIN:**
  ```sql
  SELECT columns
  FROM table1
  LEFT JOIN table2
  ON table1.column = table2.column;
  ```

- **RIGHT JOIN:**
  ```sql
  SELECT columns
  FROM table1
  RIGHT JOIN table2
  ON table1.column = table2.column;
  ```

- **FULL JOIN:**
  ```sql
  SELECT columns
  FROM table1
  FULL OUTER JOIN table2
  ON table1.column = table2.column;
  ```

**Example (INNER JOIN):**
```sql
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.id;
```

---

### **53. Nested Queries**

**Explanation:**
Nested queries (or subqueries) are queries within another SQL query. They can be used in `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statements.

**Syntax:**
```sql
SELECT column_name
FROM table_name
WHERE column_name = (SELECT column_name FROM another_table WHERE condition);
```

**Example:**
```sql
SELECT name
FROM employees
WHERE department_id = (SELECT id FROM departments WHERE department_name = 'HR');
```

---

### **54. Stored Procedures**

**Explanation:**
A stored procedure is a prepared SQL code that you can save and reuse. 

**Syntax:**

- **Create Stored Procedure:**
  ```sql
  CREATE PROCEDURE procedure_name (parameters)
  BEGIN
      SQL statements;
  END;
  ```

- **Call Stored Procedure:**
  ```sql
  CALL procedure_name(parameters);
  ```

**Example:**
```sql
CREATE PROCEDURE GetEmployeeSalary(IN emp_id INT)
BEGIN
    SELECT salary
    FROM employees
    WHERE id = emp_id;
END;

CALL GetEmployeeSalary(1);
```

---

### **55. Triggers**

#### **a. Create a Trigger**

**Explanation:**
A trigger is a set of SQL statements that automatically executes in response to certain events on a table (e.g., `INSERT`, `UPDATE`, `DELETE`).

**Syntax:**
```sql
CREATE TRIGGER trigger_name
AFTER|BEFORE INSERT|UPDATE|DELETE
ON table_name
FOR EACH ROW
BEGIN
    SQL statements;
END;
```

**Example:**
```sql
CREATE TRIGGER before_employee_insert
BEFORE INSERT ON employees
FOR EACH ROW
BEGIN
    SET NEW.hire_date = CURDATE();
END;
```

---

#### **b. Delete a Trigger**

**Explanation:**
You can remove a trigger using the `DROP TRIGGER` statement.

**Syntax:**
```sql
DROP TRIGGER trigger_name;
```

**Example:**
```sql
DROP TRIGGER before_employee_insert;
```

---

### **56. Delete a Table from the Database**

**Explanation:**
The `DROP TABLE` statement is used to delete a table and its data permanently from the database.

**Syntax:**
```sql
DROP TABLE table_name;
```

**Example:**
```sql
DROP TABLE employees;
```

---

### **57. Delete the Database**

**Explanation:**
The `DROP DATABASE` statement is used to delete a database and all its tables, views, stored procedures, and other objects permanently.

**Syntax:**
```sql
DROP DATABASE database_name;
```

**Example:**
```sql
DROP DATABASE my_database;
```

---

This concludes the tutorial. Each topic covered here provides essential tools and techniques for effectively managing and querying databases using SQL.