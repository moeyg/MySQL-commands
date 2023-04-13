# INSERT DATA

- 데이터 입력

  ```sql
  INSERT INTO table_name (column_name) VALUES (data_type);
  ```

  ```sql
  mysql> INSERT INTO soap (crops, quantity)
      -> VALUES ("Carrot", 15);
  Query OK, 1 row affected (0.01 sec)
  ```

    <br>

- 다중 `INSERT`

  ```sql
  INSERT INTO table_name (column_name) VALUES (data_type), (data_type), (data_type);
  ```

  ```sql
  mysql> INSERT INTO greenhouse (crops, quantity)
      -> VALUES ("Strawberry", 12),
      ->        ("Potato", 23),
      ->        ("Pumpkin", 8);
  Query OK, 3 rows affected (0.00 sec)
  Records: 3  Duplicates: 0  Warnings: 0
  ```

<br>

- 데이터 입력 확인
  ```sql
  SELECT * FROM table_name;
  ```
  ```sql
  mysql> SELECT * FROM greenhouse;
  +------------+----------+
  | crops      | quantity |
  +------------+----------+
  | Carrot     |       15 |
  | Strawberry |       12 |
  | Potato     |       23 |
  | Pumpkin    |        8 |
  +------------+----------+
  4 rows in set (0.00 sec)
  ```
