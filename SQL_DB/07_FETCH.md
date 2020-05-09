# **FETCH**
LIMIT와 마찬가지로 특정 집합을 출력시 출력하는 행의 수를 한정하는 역할을 한다(부분 범위 처리시 사용)

```
SELECT
	*
FROM TABLE_NAME
FETCH FIRST [N] ROW ONLY
```
출력하는 행의 수를 지정하며 N을 입력하지 않고 ROW ONLY만 입력하면 1개의 데이터만 조회
```
SELECT
	*
FROM TABLE_NAME
OFFSET N ROWS
FETCH FIRST [N] ROW ONLY
```
출력하는 행의 범위를 지정

```
SELECT
	FILM_ID
	,TITLE
FROM
	FILM
ORDER BY TITLE
FETCH FIRST ROW ONLY -- TITLE로 정렬한 집합 중에서 최초의 단 한 건 행을 리턴
```

```
SELECT
	FILM_ID
	,TITLE
FROM
	FILM
ORDER BY TITLE
	OFFSET 5 ROWS
FETCH FIRST ROW ONLY -- TITLE로 정렬한 집합 중에서 6번째 행부터 5건의 행을 리턴
```
