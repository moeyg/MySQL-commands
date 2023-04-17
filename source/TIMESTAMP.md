# TIMESTAMP

- 날짜와 시간 정보를 저장하는 데이터 타입 중 하나로, 특정 시점의 날짜와 시간을 나타낸다.<br>
- `YYYY-MM-DD HH:MM:SS` 형식으로 날짜와 시간 저장<br>
- MySQL 서버의 시간대를 기준으로 저장<br>
- 4바이트 혹은 8바이트로 저장<br>
- '1970-01-01 00:00:00'부터 '2038-01-19 03:14:07'까지의 범위를 지원<br>
- 자동으로 업데이트 되는 기능을 가지고 있어, 데이터가 삽입되거나 수정될 때 자동으로 현재 날짜와 시간으로 갱신될 수 있다.<br>

  ```sql
  -- CREATE TABLE

  mysql> CREATE TABLE comments
      -> (
      ->     content VARCHAR(100),
      ->     created_at TIMESTAMP DEFAULT NOW()
      -> );
  Query OK, 0 rows affected (0.00 sec)

  -- INSERT datas

  mysql> INSERT INTO comments (content) VALUES ("Hello, World!");
  Query OK, 1 row affected (0.01 sec)

  mysql> INSERT INTO comments (content) VALUES ("Hello, MySQL!");
  Query OK, 1 row affected (0.00 sec)

  mysql> INSERT INTO comments (content) VALUES ("Hello, DATABASE!");
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM comments ORDER BY created_at DESC;
  +------------------+---------------------+
  | content          | created_at          |
  +------------------+---------------------+
  | Hello, DATABASE! | 2023-04-14 22:23:21 |
  | Hello, MySQL!    | 2023-04-14 22:23:11 |
  | Hello, World!    | 2023-04-14 22:22:55 |
  +------------------+---------------------+
  3 rows in set (0.00 sec)
  ```

<br>

- `ON UPDATE CURRENT_TIMESTAMP` : 해당 COLUMN이 업데이트될 때 자동으로 현재 날짜와 시간(`CURRENT_TIMESTAMP`)로 갱신되도록 설정한다.

  ```sql
  -- CREATE TABLE

  mysql> CREATE TABLE comments
      -> (
      ->      content VARCHAR(100),
      ->      updated_at TIMESTAMP DEFAULT NOW() ON UPDATE CURRENT_TIMESTAMP
      -> );
  Query OK, 0 rows affected (0.02 sec)

  -- INSERT datas

  mysql> INSERT INTO comments (content) VALUES ("Hello, World!");
  Query OK, 1 row affected (0.01 sec)

  mysql> INSERT INTO comments (content) VALUES ("Hello, MySQL!");
  Query OK, 1 row affected (0.00 sec)

  mysql> INSERT INTO comments (content) VALUES ("Hello, DATABASE!");
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM comments;
  +------------------+---------------------+
  | content          | updated_at          |
  +------------------+---------------------+
  | Hello, World!    | 2023-04-14 22:46:51 |
  | Hello, MySQL!    | 2023-04-14 22:47:07 |
  | Hello, DATABASE! | 2023-04-14 22:47:16 |
  +------------------+---------------------+
  3 rows in set (0.00 sec)
  ```

  ```sql
  -- Update content

  mysql> UPDATE comments
      -> SET content="Hello, DATABASE :)"
      -> WHERE content="Hello, DATABASE!";
  Query OK, 1 row affected (0.00 sec)
  Rows matched: 1  Changed: 1  Warnings: 0

  mysql> UPDATE comments
      -> SET content="Hello, World :)"
      -> WHERE content="Hello, World!";
  Query OK, 0 rows affected (0.00 sec)
  Rows matched: 1  Changed: 0  Warnings: 0

  mysql> UPDATE comments
      -> SET content="Hello, MySQL :)"
      -> WHERE content="Hello, MySQL!";
  Query OK, 1 row affected (0.00 sec)
  Rows matched: 1  Changed: 1  Warnings: 0

  -- Result

  mysql> SELECT * FROM comments ORDER BY updated_at DESC;
  +--------------------+---------------------+
  | content            | updated_at          |
  +--------------------+---------------------+
  | Hello, MySQL :)    | 2023-04-14 22:53:20 |  -- 내용이 업데이트된 시간이 반영
  | Hello, DATABASE :) | 2023-04-14 22:51:21 |
  | Hello, World :)    | 2023-04-14 22:47:48 |
  +--------------------+---------------------+
  3 rows in set (0.00 sec)
  ```
