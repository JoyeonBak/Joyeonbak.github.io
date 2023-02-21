---
layout: post
title: "[Java] @RequestBody와 @ResponseBody"
subtitle: 
categories: Java
tags: [Java]
--- 
## 비동기 처리
- Request(요청) : 클라이언트 ➡ 서버  
- Response(응답) : 클라이언트 ⬅ 서버  


비동기 통신을 하려면 클라이언트에서 서버로 요청메세지를 보낼 때 요청/응답시에 본문에 데이터를 담아서 보내야 하는데, 이 본문을 ***body*** 라고 한다.  
요청 시 ***requestBody*** / 응답 시 ***responseBody*** 에 데이터를 담아서 보내야 한다. 


## JSON
이때 본문에 담기는 데이터 형식은 여러가지 형태이지만 가장 대표적으로 사용되는 것이 JSON이다. 다시말해, 비동기식 클라이언트/서버 통신을 위해 가장 많이 사용되는 JSON형식의 데이터를 주고받을 수 있다.


## @RequestBody
@RequestBody 어노테이션이 붙은 파라미터에는 HTTP 요청의 본문(Body)을 통째로 자바객체로 변환해서 매핑된 메소드 파라미터로 전달한다.  
그래서 일반적인 GET/POST의 요청 파라미터는 데이터를 변환할 필요가 없기 때문에 @RequestBody를 사용할 일이 없다.  
반면 XML이나 JSON기반의 비동기 요청의 경우에는 아래와 같은 이유로 해당 어노테이션이 유용하게 사용된다.  
- JSON 데이터를 원하는 타입의 객체로 변환해야 하는 경우에 사용
- HTTP 요청의 본문(Body)을 자바 객체로 받을 수 있음


출처 :  
<https://velog.io/@alicesykim95/RequestBody%EC%99%80-ResponseBody>
