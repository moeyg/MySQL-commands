# `C`reate

- `CREATE TABLES ...` : 테이블 생성
  ```sql
  CREATE TABLE BEVERAGES
  (
      BARCODE INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
      NAME VARCHAR(25),
      PRICE INT,
     TYPE VARCHAR(25)
  );
  ```

<br>

- `INSERT INTO ... VALUES ...` : 테이블에 데이터 입력
  ```sql
  INSERT INTO BEVERAGES (NAME, PRICE, TYPE)
  VALUES ("CocaCola", 2000, "SOFT_DRINK"),
         ("Sprite", 1800, "SOFT_DRINK"),
         ("Pepsi", 2000, "SOFT_DRINK"),
         ("PocariSweat", 2200, "SPORTS_DRINK"),
         ("Monster", 2000, "ENERGY_DRINK");
  ```
