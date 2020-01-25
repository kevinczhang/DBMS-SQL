# SQL Server

## IS NULL \| IS NOT NULL

```sql
SELECT
    customer_id,
    first_name,
    last_name,
    phone
FROM
    sales.customers
WHERE
    phone IS NULL
ORDER BY
    first_name,
    last_name;
```

## Nth Highest Salary

```sql
CREATE FUNCTION getNthHighestSalary(@N INT) RETURNS INT AS
BEGIN
    RETURN (
        select isnull(
        (select Salary
            from (
            select distinct Salary, 
                dense_rank()over(order by Salary desc) as DENSERANK
            from Employee
        ) result
        where result.DENSERANK = @N), null) as SecondHighestSalary
        
    );
END
```

