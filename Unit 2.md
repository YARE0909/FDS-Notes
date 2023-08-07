# SQLite

### Create

- SQLite **CREATE TABLE** statement is used to create a new table in any of the given database. Creating a basic table involves naming the table and defining its columns and each column's data type.

**Syntax:**
```sql
CREATE TABLE database_name.table_name(
   column1 datatype PRIMARY KEY(one or more columns),
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype
);
```

**Example:**
```sql
CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
);
```

### Select

- SQLite **SELECT** statement is used to fetch the data from a SQLite database table which returns data in the form of a result table. These result tables are also called **result sets**.

**Syntax:**
```sql
SELECT column1, column2, columnN FROM table_name;
SELECT * FROM table_name;
```

**Example:**
```sql
SELECT * FROM employee1 WHERE dept= "Sales";
```

### Insert

- SQLite **INSERT INTO** Statement is used to add new rows of data into a table in the database.

**Syntax:**
```sql
INSERT INTO TABLE_NAME [(column1, column2, column3,...columnN)]  
VALUES (value1, value2, value3,...valueN);

INSERT INTO TABLE_NAME VALUES (value1,value2,value3,...valueN);
```

**Example:**
```sql
INSERT INTO COMPANY VALUES (7, 'James', 24, 'Houston', 10000.00 );
```
### Update

- Update query is used to modify the existing records in a table. It is used with WHERE clause to select the specific row otherwise all the rows would be updated.

**Syntax:**
```sql
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE [condition];
```

**Example:**
```sql
UPDATE Student
SET Department = "DSBS"
WHERE RegisterNo = 1;
```

### Delete
- SQLite **DELETE** Query is used to delete the existing records from a table. You can use WHERE clause with DELETE query to delete the selected rows, otherwise all the records would be deleted.

**Syntax:**
```sql
DELETE FROM table_name
WHERE [condition];
```

**Example:**
```sql
DELETE FROM COMPANY WHERE ID = 7;
```


# Debugging
