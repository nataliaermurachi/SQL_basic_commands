`AS` - a keyword that allows to *rename* a column or table using an alias.

>`SELECT columnName AS 'newName';`

`DISTINCT` - returns unique values in the output. It filters out all dublicae values in the specified column(s).

>`SELECT DISTINCT columnName FROM tableName;`

`WHERE` - clause filters the result set to only include rows where the condition is true. WHERE  clause is used with comparison operators:  = , != , >, <, >=, <= ;


> `SELECT column  FROM tableName WHERE condition; `

`LIKE` - special operator used with the WHERE clause to search for a specific pattern in a column.

> `SELECT column FROM tablename WHERE columnName LIKE patern;`

`BETWEEN` and `AND` and `OR` are used to filter the result set within a certain range, sometimes with multiple conditions.

> `SELECT column FROM tablename WHERE columnName BETWEEN value1 AND value2 OR value3;`

`ORDER BY `- a clause that indicates you want to sort the result set by a particular column, either alphabetically or numerically; - Always goes after WHERE (if present).

`DESC` or `ASC` are used in `ORDER BY`  in descending or ascending order.

> `SELECT * FROM tableName WHERE condition ORDER BY column DESC(ASC);`

`LIMIT` - a clause that lets you specify the maximum number of rows the result set will have;

Goes always at the very end of the query;

> `SELECT column  FROM tableName WHERE condition LIMIT number; `

`CASE` statement allows to create different outputs. usually in the `SELECT` statement for handling *if-then* logic. `CASE ` statement must end with `END`.

`WHEN` - test a condition 

`THEN` - gives a string if the condition is true

`ELSE` - gives a string value if all the above conditions are false.


```
SELECT columnName,
 CASE
  WHEN condition1 THEN 'string1'
  WHEN condition2 THEN 'string2'
  ELSE 'Another string'
 END
FROM table;
```