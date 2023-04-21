# NUMBERS

### `INT`

- 부호 있는 32비트 정수를 나타내는 데이터 타입
- -2,147,483,648 ~ 2,147,483,647

<br>

### `DECIMAL(M, D)`

- 고정 소수점 숫자를 나타내는 데이터 타입
- 사용자가 지정한 정밀도와 스케일을 가지며, 소수 부분의 길이가 고정되어 있다.
  → 따라서 `FLOAT`과 `DOUBLE`보다는 정밀도가 정확하다.
- 총 `M`만큼 숫자를 가지는데, 소수점 아래 부분은 `D`만큼 갖는다.
  → 예를 들어, DECIMAL(7, 2)라면, 01234.56 을 갖는다.
- `M`의 범위는 1 ~ 65, `D`의 범위는 0 ~ 30

  ```sql
  -- CREATE TABLE : 총 길이가 7이고, 소수점 아래 숫자는 2자리

  CREATE TABLE DECIMAL_TBL (VALUE DECIMAL(7, 2));
  ```
  ```sql
  -- INSERT datas

  INSERT INTO DECIMAL_TBL (VALUES)
  VALUES (1.99),
         (449.4),
         (22.44),
         (12345.999),
         (1.99999999);
  ```
  ```sql
  -- Result

  SELECT * FROM BEVERAGES;
  +----------+
  | VALUES   |
  +----------+
  |     1.99 |
  |   449.40 |
  |    22.44 |
  | 12346.00 |  -- 소수점 아래의 자리수를 초과하게 되면 반올림
  |     2.00 |  -- 소수점 아래의 자리수를 초과하게 되면 반올림
  +----------+
  ```

  <br>

### `FLOAT`

- 부동 소수점 32비트 숫자를 나타내는 데이터 타입
- 부호, 지수, 가수 부분으로 구성되어 있어서 매우 크거나 작은 수, 그리고 소수 부분이 많은 수를 표현할 수 있다.
- 그러나 정확도가 떨어지기 때문에 정밀한 소수 계산에는 적합하지 않다.
- Precision issues : ~ 7 digits

  ```sql
  -- CREATE TABLE

  CREATE TABLE FLOAT_TBL(VALUE FLOAT);
  ```
  ```sql
  -- INSERT datas

  INSERT INTO FLOAT_TBL (VALUE)
  VALUES (88.45),
         (77.7777777),
         (10.0000001);
  ```
  ```sql
  -- Result

  SELECT * FROM FLOAT_TBL;
  +---------+
  | VALUE   |
  +---------+
  |   88.45 |
  | 77.7778 |  -- 정밀도가 떨어지는 것을 확인할 수 있다.
  |      10 |  -- 정밀도가 떨어지는 것을 확인할 수 있다.
  +---------+
  ```

  <br>

### `DOUBLE`

- 부동 소수점 64비트 숫자를 나타내는 데이터 타입
- `FLOAT`보다 더 큰 범위의 수와 더 정확한 소수 값을 저장할 수 있다.
- Precision issues : ~ 15 digits

  ```sql
  -- CREATE TABLE

  mysql> CREATE TABLE DOUBLE_TBL(VALUE DOUBLE);
  ```
  ```sql
  -- INSERT datas

  INSERT INTO DOUBLE_TBL (VALUE)
  VALUES (88.45),
         (77.7777777),
         (10.0000001);

  -- Result

  mysql> SELECT * FROM DOUBLE_TBL;
  +------------+
  | VALUE      |
  +------------+
  |      88.45 |
  | 77.7777777 |  -- FLOAT 보다는 정밀도가 뛰어나다.
  | 10.0000001 |  -- FLOAT 보다는 정밀도가 뛰어나다.
  +------------+
  ```
