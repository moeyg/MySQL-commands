# GROUP BY

- `GROUP BY` : 동일한 데이터를 각각의 그룹으로 구성하는 함수
    
    ```sql
    -- author_lname으로 그룹을 구성하고,
    -- author_lname에 따라 몇 권의 책을 집필했는지 요약
    -- COUNT(*) : 각 그룹의 모든 ROW
    
    mysql> SELECT author_lname,
        ->        COUNT(*)
        -> FROM books
        -> GROUP BY author_lname;
    +----------------+--------------+
    | author_lname   | COUNT(title) |
    +----------------+--------------+
    | Lahiri         |            2 |
    | Gaiman         |            3 |
    | Eggers         |            3 |
    | Chabon         |            1 |
    | Smith          |            1 |
    | Carver         |            2 |
    | DeLillo        |            1 |
    | Steinbeck      |            1 |
    | Foster Wallace |            2 |
    | Harris         |            2 |
    | Saunders       |            1 |
    +----------------+--------------+
    11 rows in set (0.00 sec)
    ```
    
    ```sql
    -- 두 개의 조건에 부합하는 그룹 구성
    
    mysql> SELECT CONCAT(author_lname, " ", author_fname) AS "author",
        ->        COUNT(*) AS "books"
        -> FROM books
        -> GROUP BY author_lname,
        ->          author_fname;
    +----------------------+-------+
    | author               | books |
    +----------------------+-------+
    | Lahiri Jhumpa        |     2 |
    | Gaiman Neil          |     3 |
    | Eggers Dave          |     3 |
    | Chabon Michael       |     1 |
    | Smith Patti          |     1 |
    | Carver Raymond       |     2 |
    | DeLillo Don          |     1 |
    | Steinbeck John       |     1 |
    | Foster Wallace David |     2 |
    | Harris Dan           |     1 |
    | Harris Freida        |     1 |
    | Saunders George      |     1 |
    +----------------------+-------+
    12 rows in set (0.00 sec)
    ```
    
    ```sql
    mysql> SELECT CONCAT("In ", released_year, " ", COUNT(*), " book(s) released")
        ->        AS "How many books were published in what year?"
        -> FROM books
        -> GROUP BY released_year;
    +---------------------------------------------+
    | How many books were published in what year? |
    +---------------------------------------------+
    | In 2003 2 book(s) released                  |
    | In 2016 1 book(s) released                  |
    | In 2001 3 book(s) released                  |
    | In 1996 1 book(s) released                  |
    | In 2012 1 book(s) released                  |
    | In 2013 1 book(s) released                  |
    | In 2000 1 book(s) released                  |
    | In 2010 1 book(s) released                  |
    | In 1981 1 book(s) released                  |
    | In 1989 1 book(s) released                  |
    | In 1985 1 book(s) released                  |
    | In 1945 1 book(s) released                  |
    | In 2004 1 book(s) released                  |
    | In 2005 1 book(s) released                  |
    | In 2014 1 book(s) released                  |
    | In 2017 1 book(s) released                  |
    +---------------------------------------------+
    16 rows in set (0.00 sec)
    ```
    
    ```sql
    mysql> SELECT released_year,
                  COUNT(*)
        -> FROM books
        -> GROUP BY released_year
        -> ORDER BY released_year;
    +---------------+----------+
    | released_year | COUNT(*) |
    +---------------+----------+
    |          1945 |        1 |
    |          1981 |        1 |
    |          1985 |        1 |
    |          1989 |        1 |
    |          1996 |        1 |
    |          2000 |        1 |
    |          2001 |        3 |
    |          2003 |        2 |
    |          2004 |        1 |
    |          2005 |        1 |
    |          2010 |        1 |
    |          2012 |        1 |
    |          2013 |        1 |
    |          2014 |        1 |
    |          2016 |        1 |
    |          2017 |        1 |
    +---------------+----------+
    16 rows in set (0.00 sec)
    ```