# CRUD

## `C`reate

- `CREATE TABLES` : 테이블 생성
  ```sql
  mysql> CREATE TABLE greenhouse
      -> (
      ->     No INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
      ->     crops VARCHAR(255),
      ->     quantity INT,
      ->     price INT,
      ->     type VARCHAR(255)
      -> );
  Query OK, 0 rows affected (0.02 sec)
  ```
- `INSERT INTO … VALUES …` : 테이블에 데이터 입력
  ```sql
  mysql> INSERT INTO greenhouse (crops, quantity, price, type)
      -> VALUES ('Potato', 5, 500, 'Bulbous'),
      ->        ('Pumpkin', 2, 1000, 'Vegetable'),
      ->        ('Chestnut', 3, 500, 'Seeds'),
      ->        ('Walnut', 4, 500, 'Seeds'),
      ->        ('Carrot', 10, 700, 'Vegetable'),
      ->        ('Strawberry', 15, 600, 'Vegetable'),
      ->        ('Sweetpotato', 7, 600, 'Bulbous');
  Query OK, 7 rows affected (0.00 sec)
  Records: 7  Duplicates: 0  Warnings: 0
  ```

<br>

## `R`ead

- `SELECT * FROM …` : 테이블의 내용 보기
  ```sql
  mysql> SELECT * FROM greenhouse;
  +----+-------------+----------+-------+-----------+
  | No | crops       | quantity | price | type      |
  +----+-------------+----------+-------+-----------+
  |  1 | Potato      |        5 |   500 | Bulbous   |
  |  2 | Pumpkin     |        2 |  1000 | Vegetable |
  |  3 | Chestnut    |        3 |   500 | Seeds     |
  |  4 | Walnut      |        4 |   500 | Seeds     |
  |  5 | Carrot      |       10 |   700 | Vegetable |
  |  6 | Strawberry  |       15 |   600 | Vegetable |
  |  7 | Sweetpotato |        7 |   600 | Bulbous   |
  +----+-------------+----------+-------+-----------+
  7 rows in set (0.00 sec)

  -- * : All columns
  -- SELECT * FROM breadTBL; : Get datas of all columns from breadTBL
  ```
- `SELECT … FROM …` : 테이블의 특정 `COLUMN`만 내용 보기
  ```sql
  mysql> SELECT crops FROM greenhouse;
  +-------------+
  | crops       |
  +-------------+
  | Potato      |
  | Pumpkin     |
  | Chestnut    |
  | Walnut      |
  | Carrot      |
  | Strawberry  |
  | Sweetpotato |
  +-------------+
  7 rows in set (0.00 sec)
  ```
  ```sql
  mysql> SELECT crops, price FROM greenhouse;
  +-------------+-------+
  | crops       | price |
  +-------------+-------+
  | Potato      |   500 |
  | Pumpkin     |  1000 |
  | Chestnut    |   500 |
  | Walnut      |   500 |
  | Carrot      |   700 |
  | Strawberry  |   600 |
  | Sweetpotato |   600 |
  +-------------+-------+
  7 rows in set (0.00 sec)
  ```
- `SELECT * FROM … WHERE …` : 테이블에서 조건(`WHERE`)에 맞는 `ROW`만 보기
  ```sql
  mysql> SELECT * FROM greenhouse WHERE price=600;
  +----+-------------+----------+-------+-----------+
  | No | crops       | quantity | price | type      |
  +----+-------------+----------+-------+-----------+
  |  6 | Strawberry  |       15 |   600 | Vegetable |
  |  7 | Sweetpotato |        7 |   600 | Bulbous   |
  +----+-------------+----------+-------+-----------+
  2 rows in set (0.01 sec)
  ```
  ```sql
  mysql> SELECT crops, quantity FROM greenhouse WHERE type='Vegetable';
  +------------+----------+
  | crops      | quantity |
  +------------+----------+
  | Pumpkin    |        2 |
  | Carrot     |       10 |
  | Strawberry |       15 |
  +------------+----------+
  3 rows in set (0.00 sec)
  ```
- `AS` : `COLUMN` 별칭 등록하기
  ```sql
  -- Standard expression

  mysql> SELECT crops, quantity FROM greenhouse;
  +-------------+----------+
  | crops       | quantity |
  +-------------+----------+
  | Potato      |        5 |
  | Pumpkin     |        2 |
  | Chestnut    |        3 |
  | Walnut      |        4 |
  | Carrot      |       10 |
  | Strawberry  |       15 |
  | Sweetpotato |        7 |
  +-------------+----------+
  7 rows in set (0.00 sec)

  -- Expression using AS

  mysql> SELECT crops, quantity AS qty FROM greenhouse;
  +-------------+------+
  | crops       | qty  |
  +-------------+------+
  | Potato      |    5 |
  | Pumpkin     |    2 |
  | Chestnut    |    3 |
  | Walnut      |    4 |
  | Carrot      |   10 |
  | Strawberry  |   15 |
  | Sweetpotato |    7 |
  +-------------+------+
  7 rows in set (0.00 sec)
  ```
  ```sql
  mysql> SELECT No, crops, quantity FROM greenhouse WHERE No=quantity;
  +----+-------------+----------+
  | No | crops       | quantity |
  +----+-------------+----------+
  |  2 | Pumpkin     |        2 |
  |  3 | Chestnut    |        3 |
  |  4 | Walnut      |        4 |
  |  7 | Sweetpotato |        7 |
  +----+-------------+----------+
  4 rows in set (0.00 sec)
  ```

<br>

## `U`pdate

- `UPDATE … SET … WHERE` : 조건(`WHERE`)에 맞는 부분의 내용을 `SET`에 따라 `UPDATE`
  ```sql
  -- UPDATE column contents

  mysql> UPDATE greenhouse SET type='Seed' WHERE type='Seeds';
  Query OK, 2 rows affected (0.01 sec)
  Rows matched: 2  Changed: 2  Warnings: 0

  -- Result

  mysql> SELECT * FROM greenhouse WHERE type='Seed';
  +----+----------+----------+-------+------+
  | No | crops    | quantity | price | type |
  +----+----------+----------+-------+------+
  |  3 | Chestnut |        3 |   600 | Seed |
  |  4 | Walnut   |        4 |   500 | Seed |
  +----+----------+----------+-------+------+
  2 rows in set (0.00 sec)
  ```
  ```sql
  -- UPDATE value contents

  mysql> UPDATE greenhouse SET price=600 WHERE crops='Chestnut';
  Query OK, 1 row affected (0.01 sec)
  Rows matched: 1  Changed: 1  Warnings: 0

  -- Result

  mysql> SELECT * FROM greenhouse WHERE crops='Chestnut';
  +----+----------+----------+-------+------+
  | No | crops    | quantity | price | type |
  +----+----------+----------+-------+------+
  |  3 | Chestnut |        3 |   600 | Seed |
  +----+----------+----------+-------+------+
  1 row in set (0.00 sec)
  ```
  ```sql
  -- UPDATE two crops type value

  mysql> UPDATE greenhouse SET price=550 WHERE type='Seed';
  Query OK, 2 rows affected (0.00 sec)
  Rows matched: 2  Changed: 2  Warnings: 0

  -- Result

  mysql> SELECT * FROM greenhouse WHERE type='Seed';
  +----+----------+----------+-------+------+
  | No | crops    | quantity | price | type |
  +----+----------+----------+-------+------+
  |  3 | Chestnut |        3 |   550 | Seed |
  |  4 | Walnut   |        4 |   550 | Seed |
  +----+----------+----------+-------+------+
  2 rows in set (0.00 sec)
  ```

<br>

## `D`elete

- `DELETE FROM … WHERE …` : 조건(`WHERE`)에 맞는 부분을 삭제

  ```sql
  -- DELETE

  mysql> DELETE FROM greenhouse WHERE crops='Strawberry';
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse;
  +----+-------------+----------+-------+-----------+
  | No | crops       | quantity | price | type      |
  +----+-------------+----------+-------+-----------+
  |  1 | Potato      |        5 |   500 | Bulbous   |
  |  2 | Pumpkin     |        2 |  1000 | Vegetable |
  |  3 | Chestnut    |        3 |   550 | Seed      |
  |  4 | Walnut      |        4 |   550 | Seed      |
  |  5 | Carrot      |       10 |   700 | Vegetable |
  |  7 | Sweetpotato |        7 |   600 | Bulbous   |
  +----+-------------+----------+-------+-----------+
  6 rows in set (0.00 sec)

  -- ❗️ NOT CHANGED No value
  ```

  ```sql
  -- DELETE

  mysql> DELETE FROM greenhouse WHERE price<=600;
  Query OK, 4 rows affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse;
  +----+---------+----------+-------+-----------+
  | No | crops   | quantity | price | type      |
  +----+---------+----------+-------+-----------+
  |  2 | Pumpkin |        2 |  1000 | Vegetable |
  |  5 | Carrot  |       10 |   700 | Vegetable |
  +----+---------+----------+-------+-----------+
  2 rows in set (0.00 sec)
  ```

  ```sql
  -- DELETE

  mysql> DELETE FROM greenhouse WHERE No=quantity;
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse;
  +----+--------+----------+-------+-----------+
  | No | crops  | quantity | price | type      |
  +----+--------+----------+-------+-----------+
  |  5 | Carrot |       10 |   700 | Vegetable |
  +----+--------+----------+-------+-----------+
  1 row in set (0.00 sec)
  ```

- `DELETE TABLE` : 테이블 삭제
  ```sql
  -- DELETE TABLE

  mysql> DELETE FROM greenhouse;
  Query OK, 0 rows affected (0.00 sec)

  -- Result : DELETE is keeps the table

  mysql> SHOW TABLES;
  +----------------+
  | Tables_in_farm |
  +----------------+
  | greenhouse     |
  +----------------+

  -- ❗️ DROP TABLE

  mysql> DROP TABLE greenhouse2;
  Query OK, 0 rows affected (0.00 sec)

  -- Result

  mysql> SHOW TABLES;
  Empty set (0.00 sec)
  ```
