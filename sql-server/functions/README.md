# Functions

The SQL Server user-defined functions help you simplify your development by encapsulating complex business logic and make them available for reuse in every query.

## Scalar functions

SQL Server scalar function takes one or more parameters and returns a single value. 

### Creating a scalar function

```sql
CREATE FUNCTION [schema_name.]function_name (parameter_list)
RETURNS data_type AS
BEGIN
    statements
    RETURN value
END
```

```sql
CREATE FUNCTION sales.udfNetSale(
    @quantity INT,
    @list_price DEC(10,2),
    @discount DEC(4,2)
)
RETURNS DEC(10,2)
AS 
BEGIN
    RETURN @quantity * @list_price * (1 - @discount);
END;
```

### Calling a scalar function

```sql
SELECT 
    sales.udfNetSale(10,100,0.1) net_sale;
```

### Modifying a scalar function

```sql
CREATE OR ALTER FUNCTION [schema_name.]function_name (parameter_list)
        RETURN data_type AS
        BEGIN
            statements
            RETURN value
        END
```

### Removing a scalar function

```sql
DROP FUNCTION [schema_name.]function_name;
```

## Table variables

Table variables are kinds of variables that allow you to hold rows of data, which are similar to [temporary tables](https://www.sqlservertutorial.net/sql-server-basics/sql-server-temporary-tables/).

### Declare table variables

```sql
DECLARE @table_variable_name TABLE (
    column_list
);
```

```sql
DECLARE @product_table TABLE (
    product_name VARCHAR(MAX) NOT NULL,
    brand_id INT NOT NULL,
    list_price DEC(11,2) NOT NULL
);
```

## Table-valued function

A table-valued function is a [user-defined function](https://www.sqlservertutorial.net/sql-server-user-defined-functions/) that returns data of a table type. 

### Creating a table-valued function

```sql
CREATE FUNCTION udfProductInYear (
    @model_year INT
)
RETURNS TABLE
AS
RETURN
    SELECT 
        product_name,
        model_year,
        list_price
    FROM
        production.products
    WHERE
        model_year = @model_year;
```

### Executing a table-valued function

```sql
SELECT 
    * 
FROM 
    udfProductInYear(2017);
```

## `DROP FUNCTION` statement

```sql
DROP FUNCTION [ IF EXISTS ] [ schema_name. ] function_name;
```

