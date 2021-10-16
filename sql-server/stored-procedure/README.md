---
description: >-
  Stored procedures are used to group one or more Transact-SQL statements into
  logical units.
---

# Stored Procedure

The stored procedure are stored as named objects in the SQL Server Database Server. When you call a stored procedure for the first time, SQL Server creates an execution plan and stores it in the cache. In the subsequent executions of the stored procedure, SQL Server reuses the plan so that the stored procedure can execute very fast with reliable performance.

## Creating a stored procedure

```sql
CREATE PROCEDURE uspFindProducts(@min_list_price AS DECIMAL)
AS
BEGIN
    SELECT
        product_name,
        list_price
    FROM 
        production.products
    WHERE
        list_price >= @min_list_price
    ORDER BY
        list_price;
END;
```

## Executing a stored procedure

```sql
EXECUTE uspFindProducts 
    @min_list_price = 900, 
    @max_list_price = 1000;
```

## Modifying a stored procedure

```sql
ALTER PROCEDURE uspFindProducts(
    @min_list_price AS DECIMAL
    ,@max_list_price AS DECIMAL
)
AS
BEGIN
    SELECT
        product_name,
        list_price
    FROM 
        production.products
    WHERE
        list_price >= @min_list_price AND
        list_price <= @max_list_price
    ORDER BY
        list_price;
END;
```

## Deleting a stored procedure

```sql
DROP PROCEDURE sp_name;
```
