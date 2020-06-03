# Basics

## Select

| Number of Columns | SQL Syntax |
| :--- | :--- |
| 1 | SELECT "column\_name" FROM "table\_name"; |
| More Than 1 | SELECT "column\_name1"\[, "column\_name2"\] FROM "table\_name"; |
| All | SELECT \* FROM "table\_name"; |

**DISTINCT**

SELECT DISTINCT "column\_name" FROM "table\_name";

**Where**

```sql
SELECT "column_name"
FROM "table_name"
WHERE "simple condition"
{ [AND|OR] "simple condition"}+;
```

**IN**

```sql
SELECT "column_name"
FROM "table_name"
WHERE "column_name" IN ('value1', 'value2', ...);

SELECT "column_name"
FROM "table_name"
WHERE "column_name" IN ( [SELECT STATEMENT] );
```

**LIKE**

* **%** \(percent sign\) represents zero, one, or more characters.
* **\_** \(underscore\) represents exactly one character.

Wildcards are used with the [**LIKE**](https://www.1keydata.com/sql/sqllike.html) operator in SQL.

**Order By**

```sql
SELECT "column_name"
FROM "table_name"
[WHERE "condition"]
ORDER BY "column_name" [ASC, DESC];
```

**Group By**

```sql
SELECT ["column_name1"], "function type" ("column_name2")
FROM "table_name"
[GROUP BY "column_name1"]
HAVING (arithmetic function condition);
```

Example:

```sql
SELECT Store_Name, Product_ID, SUM(Sales), AVG(Sales)
FROM Store_Information
GROUP BY Store_Name, Product_ID;
```

### **Join** 

 Place an "\(+\)" in the [**WHERE**](https://www.1keydata.com/sql/sqlwhere.html) clause on the other side of the table for which we want to include all the rows

```sql
SELECT A1.Store_Name, SUM(A2.Sales) SALES
FROM Geography A1, Store_Information A2
WHERE A1.Store_Name = A2.Store_Name (+)
GROUP BY A1.Store_Name;
```

###  **INSERT INTO SELECT.**

```sql
INSERT INTO "table1" ("column1", "column2", ...)
SELECT "column3", "column4", ...
FROM "table2";
```

##  **UPDATE**

```sql
UPDATE "table_name"
SET column_1 = [value1], column_2 = [value2], ...
WHERE "condition";
```

 **DELETE FROM**

```sql
DELETE FROM "table_name"
WHERE "condition";
```

## UNION vs UNION ALL

**UNION** and **UNION ALL** both combine the results of two SQL queries. The difference is that, while **UNION** only returns distinct values, **UNION ALL** selects all values. 

 **INTERSECT**

```sql
[SQL Statement 1]
INTERSECT
[SQL Statement 2];
```

 **MINUS**

```sql
[SQL Statement 1]
MINUS
[SQL Statement 2];
```

 **LIMIT**

```sql
[SQL Statement 1]
LIMIT [N];
```

 **EXISTS**

```sql
SELECT "column_name1"
FROM "table_name1"
WHERE EXISTS 
(SELECT * 
FROM "table_name2"
WHERE "condition");
```

