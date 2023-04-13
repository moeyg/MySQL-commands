# LIMIT

- `LIMIT` : 검색된 데이터의 행 수를 제한하는 연산자
  ```sql
  mysql> SELECT title
      -> FROM books
      -> LIMIT 5;
  +----------------------------------+
  | title                            |
  +----------------------------------+
  | The Namesake                     |
  | Norse Mythology                  |
  | American Gods                    |
  | Interpreter of Maladies          |
  | A Hologram for the King: A Novel |
  +----------------------------------+
  5 rows in set (0.00 sec)
  ```

<br>

- `LIMIT row1, row2` : row1 부터 row2 까지 조회

  ```sql
  -- LIMIT에서 첫 번째 row는 0부터 시작한다.

  mysql> SELECT title,
      ->        released_year
      -> FROM books
      -> ORDER BY released_year DESC
      -> LIMIT 0, 5;
  +----------------------------------+---------------+
  | title                            | released_year |
  +----------------------------------+---------------+
  | Lincoln In The Bardo             |          2017 |
  | Norse Mythology                  |          2016 |
  | 10% Happier                      |          2014 |
  | The Circle                       |          2013 |
  | A Hologram for the King: A Novel |          2012 |
  +----------------------------------+---------------+
  5 rows in set (0.00 sec)
  ```

  ```sql
  -- 따라서 LIMIT 1, 3은 두 번째 행부터 네 번째 행까지 조회한다.

  mysql> SELECT title,
      ->        released_year
      -> FROM books
      -> ORDER BY released_year DESC
      -> LIMIT 1, 3;
  +-----------------+---------------+
  | title           | released_year |
  +-----------------+---------------+
  | Norse Mythology |          2016 |
  | 10% Happier     |          2014 |
  | The Circle      |          2013 |
  +-----------------+---------------+
  3 rows in set (0.00 sec)
  ```
