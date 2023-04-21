# AVG

- `AVG` : 데이터의 평균값을 구하는 함수
    
    ```sql
    SELECT AVG(PAGES)
    FROM BOOKS;
    +------------+
    | AVG(PAGES) |
    +------------+
    |   348.5789 |
    +------------+
    ```
    
    ```sql
    -- 저자에 따른 페이지 평균 구하기
    
    SELECT CONCAT(AUTHOR_FIRST_NAME, " ", AUTHOR_LAST_NAME) AS "AUTHOR",
           AVG(PAGES) AS "AVG OF PAGES"
    FROM BOOKS
    GROUP BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME
    ORDER BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME DESC;
    +----------------------+--------------+
    | AUTHOR               | AVG OF PAGES |
    +----------------------+--------------+
    | Dan Harris           |     256.0000 |
    | Dave Eggers          |     431.0000 |
    | David Foster Wallace |     336.0000 |
    | Don DeLillo          |     320.0000 |
    | Freida Harris        |     428.0000 |
    | George Saunders      |     367.0000 |
    | Jhumpa Lahiri        |     244.5000 |
    | John Steinbeck       |     181.0000 |
    | Michael Chabon       |     634.0000 |
    | Neil Gaiman          |     325.6667 |
    | Patti Smith          |     304.0000 |
    | Raymond Carver       |     351.0000 |
    +----------------------+--------------+
    ```
    
    ```sql
    SELECT RELEASED_YEAR AS "YEAR",
           COUNT(*) AS "# BOOKS",
           AVG(PAGES) AS "AVG OF PAGES"
    FROM BOOKS
    GROUP BY RELEASED_YEAR
    ORDER BY RELEASED_YEAR;
    +------+---------+--------------+
    | YEAR | # BOOKS | AVG OF PAGES |
    +------+---------+--------------+
    | 1945 |       1 |     181.0000 |
    | 1981 |       1 |     176.0000 |
    | 1985 |       1 |     320.0000 |
    | 1989 |       1 |     526.0000 |
    | 1996 |       1 |     198.0000 |
    | 2000 |       1 |     634.0000 |
    | 2001 |       3 |     443.3333 |
    | 2003 |       2 |     249.5000 |
    | 2004 |       1 |     329.0000 |
    | 2005 |       1 |     343.0000 |
    | 2010 |       1 |     304.0000 |
    | 2012 |       1 |     352.0000 |
    | 2013 |       1 |     504.0000 |
    | 2014 |       1 |     256.0000 |
    | 2016 |       1 |     304.0000 |
    | 2017 |       1 |     367.0000 |
    +------+---------+--------------+
    ```
    
