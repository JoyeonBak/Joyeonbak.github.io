---
layout: post
title: "[Java_Spring] 기술 면접 준비"
subtitle: 
categories: Java
tags: [Java, Spring]
---
## SPRING
- 여기서 말하는 스프링은 Spring Core  
- SpringMVC는 라이브러리 중 하나  
- 객체를 관리할 수 있는 "컨테이너" 제공 ➡ 의존성 주입 & 제어의 역전 ➡ 결합도 감소  
 *"따라서, Spring은 자바의 오픈소스 애플리케이션 프레임워크 중 하나로 특정 기술에 종속되지 않고 객체를 관리할 수 있는 프레임워크(컨테이너)를 제공한다."*




## DI
- Dependency Injection(의존성 주입)  
- 객체간 의존관계를 미리 설정하면 ➡ 컨테이너가 의존관계 자동 연결  
- 직접 객체를 생성하거나 검색할 필요 없음 ➡ 결합도 감소



## IOC
- Inversion Of Control(제어의 역전)  
- 프레임워크의 특징 중 하나  
- 제어권이 사용자가 아닌 프레임워크에 있음  
  따라서, 필요에 따라 사용자 코드 호출 ➡ 인스턴스 생성 ~ 소멸을 컨테이너가 관리  


***


## ORM
- Object Relational Mapping  
- 관계형DB ➡ OOP(객체지향프로그래밍)언어로 변환  
- 테이블 - 객체 매핑(파싱 과정 불요)
  *비즈니스 코드(내가 짜려는 코드)가 DB테이블에 바로 접근하게 도와줌*  


<img src="/assets/images/java/orm2.png"  width="50%">  


## JPA
- ORM을 위해 자바에서 제공하는 API  
- 인터페이스 개념  

### Hibernate(하이버네이트)
- 대표적 JPA 구현체  
- JAVA의 JPA(인터페이스)를 구현한(implement) 클래스  

참고1.  
<img src="/assets/images/java/jpa.png">
참고2.  
<img src="/assets/images/java/jpa1.png">

### ORM, JPA, Hibernate 의 장단점

#### 장점
* 비즈니스 로직에 집중 가능 *<span style='color: #808080'>∵ 쿼리를 가져오거나 파싱하는 과정 필요 없음</span>*
* 객체 중심 개발 가능 *<span style='color: #808080'>∵ DB를 객체로 만드는 것</span>*
* 생산성 향상 *<span style='color: #808080'>∵ 메소드 하나만 호출하면 끝</span>*
* 유지보수 쉽고 비용 감소
* DB 의존성 감소  
  *<span style='color: #808080'>∵ MYSQL, ORACLE 등 다른 DB종류로 변경되어도 메소드만 실행하면 자동으로 변형이 가능</span>*   

#### 단점
* 직접 SQL을 쓰는 것보다 성능 속도가 느림
* 복잡한 쿼리는 Hibernate으로 구현하기 어려움  
  **그럼에도 불구하고 장점이 많아서 많이 사용**


출처 :  
- <https://www.youtube.com/watch?v=VHZ2i4cuwb8&list=PLi-xJrVzQaxU-xK2ao8utngQJqAX4DQty&index=7>  
- <https://ksbsite.tistory.com/37>  
- <https://hanamon.kr/orm%EC%9D%B4%EB%9E%80-nodejs-lib-sequelize-%EC%86%8C%EA%B0%9C/>  
- <https://geonlee.tistory.com/207>  