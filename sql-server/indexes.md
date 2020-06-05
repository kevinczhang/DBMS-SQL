---
description: >-
  SQL Server Indexes are special data structures associated with tables or views
  that help speed up query
---

# Indexes

## Types of indexes

### Clustered index

A clustered index stores data rows in a sorted structure based on its key values. Each table has only one clustered index because data rows can be only sorted in one order. The table that has a clustered index is called a clustered table.

 A clustered index organizes data using a special structured so-called [B-tree](https://en.wikipedia.org/wiki/B-tree) \(or balanced tree\) which enables searches, inserts, updates, and deletes in logarithmic amortized time.

 When you create a table with a [primary key](https://www.sqlservertutorial.net/sql-server-basics/sql-server-primary-key/), SQL Server automatically creates a corresponding clustered index based on columns included in the primary key.

### Non-clustered indexes

If you add a primary key constraint to an existing table that already has a clustered index, SQL Server will enforce the primary key using a non-clustered index.

 A nonclustered index is a data structure that improves the speed of data retrieval from tables. Unlike a [clustered index](https://www.sqlservertutorial.net/sql-server-indexes/sql-server-clustered-indexes/), a nonclustered index sorts and stores data separately from the data rows in the table. It is a copy of selected columns of data from a table with the links to the associated table. Similar to a clustered index, a nonclustered index uses the B-tree structure to organize its data.

A table may have one or more nonclustered indexes and each non-clustered index may include one or more columns of the table.

Besides storing the index key values, the leaf nodes also store row pointers to the data rows that contain the key values. These row pointers are also known as row locators.



