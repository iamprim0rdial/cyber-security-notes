# SQL Commands

```bash
-----------------------------------------------------

    SELECT:     Select data from database                             example: SELECT * FROM employees;
    AS:         Rename column or table with alias                     example: SELECT first_name AS "First Name", last_name AS "Last Name" FROM Employees;
    FROM:       Specify table we’re pulling from                      example: SELECT name, age FROM Students;
    WHERE:      Filter query to match a condition                     example: SELECT * FROM Orders WHERE order_status = 'Shipped';
    JOIN:       Combine rows from 2 or more tables                    example: SELECT Employees.name, Departments.name 
                                                                               FROM Employees 
                                                                                JOIN Departments ON Employees.department_id = Departments.id;

    AND:        Combine conditions in a query. All must be met        example:
    OR:         Combine conditions in a query. One must be met        example:
    LIKE:       Search for patterns in a column                       example:
    IN:         Specify multiple values when using WHERE              example:
    IS NULL:    Return only rows with a NULL value                    example:
    LIMIT:      Limit the number of rows returned                     example:

--------------------------------------------------------

    CASE:        Return value on a specified condition
    CREATE:      Create TABLE, DATABASE, INDEX or VIEW
    DROP:        Delete TABLE, DATABASE, or INDEX
    UPDATE:      Update table data
    DELETE:      Delete rows from a table
    ALTER TABLE: Add/Remove columns from table

--------------------------------------------------------

    GROUP BY:   Group rows that have same values into summary rows
    ORDER BY:   Set order of result. Use DESC to reverse order
    HAVING:     Same as WHERE but used for aggregate functions
    SUM:        Return sum of column
    AVG:        Return average of column
    MIN:        Return min value of column
    MAX:        Return max value of column
    COUNT:      Count number of rows

---------------------------------------------------------
```


# Example

- **Select first 10 rows for 2 columns**:
    
    `SELECT column1, column2 FROM table_name LIMIT 10;`
    
- **Select all rows with multiple filters applied**:
    
    `SELECT * FROM table_name WHERE condition1 AND condition2;`
    
- **Select all rows from col1 and col2 ordering by col1**:
    
    `SELECT col1, col2 FROM table_name ORDER BY col1;`
    
- **Return count of rows in table**:
    
    `SELECT COUNT(*) FROM table_name;`
    
- **Return sum of col1**:
    
    `SELECT SUM(col1) FROM table_name;`
    
- **Return max value from col1**:
    
    `SELECT MAX(col1) FROM table_name;`
    
- **Compute summary statistics by grouping col2**:
    
    `SELECT col2, COUNT(*), AVG(col1), SUM(col1) FROM table_name GROUP BY col2;`
    
- **Combine data from two tables using a left join**:
    
    `SELECT * FROM table1 LEFT JOIN table2 ON table1.id = table2.id;`
    
- **Aggregate and filter results**:
    
    `SELECT col1, COUNT(*) FROM table_name GROUP BY col1 HAVING COUNT(*) > 5;`
    
- **Implementation of CASE statement**:
    
    `SELECT col1, CASE WHEN condition THEN 'value1' ELSE 'value2' END FROM table_name;`
