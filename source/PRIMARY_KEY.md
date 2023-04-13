# PRIMARY KEY

- `PRIMARY KEY` : A unique identifier
    
    ```sql
    -- Setting PRIMARY KEY
    
    mysql> CREATE TABLE greenhouse5
        -> (
        ->     No INT NOT NULL,
        ->     crops VARCHAR(255),
        ->     quantity INT,
        ->     PRIMARY KEY (No)
        -> );
    Query OK, 0 rows affected (0.01 sec)
    
    -- Other way
    
    mysql> CREATE TABLE greenhouse5
        -> (
        ->     No INT PRIMARY KEY NOT NULL,
        ->     crops VARCHAR(255),
        ->     quantity INT
        -> );
    
    -- Result
    
    mysql> SHOW COLUMNS FROM greenhouse5;
    +----------+--------------+------+-----+---------+-------+
    | Field    | Type         | Null | Key | Default | Extra |
    +----------+--------------+------+-----+---------+-------+
    | No       | int          | NO   | PRI | NULL    |       |
    | crops    | varchar(255) | YES  |     | NULL    |       |
    | quantity | int          | YES  |     | NULL    |       |
    +----------+--------------+------+-----+---------+-------+
    3 rows in set (0.00 sec)
    ```
    
    ```sql
    -- Insert PRIMARY KEY
    
    mysql> INSERT INTO greenhouse5 (No, crops, quantity)
        -> VALUES (1, 'Chestnut', 20),
        ->        (2, 'Walnut', 20);
    Query OK, 2 rows affected (0.01 sec)
    Records: 2  Duplicates: 0  Warnings: 0
    
    -- Result
    
    mysql> SELECT * FROM greenhouse5;
    +----+----------+----------+
    | No | crops    | quantity |
    +----+----------+----------+
    |  1 | Chestnut |       20 |
    |  2 | Walnut   |       20 |
    +----+----------+----------+
    2 rows in set (0.00 sec)
    ```
    
- 이미 `PRIMARY KEY`가 존재하는 경우
    
    ```sql
    -- If assigning a key value that already exists.
    
    mysql> INSERT INTO greenhouse5 (No, crops, quantity)
        -> VALUES (1, 'Garlic', 30);
    ERROR 1062 (23000): Duplicate entry '1' for key 'greenhouse5.PRIMARY'
    ```
    
- `PRIMARY KEY`를 자동으로 설정하기
    
    ```sql
    -- Setting AUTO_INCREMENT
    
    mysql> CREATE TABLE greenhouse6
        -> (
        ->     No INT PRIMARY KEY AUTO_INCREMENT NOT NULL,
        ->     crops VARCHAR(255),
        ->     quantity INT
        -> );
    Query OK, 0 rows affected (0.01 sec)
    
    -- Result
    
    mysql> SHOW COLUMNS FROM greenhouse6;
    +----------+--------------+------+-----+---------+----------------+
    | Field    | Type         | Null | Key | Default | Extra          |
    +----------+--------------+------+-----+---------+----------------+
    | No       | int          | NO   | PRI | NULL    | auto_increment |
    | crops    | varchar(255) | YES  |     | NULL    |                |
    | quantity | int          | YES  |     | NULL    |                |
    +----------+--------------+------+-----+---------+----------------+
    3 rows in set (0.00 sec)
    ```
    
    ```sql
    -- Insert datas
    
    mysql> INSERT INTO greenhouse6 (crops, quantity)
        -> VALUES ('Radish', 3),
        ->        ('Pepper', 2),
        ->        ('Sweetpotato', 3);
    Query OK, 3 rows affected (0.00 sec)
    Records: 3  Duplicates: 0  Warnings: 0
    
    -- Result
    
    mysql> SELECT * FROM greenhouse6;
    +----+-------------+----------+
    | No | crops       | quantity |
    +----+-------------+----------+
    |  1 | Radish      |        3 |
    |  2 | Pepper      |        2 |
    |  3 | Sweetpotato |        3 |
    +----+-------------+----------+
    3 rows in set (0.00 sec)
    ```