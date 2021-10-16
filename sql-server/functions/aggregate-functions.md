---
description: >-
  An aggregate function performs a calculation one or more values and returns a
  single value.
---

# Aggregate Functions

The aggregate function is often used with the [`GROUP BY`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-group-by/) clause and [`HAVING`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-having/) clause of the [`SELECT`](https://www.sqlservertutorial.net/sql-server-basics/sql-server-select/) statement.

| Aggregate function                                                                                        | Description                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AVG](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-avg/)                   | The `AVG()` aggregate function calculates the average of non-NULL values in a set.                                                                                           |
| [CHECKSUM_AGG](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-checksum_agg/) | The `CHECKSUM_AGG()` function calculates a checksum value based on a group of rows.                                                                                          |
| [COUNT](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-count/)               | The `COUNT()` aggregate function returns the number of rows in a group, including rows with NULL values.                                                                     |
| [COUNT_BIG](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-count/)           | The `COUNT_BIG()` aggregate function returns the number of rows (with BIGINT data type) in a group, including rows with NULL values.                                         |
| [MAX](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-max/)                   | The `MAX()` aggregate function returns the highest value (maximum) in a set of non-NULL values.                                                                              |
| [MIN](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-min/)                   | The `MIN()` aggregate function returns the lowest value (minimum) in a set of non-NULL values.                                                                               |
| STDEV                                                                                                     | <p>The <code>STDEV()</code> function returns the statistical standard deviation of all values provided in the<br>expression based on a sample of the data population.</p>    |
| STDEVP                                                                                                    | <p>The <code>STDEVP()</code> function also returns the standard deviation for all values in the provided<br>expression, but does so based on the entire data population.</p> |
| [SUM](https://www.sqlservertutorial.net/sql-server-aggregate-functions/sql-server-sum/)                   | The `SUM()` aggregate function returns the summation of all non-NULL values a set.                                                                                           |
| VAR                                                                                                       | The `VAR()` function returns the statistical variance of values in an expression based on a sample of the specified population.                                              |
| VARP                                                                                                      | <p>The <code>VARP()</code> function returns the statistical variance of values in an expression but does<br>so based on the entire data population.</p>                      |
