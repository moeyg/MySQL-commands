# LIMIT

- `LIMIT` : 검색된 데이터의 행 수를 제한하는 연산자
  ```sql
  SELECT BOOK_ID, TITLE
  FROM BOOKS
  LIMIT 5;
  +---------+----------------------------------+
  | BOOK_ID | TITLE                            |
  +---------+----------------------------------+
  |       1 | The Namesake                     |
  |       2 | Norse Mythology                  |
  |       3 | American Gods                    |
  |       4 | Interpreter of Maladies          |
  |       5 | A Hologram for the King: A Novel |
  +---------+----------------------------------+
  ```

<br>

- `LIMIT row1, row2` : row1 부터 row2 까지 조회 (LIMIT에서 첫 번째 row는 0부터 시작한다.)

  ```sql
  -- 가장 최근에 출간한 책 5권을 정렬

  SELECT TITLE, RELEASED_YEAR
  FROM BOOKS
  ORDER BY RELASED_YEAR 
  LIMIT 0, 5;
  +----------------------------------+---------------+
  | TITLE                            | RELEASED_YEAR |
  +----------------------------------+---------------+
  | Lincoln In The Bardo             |          2017 |
  | Norse Mythology                  |          2016 |
  | 10% Happier                      |          2014 |
  | The Circle                       |          2013 |
  | A Hologram for the King: A Novel |          2012 |
  +----------------------------------+---------------+
  ```

  ```sql
  -- 따라서 LIMIT 1, 3은 두 번째 행부터 네 번째 행까지 조회한다.

  SELECT TITLE, RELEASED_YEAR
  FROM BOOKS
  ORDER BY RELEASED_YEAR DESC
  LIMIT 1, 3;
  +-----------------+---------------+
  | TITLE           | RELEASED_YEAR |
  +-----------------+---------------+
  | Norse Mythology |          2016 |
  | 10% Happier     |          2014 |
  | The Circle      |          2013 |
  +-----------------+---------------+
  ```
