# DISTINCT

- `DISTINCT` : 중복 문자열 제거 연산자

  ```sql
  -- NOT USE DISTINCT

  SELECT AUTHOR_FIRST_NAME
  FROM BOOKS;
  +-------------------+
  | AUTHOR_FIRST_NAME |
  +-------------------+
  | Jhumpa            |
  | Neil              |
  | Neil              |
  | Jhumpa            |
  | Dave              |
  | Dave              |
  | Michael           |
  | Patti             |
  | Dave              |
  | Neil              |
  | Raymond           |
  | Raymond           |
  | Don               |
  | John              |
  | David             |
  | David             |
  | Dan               |
  | Freida            |
  | George            |
  +-------------------+
  ```

  ```sql
  -- USE DISTINCT

  SELECT
  DISTINCT AUTHOR_FIRST_NAME
  FROM BOOKS;
  +-------------------+
  | AUTHOR_FIRST_NAME |
  +-------------------+
  | Jhumpa            |
  | Neil              |
  | Dave              |
  | Michael           |
  | Patti             |
  | Raymond           |
  | Don               |
  | John              |
  | David             |
  | Dan               |
  | Freida            |
  | George            |
  +-------------------+
  ```

<br>

- `DISTINCT`

  ```sql
  SELECT
  DISTINCT AUTHOR_FIRST_NAME,
           AUTHOR_LAST_NAME
  FROM BOOKS;
  +-------------------+------------------+
  | AUTHOR_FIRST_NAME | AUTHOR_LAST_NAME |
  +-------------------+------------------+
  | Jhumpa            | Lahiri           |
  | Neil              | Gaiman           |
  | Dave              | Eggers           |
  | Michael           | Chabon           |
  | Patti             | Smith            |
  | Raymond           | Carver           |
  | Don               | DeLillo          |
  | John              | Steinbeck        |
  | David             | Foster Wallace   |
  | Dan               | Harris           |
  | Freida            | Harris           |
  | George            | Saunders         |
  +-------------------+------------------+
  ```

<br>

- `DISTINCT` + `CONCAT`
  ```sql
  SELECT
  DISTINCT CONCAT(AUTHOR_FIRST_NAME, " ", AUTHOR_LAST_NAME) AS "AUTHOR"
  FROM BOOKS;
  +----------------------+
  | AUTHOR               |
  +----------------------+
  | Jhumpa Lahiri        |
  | Neil Gaiman          |
  | Dave Eggers          |
  | Michael Chabon       |
  | Patti Smith          |
  | Raymond Carver       |
  | Don DeLillo          |
  | John Steinbeck       |
  | David Foster Wallace |
  | Dan Harris           |
  | Freida Harris        |
  | George Saunders      |
  +----------------------+
  ```
