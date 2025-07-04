# memo

## 기억하고 싶은 말

1. 되고 싶은 사람을 가까이에 두라. - 미스터 비스트
2. S급들과 일하려면 그들에게 자유를 주면 된다. - 스티브 잡스
3. 그 사람을 위해 일하고 싶을 때 그 사람을 채용한다. - 마크 주커버그
4. 아무것도 하지 않는 시간이 중요하다.

## Java EE

- 오라클이 정의한 표준 스펙들의 집합으로, 실제 구현체가 아닌 "이렇게 만들어야 한다"는 설계도
- 주요 스펙들
  - 웹 기술
    - Servlet (JSR-315)
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
- 전체 구현체들
- 
