# LIKE

- `LIKE` : 문자열 값과 패턴을 비교하여 일치하는 값을 찾는 연산자

  ```sql
  -- % is wild cards

  mysql> SELECT title
      -> FROM books
      -> WHERE title
      -> LIKE "the%";
  +-------------------------------------------+
  | title                                     |
  +-------------------------------------------+
  | The Namesake                              |
  | The Circle                                |
  | The Amazing Adventures of Kavalier & Clay |
  +-------------------------------------------+
  3 rows in set (0.00 sec)
  ```

  ```sql
  mysql> SELECT title,
      ->        CONCAT(author_fname, ", ", author_lname) AS "author"
      -> FROM books
      -> WHERE author_fname
      -> LIKE "%da%";
  +-------------------------------------------+-----------------------+
  | title                                     | author                |
  +-------------------------------------------+-----------------------+
  | A Hologram for the King: A Novel          | Dave, Eggers          |
  | The Circle                                | Dave, Eggers          |
  | A Heartbreaking Work of Staggering Genius | Dave, Eggers          |
  | Oblivion: Stories                         | David, Foster Wallace |
  | Consider the Lobster                      | David, Foster Wallace |
  | 10% Happier                               | Dan, Harris           |
  | fake_book                                 | Freida, Harris        |
  +-------------------------------------------+-----------------------+
  7 rows in set (0.00 sec)
  ```

  ```sql
  mysql> SELECT title,
      ->        CONCAT(author_fname, ", ", author_lname) AS "author"
      -> FROM books
      -> WHERE author_fname
      -> LIKE "da%";
  +-------------------------------------------+-----------------------+
  | title                                     | author                |
  +-------------------------------------------+-----------------------+
  | A Hologram for the King: A Novel          | Dave, Eggers          |
  | The Circle                                | Dave, Eggers          |
  | A Heartbreaking Work of Staggering Genius | Dave, Eggers          |
  | Oblivion: Stories                         | David, Foster Wallace |
  | Consider the Lobster                      | David, Foster Wallace |
  | 10% Happier                               | Dan, Harris           |
  +-------------------------------------------+-----------------------+
  6 rows in set (0.00 sec)
  ```
