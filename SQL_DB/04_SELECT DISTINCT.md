# **SELECT DISTINCT**

SELECT 시 DISTINCT를 사용하면 중복 값을 제외한 결과값이 출력된다.
즉 같은 결과의 행이라면 중복 제거 가능

#### COLUMN_1의 값이 중복 값 존재 시 중복 값을 제거
```
SELECT
    DISTINCT COLUMN_1
FROM TABLE_NAME;
```

#### COLUMN_1 + COLUMN_2의 값 중복 존재시 중복 값을 제거
```
SELECT
    DISTINCT COLUMN_1, COLUMN_2
FROM TABLE_NAME;
```

#### COLUMN_1+COLUMN_2의 값 중복 존재시 중복 값을 제거
결과를 명확하게 하기 위해 ORDER BY 절 사용
```
SELECT
    DISTINCT COLUMN_1, COLUMN_2
FROM TABLE_NAME;
ORDER BY COLUMN_1, COLUMN_2;
```

---

#### 테이블 생성
```
create table T1 (ID SERIAL not null primary key,BCOLOR VARCHAR, FCOLOR VARCHAR);
```

#### 데이터 등록
```
insert
	into T1 (BCOLOR,FCOLOR)
values
	('RED','RED'),
	('RED','RED'),
	('RED',NULL),
	(NULL,'RED'),
	('RED','GREEN'),
	('RED','BLUE'),
	('GREEN','RED'),
	('GREEN','BLUE'),
	('GREEN','GREEN'),
	('BLUE','RED'),
	('BLUE','GREEN'),
	('BLUE','BLUE');
```

#### DISTINCT ON
```
SELECT 
	DISTINCT ON(BCOLOR) BCOLOR
	,FCOLOR
FROM
	T1
ORDER BY
	BCOLOR,FCOLOR ASC
```
BCOLOR 값 기준으로 중복을 제거하며, FCOLOR의 값은 ORDER BY ASC 기준으로 정렬
