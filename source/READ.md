# `R`ead

- `SELECT * FROM …` : 테이블의 내용 보기

  ```sql
  SELECT * FROM BEVERAGES;
  +---------+-------------+-------+--------------+
  | BARCODE | NAME        | PRICE | TYPE         |
  +---------+-------------+-------+--------------+
  |       1 | CocaCola    |  2000 | SOFT_DRINK   |
  |       2 | Sprite      |  1800 | SOFT_DRINK   |
  |       3 | Pepsi       |  2000 | SOFT_DRINK   |
  |       4 | PocariSweat |  2200 | SPORTS_DRINK |
  |       5 | Monster     |  2000 | ENERGY_DRINK |
  +---------+-------------+-------+--------------+

  -- * : All columns
  -- SELECT * FROM breadTBL; : Get datas of all columns from breadTBL
  ```

  <br>

- `SELECT … FROM …` : 테이블의 특정 `COLUMN`만 내용 보기
  ```sql
  SELECT NAME FROM BEVERAGES;
  +-------------+
  | NAME        |
  +-------------+
  | CocaCola    |
  | Sprite      |
  | Pepsi       |
  | PocariSweat |
  | Monster     |
  +-------------+
  ```
  ```sql
  SELECT NAME, TYPE FROM BEVERAGES;
  +-------------+--------------+
  | NAME        | TYPE         |
  +-------------+--------------+
  | CocaCola    | SOFT_DRINK   |
  | Sprite      | SOFT_DRINK   |
  | Pepsi       | SOFT_DRINK   |
  | PocariSweat | SPORTS_DRINK |
  | Monster     | ENERGY_DRINK |
  +-------------+--------------+
  ```

<br>

- `SELECT * FROM … WHERE …` : 테이블에서 조건(`WHERE`)에 맞는 `ROW`만 보기
  ```sql
  SELECT *
  FROM BEVERAGES
  WHERE PRICE=2000;
  +---------+----------+-------+--------------+
  | BARCODE | NAME     | PRICE | TYPE         |
  +---------+----------+-------+--------------+
  |       1 | CocaCola |  2000 | SOFT_DRINK   |
  |       3 | Pepsi    |  2000 | SOFT_DRINK   |
  |       5 | Monster  |  2000 | ENERGY_DRINK |
  +---------+----------+-------+--------------+
  ```
  ```sql
  SELECT NAME, PRICE
  FROM BEVERAGES
  WHERE TYPE="SOFT_DRINK";
  +----------+-------+
  | NAME     | PRICE |
  +----------+-------+
  | CocaCola |  2000 |
  | Sprite   |  1800 |
  | Pepsi    |  2000 |
  +----------+-------+
  ```

<br>

- `AS` : `COLUMN` 별칭 등록하기

  ```sql
  -- Expression using AS (alias)

  SELECT NAME,
         TYPE AS DRINK_TYPE
  FROM BEVERAGES;
  +-------------+--------------+
  | NAME        | DRINK_TYPE   |
  +-------------+--------------+
  | CocaCola    | SOFT_DRINK   |
  | Sprite      | SOFT_DRINK   |
  | Pepsi       | SOFT_DRINK   |
  | PocariSweat | SPORTS_DRINK |
  | Monster     | ENERGY_DRINK |
  +-------------+--------------+
  ```
  
