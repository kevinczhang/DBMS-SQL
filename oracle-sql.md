# Oracle SQL

DENSE_RANK

```sql
CREATE FUNCTION getNthHighestSalary(N IN NUMBER) RETURN NUMBER IS
result NUMBER;
BEGIN
    SELECT salary into result
        from (select distinct salary, 
        DENSE_RANK() OVER ( ORDER BY salary DESC NULLS LAST) DENSE_RANK
        FROM employee)
        where DENSE_RANK = n;
    
    RETURN result;
END;
```

NULL data will sort to the bottom
