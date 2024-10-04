To interact with MySQL from the command line client, you'll use a variety of commands. Here are the most commonly used commands and their purposes:

### 1. **Connect to MySQL Server**

To start the MySQL command-line client and connect to the server:

```bash
mysql -u username -p
```

After running this command, you will be prompted to enter your password. Replace `username` with your MySQL user.

### 2. **Show Databases**

To list all databases on the server:

```sql
SHOW DATABASES;
```

### 3. **Use a Database**

To select a database to work with:

```sql
USE database_name;
```

### 4. **Show Tables**

To list all tables in the currently selected database:

```sql
SHOW TABLES;
```

### 5. **Describe Table Structure**

To view the structure of a specific table:

```sql
DESCRIBE table_name;
```

### 6. **Create a Database**

To create a new database:

```sql
CREATE DATABASE database_name;
```

### 7. **Drop a Database**

To delete an existing database:

```sql
DROP DATABASE database_name;
```

### 8. **Create a Table**

To create a new table:

```sql
CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);
```

### 9. **Drop a Table**

To delete an existing table:

```sql
DROP TABLE table_name;
```

### 10. **Insert Data**

To add new rows to a table:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### 11. **Update Data**

To modify existing rows in a table:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### 12. **Delete Data**

To remove rows from a table:

```sql
DELETE FROM table_name
WHERE condition;
```

### 13. **Select Data**

To retrieve data from a table:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
ORDER BY column1
LIMIT number;
```

### 14. **Show Table Structure**

To see the structure of a table, including columns, types, and other attributes:

```sql
SHOW COLUMNS FROM table_name;
```

### 15. **Show Indexes**

To list indexes on a table:

```sql
SHOW INDEX FROM table_name;
```

### 16. **Execute SQL from a File**

To execute SQL commands from a file:

```bash
mysql -u username -p database_name < file.sql
```

### 17. **Export Data**

To export data to a file:

```bash
mysqldump -u username -p database_name > backup.sql
```

### 18. **Import Data**

To import data from a file:

```bash
mysql -u username -p database_name < backup.sql
```

### 19. **Quit the MySQL Client**

To exit the MySQL command-line client:

```sql
QUIT;
```

> These commands should cover most of the basic interactions you'll need to perform with the MySQL command-line client.