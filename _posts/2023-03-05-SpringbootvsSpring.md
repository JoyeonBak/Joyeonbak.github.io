---
layout: post
title: "[SpringBoot] SpringBoot와 Spring 차이"
subtitle: 
categories: SpringBoot
tags: [SpringBoot]
--- 
## Spring Framework란?

Spring은 JAVA 애플리케이션 개발을 위한 포괄적인 인프라를 지원해주는 Framework이다. 종속성 주입 등 다양한 기능을 제공하고 있다.   
- Spring JDBC
- Spring MVC
- Spring Security
- Spring AOP
- Spring ORM
- Spring Test
 
JAVA 웹 개발 초기에는 데이터 소스에 레코드를 삽입하기 위해서 많은 코드를 작성해야 했다. Spring JDBC 모듈의 JDBC Template을 사용하면 단 몇줄로 이 작업을 끝낼 수 있게 된다.  
 
## Spring Boot란?

Spring Boot는 기본적으로 Spring Framework을 설정하는데 필요한 구성을 제거하는 Spring Framework 확장 버전이라고 생각하면 편하다.  개발자 입장에서 더 빠르고 효율적으로 프로그램 개발이 가능하도록 지원한다. Spring Boot가 지원하는 기능은 다음과 같다.
- 빌드 및 애플리케이션 구성 단순화를 위한 Starter Dependency  
- 애플리케이션 배포의 복잡성을 피하기 위한 임베디드 서버 제공  
- 메트릭, 상태 확인 및 외부 구성 작업
- Spring 기능을 위한 자동구성 작업
- Spring-boot-starter-data-jpa
- Spring Boot Starter Security
- Spring Boot Starter Test
- Spring Boot Starter Thymeleaf
 
 
### Maven 종속성
만약 Spring으로 웹 개발 프로젝트를 실행한다면 Spring Test, JUnit, Hamcrest, Mockito 라이브러리 종속성을 추가해줘야 한다. 하지만 Spring Boot는 모든 라이브러리 구성을 자동으로 포함하기 위한 Test용 Starter Dependency 하나만 만들면 끝이다. 굉장히 단순화 되는 것이다.
 
### MVC 구성
또한 MVC(Model-View-Controller) 구성을 보면 Dispatcher, Suvlet, Mapping등 기타 지원 구성을 따로 개발자가 정의해줘야 한다. web.xml파일이나 initializer 클래스를 이용해서 구성 작업을 해줘야 한다. 또한 구성 클래스에 EnableWebMvc 주석을 추가하고 컨트롤러에서 반환된 뷰를 확인하기 위해 View resolver를 정의해줘야 한다.  
 

Spring Boot는 Web Starter만 추가하면 작동하도록 몇 가지 속성만 추가해주면 된다. Spring에서 필요한 모든 구성은 auto-configuration이라는 프로세스를 통해서 Boot 웹 스타터를 추가하는 작업 하나로 자동으로 프로젝트가 구성된다. 
 
 
### Spring Boot 보안

Spring을 사용해서 보안을 활성화하기 위해서는 spring-security-web과 spring-security-config 종속성을 모두 필요로 한다. 또한 WebSecurityConfigurerAdapter를 확장하고 EnableWebSecurity 주석을 사용하는 클래스를 추가해줘야 한다. 이 과정에서 inMemoryAuthentication을 사용한 인증이 필요하다.  
 

Spring Boot는 모든 관련 종속성을 클래스 경로에 자동으로 추가하기 때문에 spring-boot-starter-security의 종속성만 정의해주면 끝난다. 
 
 
### Spring Boot 배포

Spring이나 Spring Boot 모두 Maven 혹은 Gradle과 같은 일반적인 패키지 관리 기술을 지원하지만, 배포에서는 다른 점을 보이고 있다. Spring Boot Maven Plugin은 Maven에서 Spring Boot를 지원하고 있다. 또한 실행가능 한 jar 또는 war 아카이브를 패키징하여 적재적소에서 애플리케이션을 실행할 수 있다.
 
 
Spring Boot는 다음 기능을 추가로 제공한다.
- 임베디드 컨테이너 제공
- java -jar 명령을 사용해서 jar를 독립적으로 실행하도록 프로비저닝
- 외부 컨테이너에 배포할 때 잠재적인 jar 충돌을 피하기 위해 종속성을 제외하는 옵션
- 배포 시 활성 프로필을 지정하는 옵션
- 통합 테스트를 위한 무작위 포트 생성
 

## 결론

Spring Boot는 Spring 자체의 확장 버전이다. 개발, 테스트, 배포가 Spring Framework에 비해서 혁신적으로 간편해지는 Framework이다. 특정 프로젝트에서 필수적인 종속성 구성이 필요하다면 Spring을, 일반적인 종속성 구성으로 구현이 가능한 프로젝트라면 Spring Boot로도 충분한 결과물을 얻어낼 수 있을 것이다.



출처 :  
<https://incomeplus.tistory.com/344>
