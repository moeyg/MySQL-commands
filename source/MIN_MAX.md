# MIN & MAX

- `MIN`
    
    ```sql
    SELECT
    MIN(PAGES) AS "MINIMUN PAGES"
    FROM BOOKS;
    +---------------+
    | MINIMUN PAGES |
    +---------------+
    |           176 |
    +---------------+
    ```
    

- `MAX`
    
    ```sql
    SELECT
    MAX(PAGES) AS "MAXIMUN PAGES"
    FROM BOOKS;
    +---------------+
    | MAXIMUN PAGES |
    +---------------+
    |           634 |
    +---------------+
    ```
    

- `GROUP BY` + `MIN`
    
    ```sql
    -- 저자가 최초로 책을 출간한 년도를 그룹화
    
    SELECT CONCAT(AUTHOR_FIRST_NAME, " ", AUTHOR_LAST_NAME) AS "AUTHOR",
           MIN(RELEASED_YEAR) AS "FIRST PUBLICATION"
    FROM BOOKS
    GROUP BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME;
    +----------------------+-------------------+
    | AUTHOR               | FIRST PUBLICATION |
    +----------------------+-------------------+
    | Jhumpa Lahiri        |              1996 |
    | Neil Gaiman          |              2001 |
    | Dave Eggers          |              2001 |
    | Michael Chabon       |              2000 |
    | Patti Smith          |              2010 |
    | Raymond Carver       |              1981 |
    | Don DeLillo          |              1985 |
    | John Steinbeck       |              1945 |
    | David Foster Wallace |              2004 |
    | Dan Harris           |              2014 |
    | Freida Harris        |              2001 |
    | George Saunders      |              2017 |
    +----------------------+-------------------+
    ```
    
- `GROUP BY` + `MAX`
    
    ```sql
    -- 저자가 최근에 책을 출간한 년도를 그룹화
    
    SELECT CONCAT(AUTHOR_FIRST_NAME, " ", AUTHOR_LAST_NAME) AS "AUTHOR",
           MAX(RELEASED_YEAR) AS "LAST PUBLICATION"
    FROM BOOKS
    GROUP BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME;
    +----------------------+------------------+
    | AUTHOR               | LAST PUBLICATION |
    +----------------------+------------------+
    | Jhumpa Lahiri        |             2003 |
    | Neil Gaiman          |             2016 |
    | Dave Eggers          |             2013 |
    | Michael Chabon       |             2000 |
    | Patti Smith          |             2010 |
    | Raymond Carver       |             1989 |
    | Don DeLillo          |             1985 |
    | John Steinbeck       |             1945 |
    | David Foster Wallace |             2005 |
    | Dan Harris           |             2014 |
    | Freida Harris        |             2001 |
    | George Saunders      |             2017 |
    +----------------------+------------------+
    ```
