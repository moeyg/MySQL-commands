# DATABASE & TABLES

## DATABASE

- `DATABASE` 확인

  ```sql
  SHOW DATABASES;
  +--------------------+
  | Database           |
  +--------------------+
  | information_schema |
  | mysql              |
  | performance_schema |
  | sys                |
  +--------------------+
  ```

<br>

- `DATABASE` 생성

  ```sql
  CREATE DATABASE VENDING_MACHINE;
  ```
  
  ```sql
  SHOW DATABASES;
  +--------------------+
  | Database           |
  +--------------------+
  | information_schema |
  | mysql              |
  | performance_schema |
  | sys                |
  | VENDING_MACHINE    |
  +--------------------+
  ```

- `DATABASE` 사용

  ```sql
  USE VENDING_MACHINE;
  ```

- 현재 사용 중인 `DATABASE` 확인

  ```sql
  SELECT DATABASE();
  +-----------------+
  | DATABASE()      |
  +-----------------+
  | vending_machine |
  +-----------------+
  ```

<br>

- `DATABASE` 삭제

  ```sql
  DROP DATABASE VENDING_MACHINE;
  ```

<br>

## TABLE

- `TABLE` 생성

  ```sql
  CREATE TABLE BEVERAGES
  (
       NAME VARCHAR(25),
       PRICE INT
  );
  ```

<br>

- `TABLE` 확인

  ```sql
  SHOW TABLES;
  +---------------------------+
  | Tables_in_vending_machine |
  +---------------------------+
  | BEVERAGES                 |
  +---------------------------+
  ```

<br>

- `TABLE COLUMN` 확인

  ```sql
  SHOW COLUMNS FROM BEVERAGES;
  +-------+-------------+------+-----+---------+-------+
  | Field | Type        | Null | Key | Default | Extra |
  +-------+-------------+------+-----+---------+-------+
  | NAME  | varchar(25) | YES  |     | NULL    |       |
  | PRICE | int         | YES  |     | NULL    |       |
  +-------+-------------+------+-----+---------+-------+
  ```

<br>

- `TABLE` 삭제

  ```sql
  DROP TABLE BEVERAGES;
  ```
  
  ```sql
  SHOW TABLES;
  Empty set (0.00 sec)
  ```
