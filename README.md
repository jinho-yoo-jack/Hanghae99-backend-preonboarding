![spartacodingclub](https://noticon-static.tammolo.com/dgggcrkxq/image/upload/v1719643111/noticon/yeqwdeuiybor5m4hh7zj.png)
# Hanghae99 Preonboarding Backend Course

**취업시장에 침투하기 전에, 실전과 같은 훈련으로 코딩의 감(떫음)을 찾아서 세상에 스파르타st를 보여주자.<br />
어렵다고 느끼는 제군들도 있겠지만, 힌트를 보면서 잘 따라 와주기를 바란다.**



### 🎖️ 훈련 메뉴

---
- [ ]  Junit를 이용한 테스트 코드 작성법 이해
- [ ]  Spring Security를 이용한 Filter에 대한 이해
- [ ]  JWT와 구체적인 알고리즘의 이해
- [ ]  PR 날려보기
- [ ]  리뷰 바탕으로 개선하기
- [ ]  EC2에 배포해보기

### Day 1 - 시나리오 설계 및 코딩 시작!

---
**Spring Security 기본 이해**

- [ ]  Filter란 무엇인가?(with Interceptor, AOP)
      Spring에서 사용되는 Filter, Interceptor, AOP는 무승 행동을 하기 전에 먼저 실행하거나, 실행한 후에 추가적인 행동을 할 때 사용되는 기능들이다.
      Interceptor와 Filter는 Servlet 단위에서 실행된다. AOP는 메소드 앞에 Proxy 패텅의 형태로 실행된다.
      요청이 들어왔을 때 Filter를 거쳐 Interceptor가 요청을 가로채고, AOP를 거친 후 다시 Interceptor, Filter 순으로 실행된다.
      이 중 Filter란 보통 생각하는 필터처럼 거름망 같은 존재이다. 요청과 응답을 거른 후 정제하는 역할을 한다.
      Servlet Filter는 DispatcherServlet 이전에 실행 되는데 Filter가 동작하도록 지정된 자원의 앞단에서 요청내용을 변경하거나, 헤더를 검사해 인증 토큰의 유무나 문제를 파악할 수 있다.
      Spring과 분리되어야 하는 기능을 처리하거나, 인코딩 변환 처리, XSS방어, 요청에 대한 인증, 권한 체크 등을 하는 데에 쓰인다.

- [ ]  Spring Security란?
      Spring Framework 중 하나로 Spring 생태계에서 보안에 필요한 기능들을 제공하며, 개발 구조가 Spring Framework 안에서 활용하기 적합한 구조로 설계되어 있다.
      Spring Security는 인증, 권한 관리, 데이터 보호기능 등을 포함하여 사용자 관리 기능을 구현하는데 도움을 주는 Spring Framework이다.
      프레임워크를 사용하지 않고, 코드를 직접 작성할 경우 Spring에서 추구하는 IoC/DI 패턴과 같은 확장 패턴을 염두해서 인증/인가 부분을 직접 개발하기 쉽지 않지만 Spring Security에서는
      이와 같은 기능들을 제공해주기 때문에 개발 효율을 높일 수 있다.
      때문에 Spring을 사용하는 경우에는 Spring Security를 활용하여 보안 기능을 추가하며, 이 외의 추가 기능이 필요할 경우 Spring Security를 바탕으로 기능을 추가하는 방식을 채택할 수 있다.

**JWT 기본 이해**

- [ ]  JWT란 무엇인가요?
      JWT는 Json Web token의 약자로 클라이언트와 서버 사이에서 통신할 때 권한 체크를 위해 사용하는 토큰이다.
      header, payload, signature로 나눠져 있다.
      header는 어떠한 알고리즘으로 암호화 할 지, 어떤 토큰을 사용할 것인지에 대한 정보를 담고있다.
      payload에는 사용자의 정보가 담겨있다. payload에 있는 내용은 수정이 가능하여 더 많은 정보를 추가할 수 있다.
      하지만, payload 자체는 인코딩 된 것이기 때문에 payload에는 중요한 개인정보가 아닌, 해당 토큰에 대한 권한의 범위나 만료일자 같은 최소 정보만을 담아야한다.
      signature는 헤더와 정보를 합친 후 발급해준 서버가 지정한 secret key로 암호화시켜 토큰 변조를 어렵게 만든다.
      JWT는 별도의 인증 저장소가 필요하지 않기 때문에 인증서버와 db에 의존할 필요가 없다. 또한 서버 측 부하를 낮출 수 있고, 독립적이기 때문에 능률적으로 접근 권한 관리를 할 수 있다.
      하지만, 서버로부터 받은 토큰이 쿠키, 로컬, 세션 스토리지에 저장이 되는데, 탈취 당할 위험이 있기 때문에 중요 정보를 담지 말아야 한다.
      토큰에 넣는 데이터가 많아질수록 토큰이 길어져 API를 호출할 때마다 토큰 데이터를 서버에 전달해야 하기 때문에 그만큼 네트워크 대역폭 낭비가 심할 수 있다.
      또한 한 번 발급된 token은 수정 및 폐기가 불가능하다는 단점이 있다.

**토큰 발행과 유효성 확인**

- [ ]  Access / Refresh Token 발행과 검증에 관한 **테스트 시나리오** 작성하기

**유닛 테스트 작성**

- [ ]  JUnit를 이용한 JWT Unit 테스트 코드 작성해보기

  - https://preasim.github.io/39

  - [https://velog.io/@da_na/Spring-Security-JWT-Spring-Security-Controller-Unit-Test하기](https://velog.io/@da_na/Spring-Security-JWT-Spring-Security-Controller-Unit-Test%ED%95%98%EA%B8%B0)


### Day 2 - 백엔드 배포하기

---
**테스트 완성**

- [ ]  백엔드 유닛 테스트 완성하기

**로직 작성**

- [ ]  백엔드 로직을 Spring Boot로
    - [ ]  회원가입 - /signup
        - [ ]  Request Message

           ```json
           {
               "username": "JIN HO",
               "password": "12341234",
               "nickname": "Mentos"
           }
           ```

        - [ ]  Response Message

           ```json
           {
               "username": "JIN HO",
               "nickname": "Mentos",
               "authorities": [
                       {
                               "authorityName": "ROLE_USER"
                       }
               ]		
           }
           ```

    - [ ]  로그인 - /sign
        - [ ]  Request Message

           ```json
           {
               "username": "JIN HO",
               "password": "12341234"
           }
           ```

        - [ ]  Response Message

           ```json
           {
               "token": "eKDIkdfjoakIdkfjpekdkcjdkoIOdjOKJDFOlLDKFJKL",
           }
           ```


**배포해보기**

- [ ]  AWS EC2 에 배포하기

**API 접근과 검증**

- [ ]  Swagger UI 로 접속 가능하게 하기

### Day 3 - 백엔드 개선하기

---
[Git 커밋 메시지 잘 쓰는 법 | GeekNews](https://news.hada.io/topic?id=9178&utm_source=slack&utm_medium=bot&utm_campaign=TQ595477U)

**AI-assisted programming**

- [ ]  AI 에게 코드리뷰 받아보기

**Refactoring**

- [ ]  피드백 받아서 코드 개선하기

**마무리**

- [ ]  AWS EC2 재배포하기
