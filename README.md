# memo

여러 곳에 흩어진 지식과 정보를 저에게 맡게 가공한 메모입니다. 정확하지 않은 정보가 포함될 수 있으니 주의해주세요.

## 기억하고 싶은 말

1. 되고 싶은 사람을 가까이에 두라. - 미스터 비스트
2. S급들과 일하려면 그들에게 자유를 주면 된다. - 스티브 잡스
3. 그 사람을 위해 일하고 싶을 때 그 사람을 채용한다. - 마크 주커버그
4. 아무것도 하지 않는 시간이 중요하다.

## Bash

- 내가 자주 쓰는 명령
```bash
# 깨진 심볼릭 링크 찾기
find . -type l ! -exec test -e {} \; -print

# 특정 라이브러리의 설치 여부 확인
rpm -qa | grep -i glibc

# 공유 라이브러리 확인
ldconfig -p | grep -i libstdc

# 바이너리가 어떤 라이브러리를 사용하는지 확인
ldd /path/to/binary
objdump -p /path/to/binary | grep NEEDED
```

## Docker

- 내가 자주 쓰는 명령
```bash
# Dangling 이미지 삭제
docker image prune

# 이미지에 터미널로 접속
docker run -it -rm image-name:version bash
```

## Git

- 내가 자주 쓰는 명령
```bash
# 커밋 이력을 한 줄로 표시
# -%h  : 짧은 커밋 해시
# -%s  : 커밋 메시지 제목만
# -%an : 커미터 이름
# -%ae : 커미터 이메일
git log branch-name --pretty=format:"%h - %s -%an <%ae>" [--since="2023-01-01"] [--until="2023-12-31"]
```

## Linux

- UID, GID
  - 대부분의 리눅스 배포판에서 시스템 사용자/그룹은 1~999, 일반 사용자/그룹은 1000 이상
  - 시스템 사용자/그룹은 로그인이 불가능하거나 홈디렉토리가 없는 등 서비스 실행을 위한 목적을 가진다.
  - 숫자 범위로 시스템 사용자/그룹과 일반 사용자/그룹을 명확히 구분하고 관리할 수 있다.
- libc
  - C 표준 라이브러리
  - malloc, free, fopen, fread 등 시스템에 필요한 기본적인 기능을 제공한다.
  - 주요 libc 구현체
    - musl (Alpine Linux)
      - 수 백 KB 수준의 작은 크기
      - 메모리 사용량이 적다.
    - glibc (GNU C Library)
      - 수 MB에 달하는 크기
      - 대부분의 리눅스 배포판에서 기본으로 사용
      - 넓은 호환성, 많은 최적화, 널리 테스트되는 등의 장점을 갖는다.

## Java

- JSR (Java Specification Request)
  - JSR-305 (Annotations for Software Defect Detection)
    - 정적 코드 분석 도구를 위한 어노테이션 모음
    - 표준화는 실패했지만 널리 사용되고 있다.
    - `@Nullable`, `Nonnull`, `@CheckForNull`, ...
  - JSR-250 (Common Annotations)
    - 생명 주기 관리와 보안 관련 어노테이션 모음
  - JSR-330 (Dependency Injection for Java)
    - Google Guice, Spring, Dagger 등의 구현체가 있다.
    - 구현체끼리 교체가 쉽지는 않다.
  - JSR-310 (Date and Time API)

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

## Maven

- 내가 자주 쓰는 명령
```bash
# 모든 의존성 출력
mvn dependency:tree

# 특정 의존성만 지정해서 출력
mvn dependency:tree -Dincludes=com.sun.jersey:*

# 모든 프로필 출력
mvn help:all-profiles
```

## MicroProfile

- Quarkus (Red Hat) - 가장 인기 (단, 모든 스펙을 다 구현하지 않았는데 대신 가볍고 빠르다)
- Open Liberty (IBM) - Jakarta EE, MicroProfile 모두 구현했고 TCK를 통과했다
- Helidon (Oracle)

## SQL

- Anti Join보다 Not In이나 Not Exists가 낫다.
  - 데이터 베이스가 지원을 하지 않을 수 있다.
  - NULL 처리가 애매하다.
  - 조인에 사용되는 키에 인덱스가 없다면 느릴 수 있다.
  - Not In, Not Exists가 더 자주 사용되어 익숙하고 최적화가 잘 된다.
 