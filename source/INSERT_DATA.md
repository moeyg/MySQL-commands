# INSERT DATA

- 데이터 입력

  ```sql
  mysql> INSERT INTO BEVERAGES (NAME, PRICE)
      -> VALUES ("CocaCola", 2000);
  Query OK, 1 row affected (0.00 sec)
  ```

    <br>

- 다중 `INSERT`

  ```sql
  mysql> INSERT INTO BEVERAGES (NAME, PRICE)
      -> VALUES ("Sprite", 1800),
      ->        ("Pepsi", 2000);
  Query OK, 2 rows affected (0.00 sec)
  Records: 2  Duplicates: 0  Warnings: 0
  ```

<br>

- 데이터 입력 확인

  ```sql
  mysql> SELECT * FROM BEVERAGES;
  +----------+-------+
  | NAME     | PRICE |
  +----------+-------+
  | CocaCola |  2000 |
  | Sprite   |  1800 |
  | Pepsi    |  2000 |
  +----------+-------+
  3 rows in set (0.00 sec)
  ```
