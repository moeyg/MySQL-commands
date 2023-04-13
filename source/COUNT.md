# COUNT

- `COUNT(COLUMN)` : `COLUMN` 에 해당하는 `ROW` 의 개수를 읽어주는 함수
    
    ```sql
    mysql> SELECT COUNT(*)
        -> FROM books;
    +----------+
    | COUNT(*) |
    +----------+
    |       19 |
    +----------+
    1 row in set (0.01 sec)
    ```
    
    ```sql
    mysql> SELECT COUNT(DISTINCT author_fname, author_lname)
        ->        AS "COUNT(author name)"
        -> FROM books;
    +--------------------+
    | COUNT(author name) |
    +--------------------+
    |                 12 |
    +--------------------+
    1 row in set (0.01 sec)
    ```
    
    ```sql
    mysql> SELECT COUNT(title)
        -> FROM books
        -> WHERE title
        -> LIKE "%the%";
    +--------------+
    | COUNT(title) |
    +--------------+
    |            6 |
    +--------------+
    1 row in set (0.00 sec)
    
    -- Double Check
    
    mysql> SELECT title
        -> FROM books
        -> WHERE title
        -> LIKE "%the%";
    +-------------------------------------------+
    | title                                     |
    +-------------------------------------------+
    | The Namesake                              |
    | A Hologram for the King: A Novel          |
    | The Circle                                |
    | The Amazing Adventures of Kavalier & Clay |
    | Consider the Lobster                      |
    | Lincoln In The Bardo                      |
    +-------------------------------------------+
    6 rows in set (0.00 sec)
    ```