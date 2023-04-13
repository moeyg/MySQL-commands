# `R`ead

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

  <br>

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

<br>

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
  mysql> SELECT crops, quantity FROM greenhouse WHERE type="Vegetable";
  +------------+----------+
  | crops      | quantity |
  +------------+----------+
  | Pumpkin    |        2 |
  | Carrot     |       10 |
  | Strawberry |       15 |
  +------------+----------+
  3 rows in set (0.00 sec)
  ```

<br>

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

  mysql> SELECT crops, quantity AS "qty" FROM greenhouse;
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
