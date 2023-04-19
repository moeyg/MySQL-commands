# NULL & NOT NULL

- `NULL` : The value is Not known.

  ```sql
  SHOW COLUMNS FROM BEVERAGES;
  +-------+-------------+------+-----+---------+-------+
  | Field | Type        | Null | Key | Default | Extra |
  +-------+-------------+------+-----+---------+-------+
  | NAME  | varchar(25) | YES  |     | NULL    |       |
  | PRICE | int         | YES  |     | NULL    |       |
  +-------+-------------+------+-----+---------+-------+

  -- Null is YES
  ```

  ```sql
  -- PRICE is empty

  INSERT INTO BEVERAGES (NAME)
  VALUES ("PocariSweat");

  -- Result

  SELECT * FROM BEVERAGES;
  +-------------+-------+
  | NAME        | PRICE |
  +-------------+-------+
  | CocaCola    |  2000 |
  | Sprite      |  1800 |
  | Pepsi       |  2000 |
  | PocariSweat |  NULL |  -- NULL
  +-------------+-------+
  ```

  ```sql
  -- NAME & PRICE is empty

  INSERT INTO BEVERAGES ()
  VALUES ();

  -- Result

  mysql> SELECT * FROM BEVERAGES;
  +-------------+-------+
  | NAME        | PRICE |
  +-------------+-------+
  | CocaCola    |  2000 |
  | Sprite      |  1800 |
  | Pepsi       |  2000 |
  | PocariSweat |  NULL |  -- PRICE NULL
  | NULL        |  NULL |  -- NAME & PRICE NULL
  +-------------+-------+
  ```

<br>

- `NOT NULL`

  ```sql
  -- Setting NOT NULL

  CREATE TABLE SNACKS
  (
       NAME VARCHAR(25) NOT NULL,
       PRICE INT NOT NULL
  );
  
  -- Result

  SHOW COLUMNS FROM SNACKS;
  +-------+-------------+------+-----+---------+-------+
  | Field | Type        | Null | Key | Default | Extra |
  +-------+-------------+------+-----+---------+-------+
  | NAME  | varchar(25) | NO   |     | NULL    |       |
  | PRICE | int         | NO   |     | NULL    |       |
  +-------+-------------+------+-----+---------+-------+
  
  -- Null NO
  ```

  ```sql
  -- If NOT NULL, value is empty

  INSERT INTO SNACK (NAME)
  VALUES ("Pringles");
  ERROR 1364 (HY000): Field 'PRICE' doesn't have a default value
  ```

<br>

- `DEFAULT`

  ```sql
  -- Setting DEFAULT

  CREATE TABLE SNACKS
  (
       NAME VARCHAR(25) NOT NULL DEFAULT "UNKNOWN",
       PRICE INT NOT NULL DEFAULT 0
  );

  -- Result

  SHOW COLUMNS FROM SNACKS;
  +-------+-------------+------+-----+---------+-------+
  | Field | Type        | Null | Key | Default | Extra |
  +-------+-------------+------+-----+---------+-------+
  | NAME  | varchar(25) | NO   |     | UNKNOWN |       |
  | PRICE | int         | YES  |     | 0       |       |
  +-------+-------------+------+-----+---------+-------+

  -- Default UNKNOWN, 0
  ```

  ```sql
  -- PRICE Default value

  INSERT INTO SNACKS (NAME)
  VALUES ("Pringles");

  -- NAME Default value

  INSERT INTO SNACKS (PRICE)
  VALUES (1500);

  -- NAME & PRICE Default value

  INSERT INTO SNACKS ()
  VALUES ();

  -- Result

  SELECT * FROM SNACKS;
  +----------+-------+
  | NAME     | PRICE |
  +----------+-------+
  | Pringles |     0 |. -- PRICE DEFAULT VALUE
  | UNKNOWN  |  1500 |. -- NAME DEFAULT VALUE
  | UNKNOWN  |     0 |. -- NAME, PRICE DEFAULT VALUE
  +----------+-------+
  ```
