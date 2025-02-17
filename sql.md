# SQL Commands

```bash
--------------------------------------------------------------------------------------------------------------------------

    SELECT:     Select data from database                             example: SELECT * FROM employees;
    AS:         Rename column or table with alias                     example: SELECT first_name AS "First Name", last_name AS "Last Name" FROM Employees;
    FROM:       Specify table we’re pulling from                      example: SELECT name, age FROM Students;
    WHERE:      Filter query to match a condition                     example: SELECT * FROM Orders WHERE order_status = 'Shipped';
    JOIN:       Combine rows from 2 or more tables                    example: SELECT Employees.name, Departments.name FROM Employees JOIN Departments ON Employees.department_id = Departments.id;

-----------------------------------------------------------------------------------------------------------------------------
                                       
    AND:        Combine conditions in a query. All must be met        example: SELECT * FROM Employees WHERE age > 30 AND department = 'HR';
    OR:         Combine conditions in a query. One must be met        example: SELECT * FROM Employees WHERE age > 30 OR department = 'HR';
    LIKE:       Search for patterns in a column                       example: SELECT * FROM Employees WHERE name LIKE 'John%';
    IN:         Specify multiple values when using WHERE              example: SELECT * FROM Products WHERE category IN ('Electronics', 'Furniture');
    IS NULL:    Return only rows with a NULL value                    example: SELECT * FROM Employees WHERE manager_id IS NULL;
    LIMIT:      Limit the number of rows returned                     example: SELECT * FROM Employees LIMIT 10;

-----------------------------------------------------------------------------------------------------------------------------

    CASE:        Return value on a specified condition                example: SELECT name, CASE WHEN age >= 18 THEN 'Adult' ELSE 'Minor' END AS status FROM Employees;
    CREATE:      Create TABLE, DATABASE, INDEX or VIEW                example: CREATE TABLE Customers ( id INT PRIMARY KEY,name VARCHAR(100),email VARCHAR(100));
    DROP:        Delete TABLE, DATABASE, or INDEX                     example: DROP TABLE Employees;
    UPDATE:      Update table data                                    example: UPDATE Employees SET salary = 60000 WHERE id = 1;
    DELETE:      Delete rows from a table                             example: DELETE FROM Employees WHERE id = 1;
    ALTER TABLE: Add/Remove columns from table                        example: ALTER TABLE Employees ADD column address VARCHAR(255);

-------------------------------------------------------------------------------------------------------------------------------------------

    GROUP BY:   Group rows that have same values into summary rows    example: SELECT department, COUNT(*) FROM Employees GROUP BY department;
    ORDER BY:   Set order of result. Use DESC to reverse order        example: SELECT * FROM Employees ORDER BY salary DESC;
    HAVING:     Same as WHERE but used for aggregate functions        example: SELECT department, COUNT(*) FROM Employees GROUP BY department HAVING COUNT(*) > 5;
    SUM:        Return sum of column                                  example: SELECT SUM(salary) FROM Employees;
    AVG:        Return average of column                              example: SELECT AVG(salary) FROM Employees;
    MIN:        Return min value of column                            example: SELECT MIN(salary) FROM Employees;
    MAX:        Return max value of column                            example: SELECT MAX(salary) FROM Employees;
    COUNT:      Count number of rows                                  example: SELECT COUNT(*) FROM Employees;

----------------------------------------------------------------------------------------------------------------------
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
