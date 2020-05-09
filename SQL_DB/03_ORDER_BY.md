# **ORDER BY**

```
SELECT 
    COLUMN_1    
    ,COLUMN_2   
    ,...
FROM
    TABLE_NAME 
ORDER BY COLUMN_1 ASC   -- SQL 결과물 출력시 COLUMN_1 오름차순으로 정렬
        , COLUMN_2 DESC -- SQL 결과물 출력시 COLUMN_2 내림차순으로 정렬
;               
```

아래 쿼리는 위 쿼리와 같이 작동한다.

```
SELECT 
    COLUMN_1    
    ,COLUMN_2   
    ,...
FROM
    TABLE_NAME 
ORDER BY 1 ASC  -- ORDER BY 절에 정수를 넣어도 SELECT 대상 COLUMN 순으로 작동
        ,2 DESC 
;               
```

단 가독성, 유지보수 측면에서 첫 번째 방식대로 COLUMN명을 표기해주는 것이 좋음