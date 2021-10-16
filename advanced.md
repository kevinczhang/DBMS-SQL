# Advanced

## CASE

**CASE** is used to provide if-then-else type of logic to SQL. There are two formats: 

1. **Simple CASE** expression, where we compare an expression to static values. 
2. **Searched CASE** expression, where we compare an expression to one or more logical conditions.

#### Simple CASE Expression Syntax

```sql
SELECT CASE ("column_name") 
  WHEN "value1" THEN "result1" 
  WHEN "value2" THEN "result2" 
  ... 
  [ELSE "resultN"] 
  END
FROM "table_name";
```

Example:

```sql
SELECT Store_Name, CASE Store_Name
  WHEN 'Los Angeles' THEN Sales * 2
  WHEN 'San Diego' THEN Sales * 1.5
  ELSE Sales
  END
"New Sales",
Txn_Date
FROM Store_Information;
```

#### Searched CASE Expression Syntax

```sql
SELECT CASE
  WHEN "condition1" THEN "result1" 
  WHEN "condition2" THEN "result2" 
  ... 
  [ELSE "resultN"] 
  END
FROM "table_name";
```

Example:

```sql
SELECT Store_Name, Txn_Date, CASE
  WHEN Sales >= 1000 THEN 'Good Day'
  WHEN Sales >= 500 THEN 'OK Day'
  ELSE 'Bad Day'
  END
"Sales Status"
FROM Store_Information;
```

##  **DECODE**

 **DECODE** is a function in Oracle and is used to provide if-then-else type of logic to SQL. It is not available in MySQL or SQL Server.

```sql
SELECT DECODE ( "column_name", "search_value_1", "result_1", 
["search_value_n", "result_n"],
{"default_result"} );
```

**Example:**

```sql
SELECT DECODE (Store_Name, 
  'Los Angeles', 'LA', 
  'San Francisco', 'SF', 
  'San Diego', 'SD', 
  'Others') Area, Sales, Txn_Date 
FROM Store_Information;
```

