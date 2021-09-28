After connecting to MySql server, check for existing databases:

* List current databases: 

> `SHOW databases;` 

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```
___

* Create a database:

> `CREATE DATABASE <name> ;` 
```
mysql> CREATE DATABASE test_db;
Query OK, 1 row affected (0.00 sec)
```

___
* Delete a database:

> `DROP DATABASE <name>;`

```
mysql> DROP DATABASE test_db;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.00 sec)

```
---

* Tell SQL which database we want to work with or switch the databases :

> `USE <database name>;`

```
mysql> CREATE DATABASE dog_walking_app;
Query OK, 1 row affected (0.01 sec)

mysql> USE dog_walking_app;
Database changed
```
* Check the currently used database:

> `SELECT database();`

```
mysql> SELECT database();
+-----------------+
| database()      |
+-----------------+
| dog_walking_app |
+-----------------+
1 row in set (0.00 sec)
```

___

