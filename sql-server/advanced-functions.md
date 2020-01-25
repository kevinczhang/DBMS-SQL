# Advanced Functions

## CAST\(\)

The CAST\(\) function converts a value \(of any type\) into a specified datatype.

CAST\(expression AS datatype\(length\)\)

#### Parameter Values

| Value | Description |
| :--- | :--- |
| expression | Required. The value to convert |
| datatype | Required. The datatype to convert _expression_ to. Can be one of the following: bigint, int, smallint, tinyint, bit, decimal, numeric, money, smallmoney, float, real, datetime, smalldatetime, char, varchar, text, nchar, nvarchar, ntext, binary, varbinary, or image |
| _\(length\)_ | Optional. The length of the resulting data type \(for char, varchar, nchar, nvarchar, binary and varbinary\) |

```sql
SELECT CAST(25.65 AS varchar);
```

## COALESCE\(\)

The COALESCE\(\) function returns the first non-null value in a list.

```sql
SELECT COALESCE(NULL, 1, 2, 'W3Schools.com');
```

## IIF\(\)

The IIF\(\) function returns a value if a condition is TRUE, or another value if a condition is FALSE.

 IIF\(_condition_, _value\_if\_true_, _value\_if\_false_\)

```sql
SELECT IIF(500<1000, 5, 10);
```

## ISNULL\(\)

The ISNULL\(\) function returns a specified value if the expression is NULL.

If the expression is NOT NULL, this function returns the expression.

```sql
SELECT ISNULL(NULL, 'W3Schools.com');
```

## ISNUMERIC\(\)

The ISNUMERIC\(\) function tests whether an expression is numeric.

This function returns 1 if the expression is numeric, otherwise it returns 0.

```sql
SELECT ISNUMERIC('4567');
```

## NULLIF\(\) Function

The NULLIF\(\) function returns NULL if two expressions are equal, otherwise it returns the first expression.

```sql
SELECT NULLIF('Hello', 'Hello');
```



