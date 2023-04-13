# SUM

- `SUM` : 데이터의 합계를 구하는 함수
    
    ```sql
    mysql> SELECT SUM(pages)
        -> FROM books;
    +------------+
    | SUM(pages) |
    +------------+
    |       6623 |
    +------------+
    1 row in set (0.01 sec)
    ```
    
    ```sql
    mysql> SELECT CONCAT(author_lname, " ", author_fname) AS "author",
        ->        SUM(pages) AS "All pages"
        -> FROM books
        -> GROUP BY author_lname,
        ->          author_fname;
    +----------------------+-----------+
    | author               | All pages |
    +----------------------+-----------+
    | Lahiri Jhumpa        |       489 |
    | Gaiman Neil          |       977 |
    | Eggers Dave          |      1293 |
    | Chabon Michael       |       634 |
    | Smith Patti          |       304 |
    | Carver Raymond       |       702 |
    | DeLillo Don          |       320 |
    | Steinbeck John       |       181 |
    | Foster Wallace David |       672 |
    | Harris Dan           |       256 |
    | Harris Freida        |       428 |
    | Saunders George      |       367 |
    +----------------------+-----------+
    12 rows in set (0.00 sec)
    ```