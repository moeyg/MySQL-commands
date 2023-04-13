# `D`elete

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
