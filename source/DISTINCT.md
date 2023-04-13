# DISTINCT

- `DISTINCT` : 중복 문자열 제거 연산자

  ```sql
  -- NOT USE DISTINCT

  mysql> SELECT author_lname
      -> FROM books;
  +----------------+
  | author_lname   |
  +----------------+
  | Lahiri         |
  | Gaiman         |
  | Gaiman         |
  | Lahiri         |
  | Eggers         |
  | Eggers         |
  | Chabon         |
  | Smith          |
  | Eggers         |
  | Gaiman         |
  | Carver         |
  | Carver         |
  | DeLillo        |
  | Steinbeck      |
  | Foster Wallace |
  | Foster Wallace |
  | Harris         |
  | Harris         |
  | Saunders       |
  +----------------+
  19 rows in set (0.00 sec)
  ```

  ```sql
  -- USE DISTINCT

  mysql> SELECT
      -> DISTINCT author_lname
      -> FROM books;
  +----------------+
  | author_lname   |
  +----------------+
  | Lahiri         |
  | Gaiman         |
  | Eggers         |
  | Chabon         |
  | Smith          |
  | Carver         |
  | DeLillo        |
  | Steinbeck      |
  | Foster Wallace |
  | Harris         |
  | Saunders       |
  +----------------+
  11 rows in set (0.01 sec)
  ```

<br>

- `DISTINCT`

  ```sql
  mysql> SELECT
      -> DISTINCT
      -> author_lname, author_fname
      -> FROM books;
  +----------------+--------------+
  | author_lname   | author_fname |
  +----------------+--------------+
  | Lahiri         | Jhumpa       |
  | Gaiman         | Neil         |
  | Eggers         | Dave         |
  | Chabon         | Michael      |
  | Smith          | Patti        |
  | Carver         | Raymond      |
  | DeLillo        | Don          |
  | Steinbeck      | John         |
  | Foster Wallace | David        |
  | Harris         | Dan          |
  | Harris         | Freida       |
  | Saunders       | George       |
  +----------------+--------------+
  12 rows in set (0.00 sec)
  ```

<br>

- `DISTINCT` + `CONCAT`
  ```sql
  mysql> SELECT
      -> DISTINCT
      -> CONCAT(author_lname, " ", author_fname)
      -> AS author
      -> FROM books;
  +----------------------+
  | author               |
  +----------------------+
  | Lahiri Jhumpa        |
  | Gaiman Neil          |
  | Eggers Dave          |
  | Chabon Michael       |
  | Smith Patti          |
  | Carver Raymond       |
  | DeLillo Don          |
  | Steinbeck John       |
  | Foster Wallace David |
  | Harris Dan           |
  | Harris Freida        |
  | Saunders George      |
  +----------------------+
  12 rows in set (0.00 sec)
  ```
