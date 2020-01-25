# Date Functions

## CURRENT\_DATE

```sql
SELECT CURRENT_DATE; --2018-07-21

```

 SQL Server does not support `CURRENT_DATE` function. However, it has another function named `GETDATE()` that returns the current date and time. To get the current date, you use the `CAST`\(\) function with the `GETDATE()` function as shown in the following statement:

```sql
SELECT CAST(GETDATE() AS DATE) 'Current Date';
```

## CURRENT\_TIMESTAMP

```sql
SELECT CURRENT_TIMESTAMP; -- 2020-01-25 18:37:51.303
```

## DATEADD\(\)

The DATEADD\(\) function adds a time/date interval to a date and then returns the date.

```sql
SELECT DATEADD(year, 1, '2017/08/25') AS DateAdd;
```

DATEADD\(_interval_, _number_, _date_\)

### Parameter Values

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>interval</em>
      </td>
      <td style="text-align:left">
        <p>Required. The time/date interval to add. Can be one of the following values:</p>
        <ul>
          <li>year, yyyy, yy = Year</li>
          <li>quarter, qq, q = Quarter</li>
          <li>month, mm, m = month</li>
          <li>dayofyear = Day of the year</li>
          <li>day, dy, y = Day</li>
          <li>week, ww, wk = Week</li>
          <li>weekday, dw, w = Weekday</li>
          <li>hour, hh = hour</li>
          <li>minute, mi, n = Minute</li>
          <li>second, ss, s = Second</li>
          <li>millisecond, ms = Millisecond</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>number</em>
      </td>
      <td style="text-align:left">Required. The number of <em>interval</em> to add to date. Can be positive
        (to get dates in the future) or negative (to get dates in the past)</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>date</em>
      </td>
      <td style="text-align:left">Required. The date that will be modified</td>
    </tr>
  </tbody>
</table>## DATEDIFF\(\)

The DATEDIFF\(\) function returns the difference between two dates.

### Syntax

DATEDIFF\(_interval_, _date1_, _date2_\)

### Parameter Values

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>interval</em>
      </td>
      <td style="text-align:left">
        <p>Required. The part to return. Can be one of the following values:</p>
        <ul>
          <li>year, yyyy, yy = Year</li>
          <li>quarter, qq, q = Quarter</li>
          <li>month, mm, m = month</li>
          <li>dayofyear = Day of the year</li>
          <li>day, dy, y = Day</li>
          <li>week, ww, wk = Week</li>
          <li>weekday, dw, w = Weekday</li>
          <li>hour, hh = hour</li>
          <li>minute, mi, n = Minute</li>
          <li>second, ss, s = Second</li>
          <li>millisecond, ms = Millisecond</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>date1, date2</em>
      </td>
      <td style="text-align:left">Required. The two dates to calculate the difference between</td>
    </tr>
  </tbody>
</table>```sql
SELECT DATEDIFF(month, '2017/08/25', '2011/08/25') AS DateDiff;
```

## DATEFROMPARTS\(\)

The DATEFROMPARTS\(\) function returns a date from the specified parts \(year, month, and day values\).

### Syntax

DATEFROMPARTS\(_year_, _month_, _day_\)

### Parameter Values

| Parameter | Description |
| :--- | :--- |
| _year_ | Required. Specifies a year \(4 digits\) |
| _month_ | Required. Specifies a month \(from 1 to 12\) |
| _day_ | Required. Specifies a day \(from 1 to 31\) |

## DATENAME\(\)

The DATENAME\(\) function returns a specified part of a date.

This function returns the result as a string value.

### Syntax

DATENAME\(_interval_, _date_\)

### Parameter Values

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>interval</em>
      </td>
      <td style="text-align:left">
        <p>Required. The part to return. Can be one of the following values:</p>
        <ul>
          <li>year, yyyy, yy = Year</li>
          <li>quarter, qq, q = Quarter</li>
          <li>month, mm, m = month</li>
          <li>dayofyear = Day of the year</li>
          <li>day, dy, y = Day</li>
          <li>week, ww, wk = Week</li>
          <li>weekday, dw, w = Weekday</li>
          <li>hour, hh = hour</li>
          <li>minute, mi, n = Minute</li>
          <li>second, ss, s = Second</li>
          <li>millisecond, ms = Millisecond</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>date</em>
      </td>
      <td style="text-align:left">Required. The date to use</td>
    </tr>
  </tbody>
</table>```sql
SELECT DATENAME(yy, '2017/08/25') AS DatePartString;
```

## DATEPART\(\)

The DATEPART\(\) function returns a specified part of a date.

This function returns the result as an integer value.

### Syntax

DATEPART\(_interval_, _date_\)

### Parameter Values

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>interval</em>
      </td>
      <td style="text-align:left">
        <p>Required. The part to return. Can be one of the following values:</p>
        <ul>
          <li>year, yyyy, yy = Year</li>
          <li>quarter, qq, q = Quarter</li>
          <li>month, mm, m = month</li>
          <li>dayofyear, dy, y = Day of the year</li>
          <li>day, dd, d = Day of the month</li>
          <li>week, ww, wk = Week</li>
          <li>weekday, dw, w = Weekday</li>
          <li>hour, hh = hour</li>
          <li>minute, mi, n = Minute</li>
          <li>second, ss, s = Second</li>
          <li>millisecond, ms = Millisecond</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>date</em>
      </td>
      <td style="text-align:left">Required. The date to use</td>
    </tr>
  </tbody>
</table>## DAY\(\)

The DAY\(\) function returns the day of the month \(from 1 to 31\) for a specified date.

### Syntax

DAY\(_date_\)

### Parameter Values

| Parameter | Description |
| :--- | :--- |
| _date_ | Required. The date to return the day of the month from |

## GETDATE\(\)

The GETDATE\(\) function returns the current database system date and time, in a 'YYYY-MM-DD hh:mm:ss.mmm' format.

## ISDATE\(\)

The ISDATE\(\) function checks an expression and returns 1 if it is a valid date, otherwise 0.

## MONTH\(\)

The MONTH\(\) function returns the month part for a specified date \(a number from 1 to 12\).

## SYSDATETIME\(\)

The SYSDATETIME\(\) function returns the date and time of the computer where the SQL Server is running.

## YEAR\(\)

The YEAR\(\) function returns the year part for a specified date.

