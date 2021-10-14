# Log 레벨
1. trace
2. debug <- 개발서버
3. (default) info <- 운영서버
4. warn
5. error

application.properties
````xml
#디폴트 로그 레벨 설정
logging.level.root=info

#hello.springmvc 패키지와 그 하위 로그 레벨 설정(trace 이하 레벨 전부 출력)
logging.level.hello.springmvc=trace
````

### @RestController
- @Controller: 반환값이 String이면 View 이름으로 인식 -> View 찾아 렌더링 됨
- @RestController: 반환 값으로 View를 찾는 것이 아니라, HTTP 메시지 바디에 바로 입력함.

> @Conroller 의 사용 가능한 파라미터 목록   
> https://docs.spring.io/spring-framework/docs/current/reference/html/web.html#mvc-annarguments

> @Conroller 의 사용 가능한 응답 값 목록   
> https://docs.spring.io/spring-framework/docs/current/reference/html/web.html#mvc-annreturn-types

### MultiValueMap
- 하나의 키에 여러 값을 받을 수 있음
- Http header, HTTP 쿼리 파라미터와 같이 하나의 키에 여러 값을 받을 때 사용

