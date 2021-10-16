# Joints

## Inner Join

 [Inner join](https://www.sqlservertutorial.net/sql-server-basics/sql-server-inner-join/) produces a data set that includes rows from the left table which have matching rows from the right table.

```sql
SELECT  
    c.id candidate_id,
    c.fullname candidate_name,
    e.id employee_id,
    e.fullname employee_name
FROM 
    hr.candidates c
    INNER JOIN hr.employees e 
        ON e.fullname = c.fullname;
```

The following Venn diagram illustrates the result of the inner join of two result sets:

![SQL Server Joins - Inner Join](https://cdn.sqlservertutorial.net/wp-content/uploads/SQL-Server-Joins-Inner-Join-1.png)

## Left Join

 [Left join](https://www.sqlservertutorial.net/sql-server-basics/sql-server-left-join/) selects data starting from the left table and matching rows in the right table. The left join returns all rows from the left table and the matching rows from the right table. If a row in the left table does not have a matching row in the right table, the columns of the right table will have nulls.

```sql
SELECT  
 c.id candidate_id,
 c.fullname candidate_name,
 e.id employee_id,
 e.fullname employee_name
FROM 
 hr.candidates c
 LEFT JOIN hr.employees e 
 ON e.fullname = c.fullname;
```

The following Venn diagram illustrates the result of the left join of two result sets:

![SQL Server Joins - Left Join](https://cdn.sqlservertutorial.net/wp-content/uploads/SQL-Server-Joins-Left-Join.png)

## Right Join

The right join returns a result set that contains all rows from the right table and the matching rows in the left table. If a row in the right table that does not have a matching row in the left table, all columns in the left table will contain nulls.

```sql
SELECT  
    c.id candidate_id,
    c.fullname candidate_name,
    e.id employee_id,
    e.fullname employee_name
FROM 
    hr.candidates c
    RIGHT JOIN hr.employees e 
        ON e.fullname = c.fullname;
```

![](<../.gitbook/assets/image (3).png>)

## full join

 The [full outer join](https://www.sqlservertutorial.net/sql-server-basics/sql-server-full-outer-join/) or [full join](https://www.sqlservertutorial.net/sql-server-basics/sql-server-full-outer-join/) returns a result set that contains all rows from both left and right tables, with the matching rows from both sides where available. In case there is no match, the missing side will have [NULL](https://www.sqlservertutorial.net/sql-server-basics/sql-server-null/) values.

```sql
SELECT  
    c.id candidate_id,
    c.fullname candidate_name,
    e.id employee_id,
    e.fullname employee_name
FROM 
    hr.candidates c
    FULL JOIN hr.employees e 
        ON e.fullname = c.fullname;
```

Here is the output:

![SQL Server Joins - full Join](https://cdn.sqlservertutorial.net/wp-content/uploads/SQL-Server-Joins-full-Join.png)
