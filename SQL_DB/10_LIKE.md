# **LIKE**

특정 집합(컬럼 혹은 리스트)에서 어떠한 컬럼의 값이 특정 값과 유사한 패턴을 갖는 집합을 출력하는 연산자

```
select * fromt table_name
where column_name
like 특정패턴
```

특정 패턴과 유사한 값을 조회

```
select * fromt table_name
where column_name
not like 특정패턴
```

특정 패턴과 유사하지 않은 집합

| 기호 | 설명                                  |
| ---- | ------------------------------------- |
| %    | 문자 혹은 문자열이 매칭 되었다고 판단 |
| -    | 한개의 문자이든지 매칭 되었다고 판단  |

#### CUSTOMER 테이블의 FIRST_NAME이 Jen으로 시작하는 데이터를 조회

```
select
	first_name,
	last_name
from customer
where first_name like 'Jen%'
```

| SQL               | 결과값 | 설명                                                                              |
| ----------------- | ------ | --------------------------------------------------------------------------------- |
| SELECT            |        |
| 'foo' like 'foo', | TRUE   | foo = foo 는 같으므로 true                                                        |
| 'foo' like 'f%',  | TRUE   | foo = f% 는 f로 시작하기 때문에 true                                              |
| 'foo' like '_o_', | TRUE   | foo = _o_ 는 3자리이며 2번째 자리가 o이므로 참                                    |
| 'bar' like 'b_'  | FALSE  | bar는 3자리 이지만 b_ 는 2자리 이므로 b로 시작하여도 false를 반환 |


#### CUSTOMER 테이블의 FIRST_NAME에 er을 포함한 모든 데이터를 조회
```
select
	first_name,
	last_name
from
	customer
where
	first_name like '%er%';
```

#### CUSTOMER 테이블의 FIRST_NAME의 첫번째 문자는 어떠한 문자여도 상관이 없으며 다음에 her이 포함된 문자 또는 문자열 조회
```
select
	first_name,
	last_name
from
	customer
where
	first_name like '_her%';
```