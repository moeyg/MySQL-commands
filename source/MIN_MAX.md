# MIN & MAX

- `MIN`
    
    ```sql
    mysql> SELECT MIN(pages)
        -> FROM books;
    +------------+
    | MIN(pages) |
    +------------+
    |        176 |
    +------------+
    1 row in set (0.00 sec)
    ```
    

- `MAX`
    
    ```sql
    mysql> SELECT MAX(pages)
        -> FROM books;
    +------------+
    | MAX(pages) |
    +------------+
    |        634 |
    +------------+
    1 row in set (0.00 sec)
    ```
    

- `GROUP BY` + `MIN`
    
    ```sql
    -- 저자가 최초로 책을 출간한 년도를 그룹화
    
    mysql> SELECT CONCAT(author_lname, " ", author_fname) AS "author",
        ->        MIN(released_year) AS "Year of first publication"
        -> FROM books
        -> GROUP BY author_lname, author_fname;
    +----------------------+---------------------------+
    | author               | Year of first publication |
    +----------------------+---------------------------+
    | Lahiri Jhumpa        |                      1996 |
    | Gaiman Neil          |                      2001 |
    | Eggers Dave          |                      2001 |
    | Chabon Michael       |                      2000 |
    | Smith Patti          |                      2010 |
    | Carver Raymond       |                      1981 |
    | DeLillo Don          |                      1985 |
    | Steinbeck John       |                      1945 |
    | Foster Wallace David |                      2004 |
    | Harris Dan           |                      2014 |
    | Harris Freida        |                      2001 |
    | Saunders George      |                      2017 |
    +----------------------+---------------------------+
    12 rows in set (0.00 sec)
    ```
    
- `GROUP BY` + `MAX`
    
    ```sql
    -- 저자가 최근에 책을 출간한 년도를 그룹화
    
    mysql> SELECT CONCAT(author_lname, " ", author_fname) AS "author",
        ->        MAX(released_year) AS "Year of last publication"
        -> FROM books
        -> GROUP BY author_lname, author_fname;
    +----------------------+--------------------------+
    | author               | Year of last publication |
    +----------------------+--------------------------+
    | Lahiri Jhumpa        |                     2003 |
    | Gaiman Neil          |                     2016 |
    | Eggers Dave          |                     2013 |
    | Chabon Michael       |                     2000 |
    | Smith Patti          |                     2010 |
    | Carver Raymond       |                     1989 |
    | DeLillo Don          |                     1985 |
    | Steinbeck John       |                     1945 |
    | Foster Wallace David |                     2005 |
    | Harris Dan           |                     2014 |
    | Harris Freida        |                     2001 |
    | Saunders George      |                     2017 |
    +----------------------+--------------------------+
    12 rows in set (0.00 sec)
    ```