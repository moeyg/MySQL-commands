# SUM

- `SUM` : 데이터의 합계를 구하는 함수
    
    ```sql
    SELECT
    SUM(PAGES) AS "SUM OF PAGES"
    FROM BOOKS;
    +--------------+
    | SUM OF PAGES |
    +--------------+
    |         6623 |
    +--------------+
    ```
    
    ```sql
    SELECT CONCAT(AUTHOR_FIRST_NAME, " ", AUTHOR_LAST_NAME) AS "AUTHOR",
           SUM(PAGES) AS "SUM OF PAGES"
    FROM BOOKS
    GROUP BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME;
    +----------------------+--------------+
    | AUTHOR               | SUM OF PAGES |
    +----------------------+--------------+
    | Jhumpa Lahiri        |          489 |
    | Neil Gaiman          |          977 |
    | Dave Eggers          |         1293 |
    | Michael Chabon       |          634 |
    | Patti Smith          |          304 |
    | Raymond Carver       |          702 |
    | Don DeLillo          |          320 |
    | John Steinbeck       |          181 |
    | David Foster Wallace |          672 |
    | Dan Harris           |          256 |
    | Freida Harris        |          428 |
    | George Saunders      |          367 |
    +----------------------+--------------+
    ```
    
