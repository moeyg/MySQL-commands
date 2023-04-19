# CONCAT

- `SOURCE` : 파일 불러오기
  ```sql
  SOURCE /Users/moeyg/Database/book_data.sql
  ```

<br>

- `CONCAT` : 문자열 연결 함수

  ```sql
  -- books DATA

  SELECT author_fname,
         author_lname
  FROM books;
  +--------------+----------------+
  | author_fname | author_lname   |
  +--------------+----------------+
  | Jhumpa       | Lahiri         |
  | Neil         | Gaiman         |
  | Neil         | Gaiman         |
  | Jhumpa       | Lahiri         |
  | Dave         | Eggers         |
  | Dave         | Eggers         |
  | Michael      | Chabon         |
  | Patti        | Smith          |
  | Dave         | Eggers         |
  | Neil         | Gaiman         |
  | Raymond      | Carver         |
  | Raymond      | Carver         |
  | Don          | DeLillo        |
  | John         | Steinbeck      |
  | David        | Foster Wallace |
  | David        | Foster Wallace |
  +--------------+----------------+
  ```

  ```sql
  -- Use CONCAT function

  SELECT CONCAT(author_fname, " ", author_lname)
  FROM books;
  +-----------------------------------------+
  | CONCAT(author_fname, " ", author_lname) |
  +-----------------------------------------+
  | Jhumpa Lahiri                           |
  | Neil Gaiman                             |
  | Neil Gaiman                             |
  | Jhumpa Lahiri                           |
  | Dave Eggers                             |
  | Dave Eggers                             |
  | Michael Chabon                          |
  | Patti Smith                             |
  | Dave Eggers                             |
  | Neil Gaiman                             |
  | Raymond Carver                          |
  | Raymond Carver                          |
  | Don DeLillo                             |
  | John Steinbeck                          |
  | David Foster Wallace                    |
  | David Foster Wallace                    |
  +-----------------------------------------+
  ```

<br>

- `CONCAT AS` : 문자열을 결합한 자료에 별칭 붙이기

  ```sql
  -- Use AS

  SELECT
  CONCAT(author_fname, " ", author_lname) AS "full name"
  FROM books;
  +----------------------+
  | full name            |
  +----------------------+
  | Jhumpa Lahiri        |
  | Neil Gaiman          |
  | Neil Gaiman          |
  | Jhumpa Lahiri        |
  | Dave Eggers          |
  | Dave Eggers          |
  | Michael Chabon       |
  | Patti Smith          |
  | Dave Eggers          |
  | Neil Gaiman          |
  | Raymond Carver       |
  | Raymond Carver       |
  | Don DeLillo          |
  | John Steinbeck       |
  | David Foster Wallace |
  | David Foster Wallace |
  +----------------------+
  ```

  <br>

- `CONCAT` Example
  ```sql
  SELECT author_fname AS "first name",
         author_lname AS "last name",
         CONCAT(author_fname, ", ", author_lname) AS "full name"
  FROM books;
  +------------+----------------+-----------------------+
  | first name | last name      | full name             |
  +------------+----------------+-----------------------+
  | Jhumpa     | Lahiri         | Jhumpa, Lahiri        |
  | Neil       | Gaiman         | Neil, Gaiman          |
  | Neil       | Gaiman         | Neil, Gaiman          |
  | Jhumpa     | Lahiri         | Jhumpa, Lahiri        |
  | Dave       | Eggers         | Dave, Eggers          |
  | Dave       | Eggers         | Dave, Eggers          |
  | Michael    | Chabon         | Michael, Chabon       |
  | Patti      | Smith          | Patti, Smith          |
  | Dave       | Eggers         | Dave, Eggers          |
  | Neil       | Gaiman         | Neil, Gaiman          |
  | Raymond    | Carver         | Raymond, Carver       |
  | Raymond    | Carver         | Raymond, Carver       |
  | Don        | DeLillo        | Don, DeLillo          |
  | John       | Steinbeck      | John, Steinbeck       |
  | David      | Foster Wallace | David, Foster Wallace |
  | David      | Foster Wallace | David, Foster Wallace |
  +------------+----------------+-----------------------+
  ```

<br>

- `CONCAT_WS` : 처음 인자를 구분자로 하여, 나머지 인자들을 결합
  ```sql
  SELECT CONCAT_WS(" - ", title, author_fname, author_lname)
         AS "title - author name"
  FROM books;
  +------------------------------------------------------------------------+
  | title - author name                                                    |
  +------------------------------------------------------------------------+
  | The Namesake - Jhumpa - Lahiri                                         |
  | Norse Mythology - Neil - Gaiman                                        |
  | American Gods - Neil - Gaiman                                          |
  | Interpreter of Maladies - Jhumpa - Lahiri                              |
  | A Hologram for the King: A Novel - Dave - Eggers                       |
  | The Circle - Dave - Eggers                                             |
  | The Amazing Adventures of Kavalier & Clay - Michael - Chabon           |
  | Just Kids - Patti - Smith                                              |
  | A Heartbreaking Work of Staggering Genius - Dave - Eggers              |
  | Coraline - Neil - Gaiman                                               |
  | What We Talk About When We Talk About Love: Stories - Raymond - Carver |
  | Where I'm Calling From: Selected Stories - Raymond - Carver            |
  | White Noise - Don - DeLillo                                            |
  | Cannery Row - John - Steinbeck                                         |
  | Oblivion: Stories - David - Foster Wallace                             |
  | Consider the Lobster - David - Foster Wallace                          |
  +------------------------------------------------------------------------+
  16 rows in set (0.00 sec)
  ```
