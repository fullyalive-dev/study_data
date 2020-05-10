# **BETWEEN**
특정 집합(컬럼 혹은 리스트)에서 어떠한 컬럼의 값이 특정 범위안에 들어가는 집합츨 출력하는 연산자

```
SELECT * FROM TABLE_NAME
WHERE COLUMN_NAME
BETWEEN VALUE_A AND VALUE_B;

-- BETWEEN연산자를 사용하지 않으면 아래와 같다.
-- COLUMN_NAME >= VALUE_A AND COLUMN_NAME <= VALUE_B

```
COLUMN_NAME 값이 VALUE_A 와 VALUE_B 사이에 있는 값을 조회

```
SELECT * FROM TABLE_NAME
WHERE COLUMN_NAME
NOT BETWEEN VALUE_A AND VALUE_B;

-- BETWEEN연산자를 사용하지 않으면 아래와 같다.
-- COLUMN_NAME < VALUE_A AND COLUMN_NAME > VALUE_B
```
COLUMN_NAME 값이 VALUE_A 와 VALUE_B 사이에 있지 않은 값을 조회


#### AMOUNT가 8부터 9사이의 값을 조회


```
select
	CUSTOMER_ID,
	PAYMENT_ID,
	AMOUNT
from 
	PAYMENT
where AMOUNT between 8 and 9;
-- where AMOUNT >= 8 and AMOUNT <= 9
```
#### AMOUNT가 8부터 9사이가 아닌 값을 조회
```
select
	CUSTOMER_ID,
	PAYMENT_ID,
	AMOUNT
from 
	PAYMENT
where AMOUNT not between 8 and 9;
-- where AMOUNT < 8 or AMOUNT > 9
```
#### PAYMENT 테이블의 PAYMENT_DATE가 2007년 2월7일 부터 2007년 2월15일 까지의 데이터를 조회
```
select 
	customer_id,payment_id, 
	amount,payment_date 
from payment 
where cast(payment_date as date) 
between '2007-02-07' and '2007-02-15'; 
```
위 쿼리와 동일 쿼리
```
select
	customer_id,payment_id,
	amount,payment_date
from payment
where to_char(payment_date ,'YYYY-MM-DD')
between '2007-02-07' and '2007-02-15';
```