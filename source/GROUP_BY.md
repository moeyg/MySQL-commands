# GROUP BY

- `GROUP BY` : 동일한 데이터를 각각의 그룹으로 구성하는 함수
    
    ```sql
    -- AUTHOR_FIRST_NAME으로 그룹을 구성하고,
    -- AUTHOR_FIRST_NAME에 따라 몇 권의 책을 집필했는지 요약
    -- COUNT(*) : 각 그룹의 모든 ROW 개수
    
    SELECT AUTHOR_FIRST_NAME,
           COUNT(*) AS "NUMBER OF AUTHOR"
    FROM BOOKS
    GROUP BY AUTHOR_FIRST_NAME;
    +-------------------+-----------------+
    | AUTHOR_FIRST_NAME | NUMBER OF BOOKS |
    +-------------------+-----------------+
    | Jhumpa            |               2 |
    | Neil              |               3 |
    | Dave              |               3 |
    | Michael           |               1 |
    | Patti             |               1 |
    | Raymond           |               2 |
    | Don               |               1 |
    | John              |               1 |
    | David             |               2 |
    | Dan               |               1 |
    | Freida            |               1 |
    | George            |               1 |
    +-------------------+-----------------+
    ```
    
    ```sql
    -- 두 개의 조건에 부합하는 그룹 구성
    
    SELECT
    CONCAT(AUTHOR_FIRST_NAME, ", ", AUTHOR_LAST_NAME) AS "AUTHOR",
    COUNT(*) AS "NUMBER OF BOOKS"
    FROM BOOKS
    GROUP BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME;
    +-----------------------+-----------------+
    | AUTHOR                | NUMBER OF BOOKS |
    +-----------------------+-----------------+
    | Jhumpa, Lahiri        |               2 |
    | Neil, Gaiman          |               3 |
    | Dave, Eggers          |               3 |
    | Michael, Chabon       |               1 |
    | Patti, Smith          |               1 |
    | Raymond, Carver       |               2 |
    | Don, DeLillo          |               1 |
    | John, Steinbeck       |               1 |
    | David, Foster Wallace |               2 |
    | Dan, Harris           |               1 |
    | Freida, Harris        |               1 |
    | George, Saunders      |               1 |
    +-----------------------+-----------------+
    ```
    
    ```sql
    SELECT
    CONCAT("In ", RELEASED_YEAR, " ", COUNT(*), " book(s) released.")
    AS "How many books were published in what year?"
    FROM BOOKS
    GROUP BY RELEASED_YEAR;
    +---------------------------------------------+
    | How many books were published in what year? |
    +---------------------------------------------+
    | In 2003 2 book(s) released.                 |
    | In 2016 1 book(s) released.                 |
    | In 2001 3 book(s) released.                 |
    | In 1996 1 book(s) released.                 |
    | In 2012 1 book(s) released.                 |
    | In 2013 1 book(s) released.                 |
    | In 2000 1 book(s) released.                 |
    | In 2010 1 book(s) released.                 |
    | In 1981 1 book(s) released.                 |
    | In 1989 1 book(s) released.                 |
    | In 1985 1 book(s) released.                 |
    | In 1945 1 book(s) released.                 |
    | In 2004 1 book(s) released.                 |
    | In 2005 1 book(s) released.                 |
    | In 2014 1 book(s) released.                 |
    | In 2017 1 book(s) released.                 |
    +---------------------------------------------+
    ```
    
    ```sql
    -- RELEASED_YEAR로 그룹을 만들고, RELEASED_YEAR에 따라 정렬
    
    SELECT RELEASED_YEAR,
           COUNT(*) AS "NUMBER OF BOOKS"
    FROM BOOKS
    GROUP BY RELEASED_YEAR
    ORDER BY RELEASED_YEAR;
    +---------------+-----------------+
    | RELEASED_YEAR | NUMBER OF BOOKS |
    +---------------+-----------------+
    |          1945 |               1 |
    |          1981 |               1 |
    |          1985 |               1 |
    |          1989 |               1 |
    |          1996 |               1 |
    |          2000 |               1 |
    |          2001 |               3 |
    |          2003 |               2 |
    |          2004 |               1 |
    |          2005 |               1 |
    |          2010 |               1 |
    |          2012 |               1 |
    |          2013 |               1 |
    |          2014 |               1 |
    |          2016 |               1 |
    |          2017 |               1 |
    +---------------+-----------------+
    ```
