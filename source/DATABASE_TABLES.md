# DATABASE & TABLES

## DATABASE

- `DATABASE` 확인
  ```sql
  SHOW DATABASES;
  ```
  ```sql
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

<br>

- `DATABASE` 생성

  ```sql
  CREATE DATABASE database_name;
  ```

  ```sql
  mysql> CREATE DATABASE VENDING_MACHINE;
  Query OK, 1 row affected (0.00 sec)

  mysql> SHOW DATABASES;
  +--------------------+
  | Database           |
  +--------------------+
  | information_schema |
  | mysql              |
  | performance_schema |
  | sys                |
  | VENDING_MACHINE    |
  +--------------------+
  5 rows in set (0.01 sec)
  ```

- `DATABASE` 사용

  ```sql
  mysql> USE VENDING_MACHINE;
  Database changed
  ```

- 현재 사용 중인 `DATABASE` 확인

  ```sql
  mysql> SELECT DATABASE();
  +-----------------+
  | DATABASE()      |
  +-----------------+
  | vending_machine |
  +-----------------+
  1 row in set (0.00 sec)
  ```

<br>

- `DATABASE` 삭제

  ```sql
  mysql> DROP DATABASE VENDING_MACHINE;
  Query OK, 0 rows affected (0.00 sec)
  ```

<br>

## TABLE

- `TABLE` 생성

  ```sql
  mysql> CREATE TABLE BEVERAGES
    -> (
    ->     NAME VARCHAR(25),
    ->     PRICE INT
    -> );
  Query OK, 0 rows affected (0.01 sec)
  ```

<br>

- `TABLE` 확인

  ```sql
  mysql> SHOW TABLES;
  +---------------------------+
  | Tables_in_vending_machine |
  +---------------------------+
  | BEVERAGES                 |
  +---------------------------+
  1 row in set (0.00 sec)
  ```

<br>

- `TABLE COLUMN` 확인

  ```sql
  mysql> SHOW COLUMNS FROM BEVERAGES;
  +-------+-------------+------+-----+---------+-------+
  | Field | Type        | Null | Key | Default | Extra |
  +-------+-------------+------+-----+---------+-------+
  | NAME  | varchar(25) | YES  |     | NULL    |       |
  | PRICE | int         | YES  |     | NULL    |       |
  +-------+-------------+------+-----+---------+-------+
  2 rows in set (0.00 sec)
  ```

<br>

- `TABLE` 삭제

  ```sql
  mysql> DROP TABLE BEVERAGES;
  Query OK, 0 rows affected (0.00 sec)

  mysql> SHOW TABLES;
  Empty set (0.00 sec)
  ```
