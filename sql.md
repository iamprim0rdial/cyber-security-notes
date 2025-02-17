# SQL Commands

```sql
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

---

## SQL CRUD cheat sheet 

1. **Create Table**  
   - **Definition**: Creates a new table in the database.
   - **Example**:  
     ```sql
     CREATE TABLE Users (ID INT, Name VARCHAR(100), Age INT);
     ```

2. **Delete Table**  
   - **Definition**: Removes a table and all its data from the database.
   - **Example**:  
     ```sql
     DROP TABLE Users;
     ```

3. **Update Table**  
   - **Definition**: Modifies existing records in a table.
   - **Example**:  
     ```sql
     UPDATE Users SET Age = 30 WHERE ID = 1;
     ```

4. **Delete Records**  
   - **Definition**: Deletes specific records from a table.
   - **Example**:  
     ```sql
     DELETE FROM Users WHERE Age > 50;
     ```

5. **Add/Remove Column**  
   - **Definition**: Adds or removes columns in an existing table.
   - **Example**:  
     - Add:  
       ```sql
       ALTER TABLE Users ADD Email VARCHAR(100);
       ```
     - Remove:  
       ```sql
       ALTER TABLE Users DROP COLUMN Email;
       ```
---

## Order of execution of sql command

Understanding the order of execution in an SQL query is key to writing efficient and correct queries. Here’s the general order of execution for SQL commands, starting with the most basic:

1. **FROM**: First, the database determines which table(s) to pull the data from.
2. **JOIN**: If you're joining multiple tables, SQL will perform the join next.
3. **WHERE**: Filters the rows based on the condition specified.
4. **GROUP BY**: Groups rows that have the same values into summary rows.
5. **HAVING**: Applies a condition to the groups formed by `GROUP BY` (filters the grouped data).
6. **SELECT**: After filtering and grouping, SQL selects which columns to display.
7. **DISTINCT**: If used, it removes duplicate rows from the result.
8. **ORDER BY**: Orders the results based on specified columns.
9. **LIMIT/OFFSET**: Limits the number of rows returned (if specified).

### Example Query Breakdown:
```sql
SELECT COUNT(*)
FROM Employees
WHERE department = 'Sales'
GROUP BY manager
HAVING COUNT(*) > 5
ORDER BY COUNT(*) DESC
LIMIT 10;
```

**Order of Execution:**
1. **FROM**: From the `Employees` table.
2. **WHERE**: Filters rows where `department = 'Sales'`.
3. **GROUP BY**: Groups by the `manager`.
4. **HAVING**: Filters groups where the count of employees is greater than 5.
5. **SELECT**: Selects the count of employees in each group.
6. **ORDER BY**: Orders the results by the count in descending order.
7. **LIMIT**: Limits the result to the top 10 rows.

**Notes:** This is the logical order SQL uses to process the query, even if you write it in a different order!


---

## practicing SQL commands online 

1. [SQLZoo](https://sqlzoo.net/) - Interactive tutorials and quizzes to practice SQL commands.
2. [W3Schools SQL Tutorial](https://www.w3schools.com/sql/) - Beginner-friendly tutorial with an interactive SQL editor.
3. [LeetCode SQL](https://leetcode.com/problemset/database/) - Solve real-world SQL challenges with an online editor.
4. [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial/) - Learn SQL with real-world queries in an interactive SQL editor.
5. [HackerRank SQL Practice](https://www.hackerrank.com/domains/tutorials/10-days-of-sql) - Practice a variety of SQL problems from basics to advanced.
6. [SQL Fiddle](http://sqlfiddle.com/) - Test and share your SQL queries directly online.
7. [DB-Fiddle](https://www.db-fiddle.com/) - Write and execute SQL queries online, supporting multiple database systems.
8. [oracle live SQL](https://www.oracle.com/database/technologies/oracle-live-sql/) - need signin 



