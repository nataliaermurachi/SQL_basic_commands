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

