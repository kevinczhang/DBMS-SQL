# Functions

SQL Server scalar function takes one or more parameters and returns a single value.  The scalar functions help you simplify your code. For example, you may have a complex calculation that appears in many queries. 

```sql
CREATE FUNCTION [schema_name.]function_name (parameter_list)
RETURNS data_type AS
BEGIN
    statements
    RETURN value
END
```



