* Inserting data into the table:
The order matter, the column must match with the position of the value.

> `INSERT INTO <table_name>(culumn_name) VALUES (data);`

```
mysql> INSERT INTO cats(name, age) 
    -> VALUES("blue", 1)
    -> ;
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO cats(age, name) VALUES(11,'Draco');
Query OK, 1 row affected (0.00 sec)

mysql> SELECT * FROM cats;
+-------+------+
| name  | age  |
+-------+------+
| blue  |    1 |
| Draco |   11 |
+-------+------+
2 rows in set (0.00 sec)
```
___ 
<!-- Multiple insert -->
* Inserting multiple values into the table:
> INSERT INTO table_name 
            (column_name, column_name) 
VALUES      (value, value), 
            (value, value), 
            (value, value);

```
mysql> INSERT INTO cats(name,age) 
    VALUES ('Peanut', 2),
    ,('Jelly', 7);

Query OK, 3 rows affected (0.00 sec)

Records: 3  Duplicates: 0  Warnings: 0
```
* When you get an warning:
Use this command to see the warning's message:

> `SHOW WARNINGS;`

```
mysql> INSERT INTO cats(name, age) VALUES('This is some text blah blah blah blah blah text text text something about cats lalalalal meowwwwwwwwwww', 10);
Query OK, 1 row affected, 1 warning (0.00 sec)

mysql> SHOW WARNINGS;
+---------+------+-------------------------------------------+
| Level   | Code | Message                                   |
+---------+------+-------------------------------------------+
| Warning | 1265 | Data truncated for column 'name' at row 1 |
+---------+------+-------------------------------------------+
1 row in set (0.00 sec)
```

<!-- NULL OR NOT NULL -->
> *Null* means value not known;

* Null allows for records with no data;
* Not Null does not allow the column to have no data

```
mysql> CREATE TABLE cats2(
    -> name VARCHAR(100) NOT NULL,
    -> age INT NOT NULL);
Query OK, 0 rows affected (0.01 sec)

mysql> DESC cats2;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(100) | NO   |     | NULL    |       |
| age   | int          | NO   |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
2 rows in set (0.00 sec)
```
> If you insert value only in a column you get a warning and a default value is set for your column: 

```
mysql> INSERT INTO cats2(name) VALUES('Texas');

Query OK, 1 row affected, 1 warning (0.00 sec)

mysql> SHOW WARNINGS;
+---------+------+------------------------------------------+
| Level   | Code | Message                                  |
+---------+------+------------------------------------------+
| Warning | 1364 | Field 'age' doesn't have a default value |
+---------+------+------------------------------------------+
1 row in set (0.00 sec)

mysql> SELECT * FROM cats2;
+-------+-----+
| name  | age |
+-------+-----+
| Texas |   0 |
+-------+-----+
1 row in set (0.00 sec)
```

```
mysql> INSERT INTO cats2(age) VALUES(3);
Query OK, 1 row affected, 1 warning (0.00 sec)

mysql> SHOW WARNINGS;
+---------+------+-------------------------------------------+
| Level   | Code | Message                                   |
+---------+------+-------------------------------------------+
| Warning | 1364 | Field 'name' doesn't have a default value |
+---------+------+-------------------------------------------+
1 row in set (0.00 sec)

mysql> SELECT * FROM cats2;
+-------+-----+
| name  | age |
+-------+-----+
| Texas |   0 |
|       |   3 |
+-------+-----+
2 rows in set (0.00 sec)
```
> Default value for age column - 0, for name - ""(empty string);

<!-- Default values -->

> **DEFAULT** is used to set the default values for the columns 

```
mysql> CREATE TABLE cats3 
    -> ( name VARCHAR(20) DEFAULT 'no name provided',
    -> age INT DEFAULT 99);
Query OK, 0 rows affected (0.01 sec)

mysql> DESC cats3;
+-------+-------------+------+-----+------------------+-------+
| Field | Type        | Null | Key | Default          | Extra |
+-------+-------------+------+-----+------------------+-------+
| name  | varchar(20) | YES  |     | no name provided |       |
| age   | int         | YES  |     | 99               |       |
+-------+-------------+------+-----+------------------+-------+
2 rows in set (0.00 sec)
```