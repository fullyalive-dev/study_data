# **WHERE**

WHERE절은 집합을 가져올 때 어떤 집합을 가져올 것인지에 대한 조건을 설정하는 절

```
SELECT
	COLUMN_1,
    	COLUMN_2
FROM
	TABLE_NAME
WHERE
	<조건>
```

|연산자|설명|
|------|---|
|=|같음|
|>|~보다 큰|
|>=|~보다 크거나 같은|
|<|~보다 작은|
|<=|~보다 작거나 같은|
|<>, !=|~가 아닌|
|AND|그리고|
|OR|또는|

#### - CUSTOMER 테이블에서 FIRST_NAME 이 Jamie인 조건을 조회


```
select
	LAST_NAME,
	FIRST_NAME
from
	customer
where
	FIRST_NAME='Jamie';
```

#### - CUSTOMER 테이블에서 FIRST_NAME 이 Jamie이고 LAST_NAME 이 Rice인 조건을 조회

```
select
	LAST_NAME,
	FIRST_NAME
from
	customer
where
	FIRST_NAME='Jamie'
and LAST_NAME ='Rice';
```

#### - PAYMENT 테이블 에서 AMOUNT가 1이하 이거나 8이상인 조건이며 CUSTOMER_ID,AMOUNT,PAYMENT_DATE 컬럼 조회

```
select
	CUSTOMER_ID,
	AMOUNT,
	PAYMENT_DATE
from
	PAYMENT
where
	AMOUNT <= 1
 OR AMOUNT >= 8;
```