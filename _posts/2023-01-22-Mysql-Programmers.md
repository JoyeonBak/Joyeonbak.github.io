---
layout: post
title: "[SQL_MYSQL] 프로그래머스 SQL 고득점 Kit 오답 풀이"
subtitle: 
categories: SQL
tags: [SQL, MYSQL]
---
### SQL 구문 순서
순서 때문에 SELECT의 ALIAS는 ORDER BY에서만 사용/적용된다.
SELECT 컬럼명      | (5) 
FROM 테이블명       | (1)
WHERE 테이블 조건   | (2)
GROUP BY 컬럼명    | (3)
HAVING 그룹 조건    | (4)
ORDER BY 컬럼명    | (6)


### 반올림, 올림, 버림
```MYSQL
ROUND(숫자 또는 컬럼명, 반올림 하는 자리)
```

<img src="/assets/images/sql/SQL_ROUND.png"  width="50%">

| 함수                  |    의미    |
|---|---|
|ABS(숫자)                 | 절대값
|CEIL(숫자)                | 소수점 이하 올림
|FLOOR(숫자)               | 소수점 이하 버림
|ROUND(숫자, 자릿수)         | 자릿수를 기준으로 반올림
|TRUNCATE(숫자, 자릿수)      | 자릿수를 기준으로 버림
|POW(X, Y) , POWER(X, Y)  | X의 Y승
|MOD(분자, 분모)            | 분자를 분모로 나눈 나머지
|GREATEST(숫자1, 숫자2,...) | 주어진 숫자 중에 가장 큰 값을 반환
|LEAST(숫자1, 숫자2,...)    | 주어진 숫자 중에 가장 작은 값을 반환


```MYSQL
SELECT ROUND(AVG(DAILY_FEE),0) AS AVERAGE_FEE
FROM CAR_RENTAL_COMPANY_CAR
WHERE CAR_TYPE = 'SUV';
```




#### 오프라인/온라인 판매 데이터 통합하기 : UNION 또는 UNION ALL
```MYSQL
SELECT DATE_FORMAT(SALES_DATE,'%Y-%m-%d') AS SALES_DATE
      , PRODUCT_ID
      , USER_ID
      , SALES_AMOUNT
FROM ONLINE_SALE
WHERE SALES_DATE >='2022-03-01' AND SALES_DATE < '2022-04-01'

UNION ALL -- 중복허용

SELECT DATE_FORMAT(SALES_DATE,'%Y-%m-%d') AS SALES_DATE
      , PRODUCT_ID
      , NULL AS USER_ID
      , SALES_AMOUNT
FROM OFFLINE_SALE
WHERE SALES_DATE >='2022-03-01' AND SALES_DATE < '2022-04-01'
-- DATE_FORMAT(SALES_DATE,'%Y-%m')='2022-03'와 같음
```


### JOIN & GROUP BY
Q. MEMBER_PROFILE와 REST_REVIEW 테이블에서 리뷰를 가장 많이 작성한 회원의 리뷰들을 조회하는 SQL문을 작성해주세요. 
```MYSQL
```





Q. USER_INFO 테이블과 ONLINE_SALE 테이블에서  
2021년에 가입한 전체 회원들 중   
상품을 구매한 회원수와 상품을 구매한 회원의 비율(=2021년에 가입한 회원 중 상품을 구매한 회원수 / 2021년에 가입한 전체 회원 수)을 년, 월 별로 출력하는 SQL문을 작성해주세요.   
상품을 구매한 회원의 비율은 소수점 두번째자리에서 반올림하고,   
전체 결과는 년을 기준으로 오름차순 정렬해주시고 년이 같다면 월을 기준으로 오름차순 정렬해주세요.   

```MYSQL
SELECT YEAR, MONTH, COUNT(*) AS PUCHASED_USERS,
	ROUND((COUNT(*)/ (SELECT COUNT(*)
					FROM USER_INFO WHERE YEAR(JOINED) = 2021)), 1) AS PUCHASED_RATIO


-- 여기서 DISTINCT 가 중요하다. 여러번 구매한 사람이 있을 수 있기 때문.                            
FROM (
    SELECT DISTINCT YEAR(S.SALES_DATE) AS YEAR, MONTH(S.SALES_DATE) AS MONTH, U.USER_ID
    FROM ONLINE_SALE S
    JOIN USER_INFO U ON S.USER_ID = U.USER_ID AND YEAR(JOINED) = 2021
) A


GROUP BY YEAR, MONTH
ORDER BY YEAR, MONTH
```






출처 :
<https://thebook.io/006977/ch04/02/02/01/>