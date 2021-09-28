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