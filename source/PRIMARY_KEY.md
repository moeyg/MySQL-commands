# PRIMARY KEY

- `PRIMARY KEY` : A unique identifier

  ```sql
  -- Setting PRIMARY KEY

  CREATE TABLE BEVERAGES
  (
      BARCODE INT NOT NULL,
      NAME VARCHAR(25),
      PRICE INT,
      PRIMARY KEY (BARCODE)
  );

  -- Other way
  CREATE TABLE BEVERAGES
  (
      BARCODE INT NOT NULL PRIMARY KEY,
      NAME VARCHAR(25),
      PRICE INT
  );

  -- Result

  SHOW COLUMNS FROM BEVERAGES;
  +---------+-------------+------+-----+---------+-------+
  | Field   | Type        | Null | Key | Default | Extra |
  +---------+-------------+------+-----+---------+-------+
  | BARCODE | int         | NO   | PRI | NULL    |       |    
  | NAME    | varchar(25) | YES  |     | NULL    |       |
  | PRICE   | int         | YES  |     | NULL    |       |
  +---------+-------------+------+-----+---------+-------+
  ```

  ```sql
  -- Insert PRIMARY KEY

  INSERT INTO BEVERAGES (BARCODE, NAME, PRICE)
  VALUES (1, "CocaCola", 2000),
         (2, "Sprite", 1800);

  -- Result

  SELECT * FROM BEVERAGES;
  +---------+----------+-------+
  | BARCODE | NAME     | PRICE |
  +---------+----------+-------+
  |       1 | CocaCola |  2000 |
  |       2 | Sprite   |  1800 |
  +---------+----------+-------+
  ```

<br>

- 이미 `PRIMARY KEY`가 존재하는 경우

  ```sql
  INSERT INTO BEVERAGES (BARCODE, NAME, PRICE)
  VALUES (1, "Pepsi", 2000);
  ERROR 1062 (23000): Duplicate entry "1" for key "BEVERAGES.PRIMARY"
  ```

<br>

- `PRIMARY KEY`를 자동으로 설정하기

  ```sql
  -- Setting AUTO_INCREMENT

  CREATE TABLE BEVERAGES
  (
      BARCODE INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
      NAME VARCHAR(25),
      PRICE INT
  );
  
  -- Result

  SHOW COLUMNS FROM BEVERAGES;
  +---------+-------------+------+-----+---------+----------------+ 
  | Field   | Type        | Null | Key | Default | Extra          |
  +---------+-------------+------+-----+---------+----------------+
  | BARCODE | int         | NO   | PRI | NULL    | auto_increment |
  | NAME    | varchar(25) | YES  |     | NULL    |                |
  | PRICE   | int         | YES  |     | NULL    |                |
  +---------+-------------+------+-----+---------+----------------+
  ```

  ```sql
  -- Insert datas

  INSERT INTO BEVERAGES (NAME, PRICE)
  VALUES ("CocaCola", 2000),
         ("Sprite", 1800),
         ("Pepsi", 2000),
         ("PocariSweat", 2200);

  -- Result

  SELECT * FROM BEVERAGES;
  +---------+-------------+-------+
  | BARCODE | NAME        | PRICE |
  +---------+-------------+-------+
  |       1 | CocaCola    |  2000 |
  |       2 | Sprite      |  1800 |
  |       3 | Pepsi       |  2000 |
  |       4 | PocariSweat |  2200 |
  +---------+-------------+-------+
  ```
