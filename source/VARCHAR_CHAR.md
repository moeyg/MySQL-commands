# VARCHAR & CHAR

### `VARCHAR`

- 가변 길이 문자열 데이터를 저장하는 데이터 타입으로, 필요한 만큼의 공간만 차지하며 실제 문자열 데이터의 길이에 따라 저장 공간이 동적으로 조정된다.<br>
- `VARCHAR`는 최대 길이를 지정할 수 있으며, 최대 길이를 초과하는 문자열은 잘려서 저장된다.<br>
- `VARCHAR`의 장점은 저장 공간을 효율적으로 사용한다는 것이지만, 데이터의 길이가 변하는 경우 데이터를 저장할 때마다 길이를 확인하고 조정하는 작업이 필요하다.
- 최소 0에서 최대 255자까지 저장할 수 있다.<br>

### `CHAR`

- 고정 길이의 문자열 데이터를 저장하는 데이터 타입으로, 지정한 길이만큼의 고정된 공간을 차지하게 된다.<br>
- `CHAR`는 지정한 길이보다 짧은 문자열을 저장할 경우 남은 공간을 공백 문자로 채워야 한다.<br>
- `CHAR`의 장점은 데이터의 길이가 고정되어 있어 데이터 저장 및 검색 속도가 빠르다. 그러나 저장 공간을 낭비할 수 있다.<br>

### `VARCHAR` & `CHAR`

| VALUE          | CHAR(4)           | STORAGE | VARCHAR        | STORAGE |
| -------------- | ----------------- | ------- | -------------- | ------- |
| “ “ (공백 1개) | “　 “ (+공백 3개) | 4 bytes | “ “ (공백 1개) | 1 bytes |
| “ab”           | “ab “ (+공백 2개) | 4 bytes | “ab”           | 3 bytes |
| “abcd”         | “abcd”            | 4 bytes | “abcd”         | 5 bytes |
| “abcdefg”      | “abcd”            | 4 bytes | “abcdefg”      | 5 bytes |

```sql
-- CREATE TABLE

mysql> CREATE TABLE tree
    -> (
    ->     name CHAR(10),
    ->     species VARCHAR(25)
    -> );
Query OK, 0 rows affected (0.01 sec)

-- INSERT Datas

mysql> INSERT INTO tree (name, species)
    -> VALUES ("Pine", "needleleaf"),
    ->        ("Gingko", "broad-leaved"),
    ->        ("Zelkova", "broad-leaved"),
    ->        ("Cypress", "needleleaf");
Query OK, 4 rows affected (0.01 sec)
Records: 4  Duplicates: 0  Warnings: 0

-- Result

mysql> SELECT * FROM tree;
+---------+--------------+
| name    | species      |
+---------+--------------+
| Pine    | needleleaf   |
| Gingko  | broad-leaved |
| Zelkova | broad-leaved |
| Cypress | needleleaf   |
+---------+--------------+
4 rows in set (0.01 sec)

-- name은 CHAR 이므로, 10자를 채우지 못 한 공간은 공백으로 채운다.
-- species는 VARCHAR 이므로, 25자 내에서 자유롭게 공간을 채운다.
```
