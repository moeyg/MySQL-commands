# INSERT DATA

- 데이터 입력

  ```sql
  INSERT INTO BEVERAGES (NAME, PRICE)
  VALUES ("CocaCola", 2000);
  ```

    <br>

- 다중 `INSERT`

  ```sql
  INSERT INTO BEVERAGES (NAME, PRICE)
  VALUES ("Sprite", 1800),
         ("Pepsi", 2000);
  ```

<br>

- 데이터 입력 확인

  ```sql
  SELECT * FROM BEVERAGES;
  +----------+-------+
  | NAME     | PRICE |
  +----------+-------+
  | CocaCola |  2000 |
  | Sprite   |  1800 |
  | Pepsi    |  2000 |
  +----------+-------+
  ```
