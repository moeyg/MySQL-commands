# `C`reate

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

<br>

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
