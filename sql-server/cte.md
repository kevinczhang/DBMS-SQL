---
description: CTE stands for common table expression.
---

# CTE

A CTE allows you to define a temporary named result set that available temporarily in the execution scope of a statement such as [`SELECT`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-select/), [`INSERT`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-insert/), [`UPDATE`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-update/), [`DELETE`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-delete/), or [`MERGE`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-merge/).

```sql
WITH cte_category_counts (
    category_id, 
    category_name, 
    product_count
)
AS (
    SELECT 
        c.category_id, 
        c.category_name, 
        COUNT(p.product_id)
    FROM 
        production.products p
        INNER JOIN production.categories c 
            ON c.category_id = p.category_id
    GROUP BY 
        c.category_id, 
        c.category_name
),
cte_category_sales(category_id, sales) AS (
    SELECT    
        p.category_id, 
        SUM(i.quantity * i.list_price * (1 - i.discount))
    FROM    
        sales.order_items i
        INNER JOIN production.products p 
            ON p.product_id = i.product_id
        INNER JOIN sales.orders o 
            ON o.order_id = i.order_id
    WHERE order_status = 4 -- completed
    GROUP BY 
        p.category_id
) 

SELECT 
    c.category_id, 
    c.category_name, 
    c.product_count, 
    s.sales
FROM
    cte_category_counts c
    INNER JOIN cte_category_sales s 
        ON s.category_id = c.category_id
ORDER BY 
    c.category_name;
```

## recursive CTE

This example uses a recursive CTE to get all subordinates of the top manager who does not have a manager \(or the value in the `manager_id` column is NULL\):

```sql
WITH cte_org AS (
    SELECT       
        staff_id, 
        first_name,
        manager_id
        
    FROM       
        sales.staffs
    WHERE manager_id IS NULL
    UNION ALL
    SELECT 
        e.staff_id, 
        e.first_name,
        e.manager_id
    FROM 
        sales.staffs e
        INNER JOIN cte_org o 
            ON o.staff_id = e.manager_id
)
SELECT * FROM cte_org;
```

