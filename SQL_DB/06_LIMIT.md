# **LIMIT**
LIMIT는 조회한 결과 값의 행의 수를 제한, 한정하는 역할을 하며, 결과의 범위를 처리할 때 사용한다.

LIMIT 에서 중요한 부분은 OFFSET M 번째 부터 시작하는 LIMIT N개의 데이터로, OFFSET 의 첫번째 시작점은 0이기 때문에 OFFSET 3는 4번째 데이터부터 시작을 의미한다.

```
SELECT * FROM TABLE_NAME
```
```
SELECT * 
FROM TABLE_NAME 
LIMIT N 
OFFSET M --  M+1번째 행부터 데이터를 불러온다.

```

#### film 테이블 데이터중 5개의 결과 값만 조회하며 film_id로 정렬

```
select
	film_id,
	title,
	release_year
from
	film
order by film_id
limit 5;
```

