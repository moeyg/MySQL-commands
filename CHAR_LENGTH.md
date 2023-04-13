# CHAR_LENGTH

- `CHAR_LENGTH` : 문자열의 길이 구하기
    
    ```bash
    mysql> SELECT CHAR_LENGTH("Hello, World!");
    +------------------------------+
    | CHAR_LENGTH("Hello, World!") |
    +------------------------------+
    |                           13 |
    +------------------------------+
    1 row in set (0.03 sec)
    ```
    
    ```bash
    mysql> SELECT
        -> author_lname,
        -> CHAR_LENGTH(author_lname)
        -> AS 'length'
        -> FROM books;
    +----------------+--------+
    | author_lname   | length |
    +----------------+--------+
    | Lahiri         |      6 |
    | Gaiman         |      6 |
    | Gaiman         |      6 |
    | Lahiri         |      6 |
    | Eggers         |      6 |
    | Eggers         |      6 |
    | Chabon         |      6 |
    | Smith          |      5 |
    | Eggers         |      6 |
    | Gaiman         |      6 |
    | Carver         |      6 |
    | Carver         |      6 |
    | DeLillo        |      7 |
    | Steinbeck      |      9 |
    | Foster Wallace |     14 |
    | Foster Wallace |     14 |
    +----------------+--------+
    16 rows in set (0.01 sec)
    ```
    

- `CONCAT` + `CHAR_LENGTH` Example
    
    ```bash
    mysql> SELECT
        -> CONCAT
        -> (author_fname, ' is ', CHAR_LENGTH(author_fname),' characters long')
        -> AS 'author'
        -> FROM books;
    +------------------------------+
    | author                       |
    +------------------------------+
    | Jhumpa is 6 characters long  |
    | Neil is 4 characters long    |
    | Neil is 4 characters long    |
    | Jhumpa is 6 characters long  |
    | Dave is 4 characters long    |
    | Dave is 4 characters long    |
    | Michael is 7 characters long |
    | Patti is 5 characters long   |
    | Dave is 4 characters long    |
    | Neil is 4 characters long    |
    | Raymond is 7 characters long |
    | Raymond is 7 characters long |
    | Don is 3 characters long     |
    | John is 4 characters long    |
    | David is 5 characters long   |
    | David is 5 characters long   |
    +------------------------------+
    16 rows in set (0.00 sec)
    ```