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

### @RequestParam과 @ModelAttributr의 생략
- String, int, Integer 같은 단순 타입 = @RequestParam
- 나머지 = @ModelAttribute (argument resolver로 지정해둔 타입 외)

### HttpEntity
: HTTP header, body 정보를 편리하게 조회
- 메시지 바디 정보를 직접 조회
- 요청 파라미터를 조회하는 기능과 관계 없음 
  - @RequestParam X
  - @ModelAttribute X
- 응답에도 사용 가능
  - 메시지 바디 정보 직접 반환
  - 헤더 정보 포함 가능
  - view 조회 X

### 요청 파라미터 vs HTTP 메시지 바디
- 요청 파라미터 조회: @RequestParam, @ModelAttribute
- HTTP 메시지 바디 조회: @RequestBody