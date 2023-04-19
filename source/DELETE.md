# `D`elete

- `DELETE FROM … WHERE …` : 조건(`WHERE`)에 맞는 부분을 삭제

  ```sql
  -- DELETE

  DELETE
  FROM BEVERAGES
  WHERE NAME="Pepsi";
  ```
  ```sql
  -- Result

  SELECT * FROM BEVERAGES;
  +---------+-------------+-------+--------------+
  | BARCODE | NAME        | PRICE | TYPE         |
  +---------+-------------+-------+--------------+
  |       1 | CocaCola    |  1900 | SOFT_DRINK   |
  |       2 | Sprite      |  1900 | SOFT_DRINK   |
  |       4 | PocariSweat |  2200 | SPORTS_DRINK |
  |       5 | Monster     |  2500 | ENERGY_DRINK |
  +---------+-------------+-------+--------------+
  
  -- ❗️ NOT CHANGED BARCODE value
  ```
  ```sql
  -- DELETE

  DELETE
  FROM BEVERAGES
  WHERE PRICE=2200;
  ```
  ```sql
  -- Result

  SELECT * FROM BEVERAGES;
  +---------+----------+-------+--------------+
  | BARCODE | NAME     | PRICE | TYPE         |
  +---------+----------+-------+--------------+
  |       1 | CocaCola |  1900 | SOFT_DRINK   |
  |       2 | Sprite   |  1900 | SOFT_DRINK   |
  |       5 | Monster  |  2500 | ENERGY_DRINK |
  +---------+----------+-------+--------------+
  ```

<br>

- `DELETE TABLE` : 테이블 삭제

  ```sql
  -- DELETE TABLE

  DELETE FROM BEVERAGES;
  ```
  ```sql
  -- Result : DELETE is keeps the table

  SHOW TABLES;
  +---------------------------+
  | Tables_in_vending_machine |
  +---------------------------+
  | BEVERAGES                 |
  +---------------------------+
  ```
  ```sql
  -- ❗️ DROP TABLE

  DROP TABLE BEVERAGES;
  ```
  ```sql
  -- Result

  SHOW TABLES;
  Empty set (0.00 sec)
  ```
