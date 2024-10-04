# MySQL Tutorial

## 1. Create a Database

To create a new database, use the `CREATE DATABASE` statement:

```sql
CREATE DATABASE my_database;
```

## 2. Activate the Database

To select the database to use, use the `USE` statement:

```sql
USE my_database;
```

## 3. Create a Table

To create a new table, use the `CREATE TABLE` statement:

```sql
CREATE TABLE my_table (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```

## 4. Describe the Table

To see the structure of the table, use the `DESCRIBE` statement:

```sql
DESCRIBE my_table;
```

## 5. Add a New Column to the Table

To add a new column, use the `ALTER TABLE` statement:

```sql
ALTER TABLE my_table ADD COLUMN email VARCHAR(255);
```

## 6. Delete a Column from the Table

To remove a column, use:

```sql
ALTER TABLE my_table DROP COLUMN email;
```

## 7. Null - Not Null

To set a column to allow NULL values or not:

```sql
ALTER TABLE my_table MODIFY COLUMN age INT NOT NULL;
```

## 8. Make a Column Unique

To ensure a column has unique values:

```sql
ALTER TABLE my_table ADD UNIQUE (email);
```

## 9. Add Primary Key to the Table

To add a primary key:

```sql
ALTER TABLE my_table ADD PRIMARY KEY (id);
```

## 10. Delete Primary Key from the Table

To remove the primary key:

```sql
ALTER TABLE my_table DROP PRIMARY KEY;
```

## 11. Add Foreign Key to the Table

To add a foreign key:

```sql
ALTER TABLE my_table ADD CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id);
```

## 12. Delete Foreign Key from the Table

To remove a foreign key:

```sql
ALTER TABLE my_table DROP FOREIGN KEY fk_user;
```

## 13. Add Composite Primary Key to the Table

To add a composite primary key:

```sql
ALTER TABLE my_table ADD PRIMARY KEY (column1, column2);
```

## 14. Delete Composite Primary Key from the Table

To remove a composite primary key:

```sql
ALTER TABLE my_table DROP PRIMARY KEY;
```

## 15. ON DELETE CASCADE

To set up cascading deletes:

```sql
ALTER TABLE my_table ADD CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE;
```

## 16. ON DELETE SET NULL

To set up setting NULL on delete:

```sql
ALTER TABLE my_table ADD CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE SET NULL;
```

## 17. Default Values

To set a default value for a column:

```sql
ALTER TABLE my_table MODIFY COLUMN status VARCHAR(10) DEFAULT 'active';
```
```sql
ALTER TABLE my_table ALTER col SET DEFAULT Now();
```

## 18. Auto Increment

To set a column to auto-increment:

```sql
ALTER TABLE my_table MODIFY COLUMN id INT AUTO_INCREMENT;
```

## 19. Insert Data into the Table

To insert data:

```sql
INSERT INTO my_table (name, age) VALUES ('John Doe', 30);
```

```sql
INSERT INTO my_table VALUES (CURRENT_DATE(), CURRENT_TIME(), NOW());
```

## 20. Update Data in the Table

To update existing data:

```sql
UPDATE my_table SET age = 31 WHERE name = 'John Doe';
```

## 21. Delete Data from the Table

To delete data:

```sql
DELETE FROM my_table WHERE name = 'John Doe';
```

## 22. Read Data from the Table

To read data:

```sql
SELECT * FROM my_table;
```

## 23. IN Keyword

To filter results using the `IN` keyword:

```sql
SELECT * FROM my_table WHERE age IN (25, 30, 35);
```

## 24. DISTINCT

To select distinct values:

```sql
SELECT DISTINCT age FROM my_table;
```

## 25. GROUP BY

To group results:

```sql
SELECT age, COUNT(*) FROM my_table GROUP BY age;
```

## 26. ORDER BY

To sort results:

```sql
SELECT * FROM my_table ORDER BY age DESC;
```

## 27. Functions

### COUNT

To count rows:

```sql
SELECT COUNT(*) FROM my_table;
```

### AVG

To calculate average:

```sql
SELECT AVG(age) FROM my_table;
```

### SUM

To calculate sum:

```sql
SELECT SUM(age) FROM my_table;
```

### MAX

To find maximum value:

```sql
SELECT MAX(age) FROM my_table;
```

### MIN

To find minimum value:

```sql
SELECT MIN(age) FROM my_table;
```

## 28. Wild Card - LIKE

To search for a pattern:

```sql
SELECT * FROM my_table WHERE name LIKE 'J%';
```

```sql
SELECT * FROM my_table WHERE date LIKE '____-08%';
```

## 29. UNION

To combine results from multiple queries:

```sql
SELECT name FROM table1
UNION
SELECT name FROM table2;
```

## 30. JOIN

To combine rows from multiple tables:

```sql
SELECT my_table.name, other_table.description
FROM my_table
JOIN other_table ON my_table.id = other_table.my_table_id;
```

## 31. Nested Queries

To use a query inside another query:

```sql
SELECT name FROM my_table
WHERE age IN (SELECT age FROM another_table WHERE condition);
```

## 32. Stored Procedures

### Create a Stored Procedure

```sql
DELIMITER //
CREATE PROCEDURE GetUser(IN userId INT)
BEGIN
    SELECT * FROM my_table WHERE id = userId;
END //
DELIMITER ;
```

### Call a Stored Procedure

```sql
CALL GetUser(1);
```

## 33. Trigger

### Create a Trigger

```sql
DELIMITER //
CREATE TRIGGER before_insert_my_table
BEFORE INSERT ON my_table
FOR EACH ROW
BEGIN
    SET NEW.created_at = NOW();
END //
DELIMITER ;
```

### Delete a Trigger

```sql
DROP TRIGGER before_insert_my_table;
```

## 34. Delete Table from the Database

To delete a table:

```sql
DROP TABLE my_table;
```

## 35. Delete the Database

To delete a database:

```sql
DROP DATABASE my_database;
```

---

Feel free to modify or expand on any of these sections based on your needs!