# `U`pdate

- `UPDATE … SET … WHERE` : 조건(`WHERE`)에 맞는 부분의 내용을 `SET`에 따라 `UPDATE`

  ```sql
  -- UPDATE column contents

  mysql> UPDATE greenhouse
      -> SET type = "Seed"
      -> WHERE type = "Seeds";
  Query OK, 2 rows affected (0.01 sec)
  Rows matched: 2  Changed: 2  Warnings: 0

  -- Result

  mysql> SELECT * FROM greenhouse
      -> WHERE type = "Seed";
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

  mysql> UPDATE greenhouse
      -> SET price = 600
      -> WHERE crops = "Chestnut";
  Query OK, 1 row affected (0.01 sec)
  Rows matched: 1  Changed: 1  Warnings: 0

  -- Result

  mysql> SELECT * FROM greenhouse
      -> WHERE crops="Chestnut";
  +----+----------+----------+-------+------+
  | No | crops    | quantity | price | type |
  +----+----------+----------+-------+------+
  |  3 | Chestnut |        3 |   600 | Seed |
  +----+----------+----------+-------+------+
  1 row in set (0.00 sec)
  ```

  ```sql
  -- UPDATE two crops type value

  mysql> UPDATE greenhouse
      -> SET price=550
      -> WHERE type="Seed";
  Query OK, 2 rows affected (0.00 sec)
  Rows matched: 2  Changed: 2  Warnings: 0

  -- Result

  mysql> SELECT * FROM greenhouse
      -> WHERE type="Seed";
  +----+----------+----------+-------+------+
  | No | crops    | quantity | price | type |
  +----+----------+----------+-------+------+
  |  3 | Chestnut |        3 |   550 | Seed |
  |  4 | Walnut   |        4 |   550 | Seed |
  +----+----------+----------+-------+------+
  2 rows in set (0.00 sec)
  ```
