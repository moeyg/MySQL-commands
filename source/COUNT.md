# COUNT

- `COUNT(COLUMN)` : `COLUMN` 에 해당하는 `ROW` 의 개수를 읽어주는 함수
    
    ```sql
    SELECT COUNT(*)
    FROM BOOKS;
    +----------+
    | COUNT(*) |
    +----------+
    |       19 |
    +----------+
    ```
    
    ```sql
    SELECT
    COUNT(DISTINCT AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME) AS "NUMBER OF AUTHOR"
    FROM BOOKS;
    +------------------+
    | NUMBER OF AUTHOR |
    +------------------+
    |               12 |
    +------------------+
    ```
    
    ```sql
    SELECT
    COUNT(TITLE) AS "Number of books with 'the' in the title"
    FROM BOOKS
    WHERE TITLE
    LIKE "%the%";
    +-----------------------------------------+
    | Number of books with 'the' in the title |
    +-----------------------------------------+
    |                                       6 |
    +-----------------------------------------+
    ```
    
