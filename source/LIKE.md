# LIKE

- `LIKE` : 문자열 값과 패턴을 비교하여 일치하는 값을 찾는 연산자

  ```sql
  -- % is wild cards

  SELECT TITLE
  FROM BOOKS
  WHERE TITLE
  LIKE "the%";
  +-------------------------------------------+
  | title                                     |
  +-------------------------------------------+
  | The Namesake                              |
  | The Circle                                |
  | The Amazing Adventures of Kavalier & Clay |
  +-------------------------------------------+
  ```

  ```sql
  SELECT TITLE,
        CONCAT(AUTHOR_FIRST_NAME, ", ", AUTHOR_LAST_NAME) AS "AUTHOR"
  FROM BOOKS
  WHERE AUTHOR_FIRST_NAME
  LIKE "%da%";
  +-------------------------------------------+-----------------------+
  | TITLE                                     | AUTHOR                |
  +-------------------------------------------+-----------------------+
  | A Hologram for the King: A Novel          | Dave, Eggers          |
  | The Circle                                | Dave, Eggers          |
  | A Heartbreaking Work of Staggering Genius | Dave, Eggers          |
  | Oblivion: Stories                         | David, Foster Wallace |
  | Consider the Lobster                      | David, Foster Wallace |
  | 10% Happier                               | Dan, Harris           |
  | FAKE_BOOK                                 | Freida, Harris        |
  +-------------------------------------------+-----------------------+
  ```

  ```sql
  SELECT TITLE,
         CONCAT(AUTHOR_FIRST_NAME, ", ", AUTHOR_LAST_NAME) AS "AUTHOR"
  FROM BOOKS
  WHERE AUTHOR_FIRST_NAME
  LIKE "da%";
  +-------------------------------------------+-----------------------+
  | TITLE                                     | AUTHOR                |
  +-------------------------------------------+-----------------------+
  | A Hologram for the King: A Novel          | Dave, Eggers          |
  | The Circle                                | Dave, Eggers          |
  | A Heartbreaking Work of Staggering Genius | Dave, Eggers          |
  | Oblivion: Stories                         | David, Foster Wallace |
  | Consider the Lobster                      | David, Foster Wallace |
  | 10% Happier                               | Dan, Harris           |
  +-------------------------------------------+-----------------------+
  ```
