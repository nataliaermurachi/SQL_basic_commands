In a relational database contains just a bunch of *tables*;

> *Tables* are a collection of data structured in columns(headers) and rows(actual data).

Data types(basics):

* `INT` (numeric type), max_value - 4294967295
* `VARCHAR` (string type), variable length, 1 - 255 chars

* Creating tables:

> `CREATE TABLE tablename(plural) (column_name data_type, column_name data_type );`

```
mysql> CREATE TABLE cats (
    -> name VARCHAR(100),
    -> age INT
    -> );
Query OK, 0 rows affected (0.01 sec)
```
* List the tables from your current database:

> `SHOW TABLES;`

```
mysql> SHOW TABLES;
+-------------------+
| Tables_in_cat_app |
+-------------------+
| cats              |
+-------------------+
1 row in set (0.00 sec)
```
* List the columns of the table:

> `SHOW COLUMNS FROM <tablename>;` or

> `DESC <tablename>;` (the same result in this context)

```
mysql> SHOW COLUMNS FROM cats;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(100) | YES  |     | NULL    |       |
| age   | int          | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+s
2 rows in set (0.00 sec)
```
* Delete tables:

> `DROP TABLE <tablename>;` 

```
mysql> DROP TABLE cats;
Query OK, 0 rows affected (0.01 sec)

```