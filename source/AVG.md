# AVG

- `AVG` : 데이터의 평균값을 구하는 함수
    
    ```sql
    mysql> SELECT AVG(pages)
        -> FROM books;
    +------------+
    | AVG(pages) |
    +------------+
    |   348.5789 |
    +------------+
    1 row in set (0.00 sec)
    ```
    
    ```sql
    -- 저자에 따른 페이지 평균 구하기
    
    mysql> SELECT CONCAT(author_lname, " ", author_fname) AS "author",
        ->        AVG(pages) AS "average of pages"
        -> FROM books
        -> GROUP BY author_lname, author_fname;
    +----------------------+------------------+
    | author               | average of pages |
    +----------------------+------------------+
    | Lahiri Jhumpa        |         244.5000 |
    | Gaiman Neil          |         325.6667 |
    | Eggers Dave          |         431.0000 |
    | Chabon Michael       |         634.0000 |
    | Smith Patti          |         304.0000 |
    | Carver Raymond       |         351.0000 |
    | DeLillo Don          |         320.0000 |
    | Steinbeck John       |         181.0000 |
    | Foster Wallace David |         336.0000 |
    | Harris Dan           |         256.0000 |
    | Harris Freida        |         428.0000 |
    | Saunders George      |         367.0000 |
    +----------------------+------------------+
    12 rows in set (0.00 sec)
    ```
    
    ```sql
    mysql> SELECT released_year AS "year",
        ->        COUNT(title) AS "# books",
        ->        AVG(pages) AS "avg pages"
        -> FROM books
        -> GROUP BY released_year
        -> ORDER BY released_year;
    +------+---------+-----------+
    | year | # books | avg pages |
    +------+---------+-----------+
    | 1945 |       1 |  181.0000 |
    | 1981 |       1 |  176.0000 |
    | 1985 |       1 |  320.0000 |
    | 1989 |       1 |  526.0000 |
    | 1996 |       1 |  198.0000 |
    | 2000 |       1 |  634.0000 |
    | 2001 |       3 |  443.3333 |
    | 2003 |       2 |  249.5000 |
    | 2004 |       1 |  329.0000 |
    | 2005 |       1 |  343.0000 |
    | 2010 |       1 |  304.0000 |
    | 2012 |       1 |  352.0000 |
    | 2013 |       1 |  504.0000 |
    | 2014 |       1 |  256.0000 |
    | 2016 |       1 |  304.0000 |
    | 2017 |       1 |  367.0000 |
    +------+---------+-----------+
    16 rows in set (0.00 sec)
    ```