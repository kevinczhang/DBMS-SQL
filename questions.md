# Questions

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

## Department Highest Salary

```sql
Select d.Name as Department, e3.Name as Employee, e3.Salary from Department d
INNER JOIN (
    Select e1.DepartmentId, e1.Name, e1.Salary from Employee e1
    INNER JOIN (
        Select DepartmentId, MAX(Salary) as Salary from Employee
        Group By DepartmentId
    ) e2 ON e1.Salary = e2.Salary AND e1.DepartmentId = e2.DepartmentId
) e3 ON d.Id = e3.DepartmentId;
```

