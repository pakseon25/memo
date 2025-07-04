# memo

여러 곳에 흩어진 지식과 정보를 저에게 맡게 가공한 메모입니다. 정확하지 않은 정보가 포함될 수 있으니 주의해주세요.

## 기억하고 싶은 말

1. 되고 싶은 사람을 가까이에 두라. - 미스터 비스트
2. S급들과 일하려면 그들에게 자유를 주면 된다. - 스티브 잡스
3. 그 사람을 위해 일하고 싶을 때 그 사람을 채용한다. - 마크 주커버그
4. 아무것도 하지 않는 시간이 중요하다.

## Jakarta EE (구 Java EE)

- 오라클이 정의한 표준 스펙들의 집합으로, 실제 구현체가 아닌 "이렇게 만들어야 한다"는 설계도
- 이름 변화
  - J2EE (1999 - 2006)
  - Java EE (2006 - 2017)
  - Jakarta EE (2017 - 현재) // Eclipse Foundation으로 이관
- 주요 스펙들
  - 웹 기술
    - Servlet (JSR-315)
      - Java로 작성된 서버 프로그램을 위한 스펙이다.
      - doGet(), doPost(), doDelete() 등의 메서드를 오버라이드하게 된다.
      - Tomcat, Jetty같은 서블릿 컨테이너에서 실행할 수 있다.
    - JAX-RS (JSR-311/339) - RESTful 웹 서비스 : `@Path(...)`, `@GET`, ...
    - JAX-WS (JSR-224) - SOAP 웹 서비스
    - JSF (JSR-314) - 웹 UI 프레임워크
  - 의존성 주입
    - EJB (JSR-318) - 엔터프라이즈 자바빈즈 : `@Stateless`, ...
    - CDI (JSR-299/346) : `@Inject`, ...
  - 데이터 관련
    - JPA (JSR-317) - Java Persistence API : `@Entity`, ...
    - JTA (JSR-907) - Java Transaction API : `@Transactional`, ...
    - Bean Validation (JSR-303) : `@NotNull`, ...
  - 기타
    - 보안 (JSR-375) : `@RolesAllowed("...")`, ...
- 전체 구현체들 (Application Servers)
  - WildFly (Red Hat)
  - WebLogic (Oracle)
  - WebSphere (IBM)
  - GlassFish (Eclipse)
  - Payara (Payara)
- 개별 스펙 구현체들
  - JAX-RS
    - Jersey (Oracle)
      - `@Get`, `@Put`같은 어노테이션 기반으로 REST API를 개발할 수 있게 해준다.
      - `@Path`로 URL 경로를 지정할 수 있다.
      - Json, XML로 된 데이터를 자동으로 변환해준다.
    - RESTEasy (Red Hat)
    - Apache CXF (Apache)
  - JPA
    - Hibernate (Red Hat)
    - EclipseLink (Eclipse)
    - OpenJPA (Apache)
  - CDI
    - Weld (Red Hat)
    - OpenWebBeans (Apache)
  - Servlet
    - Tomcat (Apache)
    - Jetty (Eclipse)
      - 경량화된 서블릿 컨테이너다.
      - 임베디드 형태로 애플리케이션에 포함시킬 수 있다.
    - Undertow (Red Hat)
- 개별 스펙 구현체의 장단점
  - 각 스펙마다 다른 구현체를 선택해야 한다.
  - 스펙과 구현체가 분리되어 있어 설정과 통합 코드를 직접 작성해야 하므로 조합이 복잡하다.
  - 대신 전체 구현체는 필요 없는 모든 구현이 포함되는 반면 개별 스펙 구현체는 필요한 것만 포함시킬 수 있다.
- Spring과 다른 점
  - Jakarta EE 스펙을 참고하되 독자적인 구현을 제공하여 더 가볍고 사용하기 쉬우며 더 나은 개발자 경험을 제시한다.
  - Jakarta EE Application Server와는 완전히 호환되지 않을 수 있다.
    - EJB    -> Spring Bean
    - JAX-RS -> Spring MVC
    - JMS    -> Spring Integration
    - JCA    -> Spring의 다양한 Connectors
    - JSF    -> Spring MVC + Thymeleaf
  - 점진적으로 Jakarta EE 스펙을 추가 지원하고 있다.
- 지금도 널리 사용되고 있는 이유
  - 계속 발전을 거듭하고 있다.
  - 특정 벤더 종속을 피할 수 있다.
  - MicroProfile 구현체와 혼용하여 마이크로서비스 개발에도 이용할 수 있으며 Spring보다 빠른 실행을 보이기도 한다.

## MicroProfile

- Quarkus (Red Hat) - 가장 인기 (단, 모든 스펙을 다 구현하지 않았는데 대신 가볍고 빠르다)
- Open Liberty (IBM) - Jakarta EE, MicroProfile 모두 구현했고 TCK를 통과했다
- Helidon (Oracle)
