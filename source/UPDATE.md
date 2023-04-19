# `U`pdate

- `UPDATE … SET … WHERE` : 조건(`WHERE`)에 맞는 부분의 내용을 `SET`에 따라 `UPDATE`

  ```sql
  -- UPDATE column contents

  UPDATE BEVERAGES
  SET PRICE=2500
  WHERE NAME="Monster";
  ```
  ```sql
  -- Result

  SELECT * FROM BEVERAGES;
  +---------+-------------+-------+--------------+
  | BARCODE | NAME        | PRICE | TYPE         |
  +---------+-------------+-------+--------------+
  |       1 | CocaCola    |  2000 | SOFT_DRINK   |
  |       2 | Sprite      |  1800 | SOFT_DRINK   |
  |       3 | Pepsi       |  2000 | SOFT_DRINK   |
  |       4 | PocariSweat |  2200 | SPORTS_DRINK |
  |       5 | Monster     |  2500 | ENERGY_DRINK |  -- UPDATE PRICE 2000 → 2500
  +---------+-------------+-------+--------------+
  ```
  ```sql
  -- UPDATE two crops type value

  UPDATE BEVERAGES
  SET PRICE=1900
  WHERE TYPE="SOFT_DRINK";
  ```
  ```sql
  -- Result

  SELECT * FROM BEVERAGES;
  +---------+-------------+-------+--------------+
  | BARCODE | NAME        | PRICE | TYPE         |
  +---------+-------------+-------+--------------+
  |       1 | CocaCola    |  1900 | SOFT_DRINK   |  -- UPDATE PRICE 2000 → 1900
  |       2 | Sprite      |  1900 | SOFT_DRINK   |  -- UPDATE PRICE 1800 → 1900
  |       3 | Pepsi       |  1900 | SOFT_DRINK   |  -- UPDATE PRICE 2000 → 1900
  |       4 | PocariSweat |  2200 | SPORTS_DRINK |
  |       5 | Monster     |  2500 | ENERGY_DRINK |
  +---------+-------------+-------+--------------+
  ```
