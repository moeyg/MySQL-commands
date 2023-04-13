# SUBSTRING

- `SUBSTRING` : 문자열을 인덱스에 따라 자르기
  ```sql
  -- Two index

  mysql> SELECT SUBSTRING('Hello, World!', 1, 6);
  +----------------------------------+
  | SUBSTRING('Hello, World!', 1, 6) |
  +----------------------------------+
  | Hello,                           |
  +----------------------------------+
  1 row in set (0.00 sec)

  -- One index

  mysql> SELECT SUBSTRING('Hello, World!', 7);
  +-------------------------------+
  | SUBSTRING('Hello, World!', 7) |
  +-------------------------------+
  |  World!                       |
  +-------------------------------+
  1 row in set (0.00 sec)

  -- Negative index

  mysql> SELECT SUBSTRING('Hello, World!', -5);
  +--------------------------------+
  | SUBSTRING('Hello, World!', -5) |
  +--------------------------------+
  | orld!                          |
  +--------------------------------+
  1 row in set (0.00 sec)
  ```
  ```sql
  mysql> SELECT
      -> SUBSTRING(title, 1, 10)
      -> FROM books;
  +-------------------------+
  | SUBSTRING(title, 1, 10) |
  +-------------------------+
  | The Namesa              |
  | Norse Myth              |
  | American G              |
  | Interprete              |
  | A Hologram              |
  | The Circle              |
  | The Amazin              |
  | Just Kids               |
  | A Heartbre              |
  | Coraline                |
  | What We Ta              |
  | Where I'm               |
  | White Nois              |
  | Cannery Ro              |
  | Oblivion:               |
  | Consider t              |
  +-------------------------+
  16 rows in set (0.00 sec)
  ```
  ```sql
  -- Use AS

  mysql> SELECT
      -> SUBSTRING(title, 1, 10)
      -> AS 'short title'
      -> FROM books;
  +-------------+
  | short title |
  +-------------+
  | The Namesa  |
  | Norse Myth  |
  | American G  |
  | Interprete  |
  | A Hologram  |
  | The Circle  |
  | The Amazin  |
  | Just Kids   |
  | A Heartbre  |
  | Coraline    |
  | What We Ta  |
  | Where I'm   |
  | White Nois  |
  | Cannery Ro  |
  | Oblivion:   |
  | Consider t  |
  +-------------+
  16 rows in set (0.00 sec)
  ```

<br>

- `CONCAT` + `SUBSTRING` Example
  ```sql
  mysql> SELECT
      -> CONCAT
      -> (SUBSTRING(title, 1, 10), ' ...')
      -> AS 'short title'
      -> FROM books;
  +----------------+
  | short title    |
  +----------------+
  | The Namesa ... |
  | Norse Myth ... |
  | American G ... |
  | Interprete ... |
  | A Hologram ... |
  | The Circle ... |
  | The Amazin ... |
  | Just Kids ...  |
  | A Heartbre ... |
  | Coraline ...   |
  | What We Ta ... |
  | Where I'm  ... |
  | White Nois ... |
  | Cannery Ro ... |
  | Oblivion:  ... |
  | Consider t ... |
  +----------------+
  16 rows in set (0.00 sec)
  ```
