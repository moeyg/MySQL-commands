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
  mysql> CREATE DATABASE FARM;
  Query OK, 1 row affected (0.00 sec)

  mysql> SHOW DATABASES;
  +--------------------+
  | Database           |
  +--------------------+
  | FARM               |
  | information_schema |
  | mysql              |
  | performance_schema |
  | sys                |
  +--------------------+
  5 rows in set (0.01 sec)
  ```

- `DATABASE` 사용

  ```sql
  USE database_name;
  ```

  ```sql
  mysql> USE FARM;
  Database changed
  ```

- 현재 사용 중인 `DATABASE` 확인

  ```sql
  SELECT DATABASE();
  ```

  ```sql
  mysql> SELECT DATABASE();
  +------------+
  | DATABASE() |
  +------------+
  | FARM       |
  +------------+
  1 row in set (0.00 sec)
  ```

<br>

- `DATABASE` 삭제
  ```sql
  DROP DATABASE database_name;
  ```
  ```sql
  mysql> DROP DATABASE FARM;
  Query OK, 0 rows affected (0.00 sec)
  ```

<br>

## TABLE

- `TABLE` 생성

  ```sql
  CREATE TABLE table_name
  (
      column_name data_type,
      column_name data_type
  );

  ```

  ```sql
  mysql> CREATE TABLE greenhouse
      -> (
      ->     crops VARCHAR(255),
      ->     quantity INT
      -> );
  Query OK, 0 rows affected (0.01 sec)
  ```

<br>

- `TABLE` 확인

  ```sql
  SHOW TABLES;
  ```

  ```sql
  mysql> SHOW TABLES;
  +----------------+
  | Tables_in_farm |
  +----------------+
  | greenhouse     |
  +----------------+
  1 row in set (0.00 sec)
  ```

<br>

- `TABLE COLUMN` 확인
  ```sql
  SHOW COLUMNS FROM table_name;
  ```
  ```sql
  mysql> SHOW COLUMNS FROM greenhouse;
  +----------+--------------+------+-----+---------+-------+
  | Field    | Type         | Null | Key | Default | Extra |
  +----------+--------------+------+-----+---------+-------+
  | crops    | varchar(255) | YES  |     | NULL    |       |
  | quantity | int          | YES  |     | NULL    |       |
  +----------+--------------+------+-----+---------+-------+
  2 rows in set (0.00 sec)
  ```

<br>

- `TABLE` 삭제

  ```bash
  DROP TABLE table_name;
  ```

  ```sql
  mysql> DROP TABLE greenhouse;
  Query OK, 0 rows affected (0.00 sec)

  mysql> SHOW TABLES;
  Empty set (0.00 sec)
  ```
