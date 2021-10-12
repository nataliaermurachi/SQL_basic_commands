

After connecting to MySql server, check for existing databases:

* List current databases: 

> `SHOW databases;` 

* Create a database:

> `CREATE DATABASE <name> ;` 

* Delete a database:

> `DROP DATABASE <name>;`

* Tell SQL which database we want to work with or switch the databases :

> `USE <database name>;`

* Check the currently used database:

> `SELECT database();`

[More details and exemple](https://github.com/nataliaermurachi/mysql_basic_commands/blob/main/database.md)

---

> *Tables* are a collection of data structured in columns(headers) and rows(actual data).

* Creating tables:

> `CREATE TABLE tablename(plural) (column_name data_type, column_name data_type );`

* List the tables from your current database:

> `SHOW TABLES;`

* List the columns of the table:

> `SHOW COLUMNS FROM <tablename>;` or

> `DESC <tablename>;` (the same result in this context)

* Delete tables:

> `DROP TABLE <tablename>;` 

[More details and exemple](https://github.com/nataliaermurachi/mysql_basic_commands/blob/main/table.md)

---

* Inserting data into the table:
The order matter, the column must match with the position of the value.

> `INSERT INTO <table_name>(culumn_name) VALUES (data);`

* Inserting multiple values into the table:

> INSERT INTO table_name 
            (column_name, column_name) 
VALUES      (value, value), 
            (value, value), 
            (value, value);

* When you get an warning:
Use this command to see the warning's message:

> `SHOW WARNINGS;`

[More details and exemple](https://github.com/nataliaermurachi/mysql_basic_commands/blob/main/insertData.md

---

> Constraints: 

[More details and exemple](https://github.com/nataliaermurachi/mysql_basic_commands/blob/main/Constraints.md)

---

> Queries:
[More details and exemple](https://github.com/nataliaermurachi/mysql_basic_commands/blob/main/queries.md)

---

### Agregates

> `Count()` - a function that takes the name of a column as an argument and counts the number of non-empty values in that column.

`SELECT COUNT(column_name) FROM table;`

> `Sum()` - is a function that takes the name of a column as an argument snd returns the sum of all the values in that column.

`SELECT SUM(column_name) FROM table;`

> `Max()` and `Min()` take the name of a column as an argument and returns the largest or the smalest value in that column.

`SELECT MIN(column_name) FROM table;`

`SELECT MAX(column_name) FROM table;`

>`Avg()` - is a function that takes a column name as an argument and returns the average value for that column.

`SELECT AVG(column_name) FROM table;`

> `Round()` - is a function that takes a column name and an integer as parameters. It rounds the values in the column to the number of decimal places specified by the integer.

`SELECT ROUND(column_name, integer) FROM table;`

> `GROUP BY` - is a clause that is used wit agregate functions and SElect statement to arrange identical data into *groups*. (comes after `WHERE` but before `ORDER BY` or `LIMIT`).

`SELECT column, function FROM table GROUP BY column_name;`

Sometimes `GROUP BY` is used to group the columns by a calculation done on a column:

`SELECT column_name, function(column) FROM table GROUP BY function;`

> `HAVING` - allows to filter which groups to include, it *filters groups*. Comes after `GROUP BY` and before `ORDER BY` and `LIMIT`

