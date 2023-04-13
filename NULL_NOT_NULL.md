# NULL & NOT NULL

- `NULL` : The value is Not known.

  ```sql
  mysql> SHOW COLUMNS FROM greenhouse;
  +----------+--------------+------+-----+---------+-------+
  | Field    | Type         | Null | Key | Default | Extra |
  +----------+--------------+------+-----+---------+-------+
  | crops    | varchar(255) | YES  |     | NULL    |       |
  | quantity | int          | YES  |     | NULL    |       |
  +----------+--------------+------+-----+---------+-------+
  2 rows in set (0.00 sec)

  -- Null is YES
  ```

  ```sql
  -- quantity is empty

  mysql> INSERT INTO greenhouse (crops)
      -> VALUES ('Corn');
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse;
  +------------+----------+
  | crops      | quantity |
  +------------+----------+
  | Carrot     |       15 |
  | Strawberry |       12 |
  | Potato     |       23 |
  | Pumpkin    |        8 |
  | Corn       |     NULL |  -- NULL
  +------------+----------+
  5 rows in set (0.00 sec)
  ```

  ```sql
  -- crops & quantity is empty

  mysql> INSERT INTO greenhouse ()
      -> VALUES ();
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse;
  +------------+----------+
  | crops      | quantity |
  +------------+----------+
  | Carrot     |       15 |
  | Strawberry |       12 |
  | Potato     |       23 |
  | Pumpkin    |        8 |
  | Corn       |     NULL |  -- quantity NULL
  | NULL       |     NULL |  -- crops & quantity NULL
  +------------+----------+
  6 rows in set (0.00 sec)
  ```

- `NOT NULL`

  ```sql
  -- Setting NOT NULL

  mysql> CREATE TABLE greenhouse2
      -> (
      ->     crops VARCHAR(255) NOT NULL,  -- Setting NOT NULL
      ->     quantity INT NOT NULL         -- Setting NOT NULL
      -> );
  Query OK, 0 rows affected (0.01 sec)

  -- Result

  mysql> SHOW COLUMNS FROM greenhouse2;
  +----------+--------------+------+-----+---------+-------+
  | Field    | Type         | Null | Key | Default | Extra |
  +----------+--------------+------+-----+---------+-------+
  | crops    | varchar(255) | NO   |     | NULL    |       |
  | quantity | int          | NO   |     | NULL    |       |
  +----------+--------------+------+-----+---------+-------+
  2 rows in set (0.00 sec)

  -- Null NO
  ```

  ```sql
  -- If NOT NULL, value is empty

  mysql> INSERT INTO greenhouse2 (crops)
      -> VALUES ('Tomato');
  ERROR 1364 (HY000): Field 'quantity' doesn't have a default value
  ```

- `DEFAULT`
  ```sql
  -- Setting DEFAULT

  mysql> CREATE TABLE greenhouse3
      -> (
      ->     crops VARCHAR(255) DEFAULT 'unknown',
      ->     quantity INT DEFAULT 0
      -> );
  Query OK, 0 rows affected (0.01 sec)

  -- Result

  mysql> SHOW COLUMNS FROM greenhouse3;
  +----------+--------------+------+-----+---------+-------+
  | Field    | Type         | Null | Key | Default | Extra |
  +----------+--------------+------+-----+---------+-------+
  | crops    | varchar(255) | YES  |     | unknown |       |
  | quantity | int          | YES  |     | 0       |       |
  +----------+--------------+------+-----+---------+-------+
  2 rows in set (0.01 sec)

  -- Default unknown, 0
  ```
  ```sql
  -- quantity Default value

  mysql> INSERT INTO greenhouse3 (crops)
      -> VALUES ('Apple');
  Query OK, 1 row affected (0.03 sec)

  -- crops Default value

  mysql> INSERT INTO greenhouse3 (quantity)
      -> VALUES (35);
  Query OK, 1 row affected (0.00 sec)

  -- crops & quantity Default value

  mysql> INSERT INTO greenhouse3 ()
      -> VALUES ();
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse3;
  +---------+----------+
  | crops   | quantity |
  +---------+----------+
  | Apple   |        0 |  -- quantity Default value
  | unknown |       35 |  -- crops Default value
  | unknown |        0 |  -- crops & quantity Default value
  +---------+----------+
  3 rows in set (0.00 sec)
  ```
- `NOT NULL` & `DEFAULT`
  ```sql
  -- Setting NOT NULL & DEFAULT

  mysql> CREATE TABLE greenhouse4
      -> (
      ->     crops VARCHAR(255) NOT NULL DEFAULT 'unknown',
      ->     quantity INT NOT NULL DEFAULT 0
      -> );
  Query OK, 0 rows affected (0.04 sec)

  -- Result

  mysql> SHOW COLUMNS FROM greenhouse4;
  +----------+--------------+------+-----+---------+-------+
  | Field    | Type         | Null | Key | Default | Extra |
  +----------+--------------+------+-----+---------+-------+
  | crops    | varchar(255) | NO   |     | unknown |       |
  | quantity | int          | NO   |     | 0       |       |
  +----------+--------------+------+-----+---------+-------+
  2 rows in set (0.02 sec)
  ```
  ```sql
  -- If value is NULL

  mysql> INSERT INTO greenhouse4 (crops, quantity)
      -> VALUES ('Acorn', NULL);
  ERROR 1048 (23000): Column 'quantity' cannot be null

  -- If value is empty

  mysql> INSERT INTO greenhouse4 (crops)
      -> VALUES ('Acorn');
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM greenhouse4;
  +-------+----------+
  | crops | quantity |
  +-------+----------+
  | Acorn |        0 |
  +-------+----------+
  1 row in set (0.00 sec)
  ```
