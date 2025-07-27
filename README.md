&# memo

**여러 곳에 흩어진 지식과 정보를 저에게 맡게 가공한 메모입니다. 정확하지 않은 정보가 포함될 수 있으니 주의해주세요.**

## 기억하고 싶은 말

1. 되고 싶은 사람을 가까이에 두라. - 미스터 비스트
1. S급들과 일하려면 그들에게 자유를 주면 된다. - 스티브 잡스
1. 그 사람을 위해 일하고 싶을 때 그 사람을 채용한다. - 마크 주커버그
1. 아무것도 하지 않는 시간이 중요하다.
1. 의사들은 가난한 환자들에게 무관심했고, 간호사들의 긴급출동 호출에도 느그하게 대응했다. 그들은 항상 무기력해보이고 모든 것을 따분하고 지루하게 여기는 것처럼 보였다. 한번은 과장이 병실을 돌다가 어떤 환자의 상태를 유심히 살폈다. 그러다가 갑자기 주니어 의사들을 모두 호출했다. 그 환자는 보통의 환자들에게 볼 수 없는 특이한 병이었고 모든 의사들은 새로운 케이스를 연구하기 위해 모여들었다. 그리고 그 옆에서는 평범한 환자들이 죽어가고 있었다 - 1800년대말 프랑스에서 있었던 일이라고 한다
1. 셔츠 앞에 적힌 팀의 이름을 위해서 경기를 해라. 그러면 사람들은 그 셔츠 뒤에 적힌 당신의 이름을 기억할 것이다.
1. 학습에는 의도가 필요하다
1. One of the real challenges here is the way that A.I. undermines the human value of attention, and the individuality that flows from that. - nytimes

## 어딘가에 넣기 애매한 말

1. 라이브 서비스의 데이터를 처리하는 경우 어뷰징, DDoS로 데이터양이 폭증할 수 있으므로 이에 대한 대응책이 있어야 한다.
1. Designing for large scale can be deferred by setting the right expectations with customers, and by adding guardrails like product limits and rate limits. Focusing on launching initial versions of products with just a few essential parts, maybe two or three components, gives us something to ship, test, and learn from quickly. We can always add complexity later, but only once it’s clear we need it. (https://blog.cloudflare.com/timescaledb-art/)
1. Unlike most traditional SQL databases, Impala eschews these exhaustive search query optimization strategies to simplify query planning. This is an emerging trend adopted by several database systems including Google’s F1 and Youtube’s Procella, which take a similar non-exhaustive approach to query optimization. This means that small queries can be planned quickly, avoiding situations where it takes longer to plan a query than to execute it. Impala’s planner simplifies planning in several ways. (https://www.cloudera.com/blog/technical/keeping-small-queries-fast-short-query-optimizations-in-apache-impala.html)

## 좋은 글에서 발췌

### 언제 멈추고 언제 밀어붙여야 할까(번역글)
출처: https://news.hada.io/topic?id=21613

```
(전략)

실행 전략: 불확실성 속에서 현명하게 판단하는 질문들
아래와 같은 질문과 전략을 통해, 멈출지 계속할지 조금 더 객관적으로 판단할 수 있다.
- 재미와 배움: 여전히 이 프로젝트가 재미있고, 배우는 게 있는가?
- 진행 속도: 최근 진행이 빨라지고 있는가, 느려지고 있는가?
- 제3자 시각: 외부인의 피드백으로 자신을 점검한다.
- 매몰비용 무시: 이미 쓴 시간·돈에 휘둘려 결정하지 않는다.
- 팀의 에너지: 팀이 더 이상 확신이나 아이디어가 없다면, 방향 전환(pivot)이나 종료를 고민한다.
- 12개월 뒤 상상: 1년 뒤에도 이 일을 하고 있을 자신이 있는가?
- 제품 경쟁력: 우리 제품이 시장 대안보다 확실히 낫거나 곧 나아질 것 같은가?
- 입증된 사례(Existence proof): 남이 비슷한 성공을 이미 해냈는가?
- 가치·개선·의지: (a) 충분히 가치 있는가, (b) 개선 가능성이 있는가, (c) 내가 여전히 에너지가 있는가?
- 기회비용(Opportunity Cost): 이 일에 집착하느라 더 중요한 기회를 놓치고 있지 않은가?
- 결과와 보상: 실패 시 불이익, 성공 시 보상은 무엇인가?
- 두려움 극복: 두려움 때문에 결정을 미루지 않는다.
- 내면의 소리: 혼자 산책하며 내면의 진짜 답을 들어본다.
- 처음의 ‘이유(Why)’: 시작할 때의 동기가 지금도 유효한가?

(후략)
```

### "평범한" 엔지니어를 찬양하며
출처: https://news.hada.io/topic?id=21606

```
(전략)

"10x팀"을 만드는 방법
- 코드 작성과 배포 사이의 간격을 최대한 줄임
  - 빠른 배포 주기는 인지 부담을 줄이고, 더 빠른 실험과 피드백을 가능하게 함
  - 배포가 느릴수록 여러 변경이 한꺼번에 모여, 문제 추적과 롤백이 어려워짐
- 실수 복구와 롤백을 쉽게 만듦
  - 개발자가 스스로 코드를 배포하고, 문제를 발견하면 신속하게 복구할 수 있어야 함
- 옳은 행동을 쉽게, 잘못된 행동을 어렵게 만듦
  - 디자이너, 플랫폼 엔지니어와 협력해, 가드레일과 셀프서비스 체계를 구축
- 관측성과 계측 도구에 적극 투자
  - 실제 코드 동작을 시각화하여, 모든 엔지니어가 쉽게 시스템을 이해하고 디버깅할 수 있도록 지원
- 내부 도구와 생산성 향상에 엔지니어링 리소스 투자
  - 이런 시스템은 별도의 오너십이 필요하고, 전사적 우선순위가 되어야 함
- 포용적 문화 조성
  - 누구나 질문, 실수, 탐색이 가능한 환경
  - 다양한 배경, 스킬, 연차가 어우러진 팀이 더 회복력 있고, 변화에 강함
- 모든 레벨의 엔지니어가 섞인 팀 구성
  - 주니어부터 시니어까지 서로 배우고 가르치며 함께 성장하는 구조
  - 이런 시스템은 신입 온보딩, 팀 간 이동 등에도 재활용 가능

(후략)
```

## Expert Generalist

```
(전략)

We've always felt that such desires are wrong-headed. The characteristics that we've observed separating effective software developers from the chaff aren't things that depend on the specifics of tooling. We rather appreciate such things as: the knowledge of core concepts and patterns of programming, a knack for decomposing complex work-items into small, testable pieces, and the ability to collaborate with both other programmers and those who will benefit from the software.

We think that the notion of mechanical sympathy has a broader sense in software, in that we do need to cultivate such a sympathy for any adjacent domain to the ones we are working on. When working on a database design, we need such a sympathy for the user-interface so we can construct a design that will work smoothly with the user-experience. A user-experience designer needs such a sympathy with software constraints so when choosing between similarly valuable user flows, they take into account how hard it is to build them.

(후략)
```

## Apache Hudi

- Viewed through the lens of the RUM Conjecture - which states that optimizing for two of Read, Update, and Memory inevitably requires trading off the third. CoW and MoR emerge as two natural design responses to the trade-offs in lakehouse table formats: (https://hudi.apache.org/blog/2025/07/21/mor-comparison/)
- Copy-on-Write tables optimize for read performance. They rewrite Parquet files entirely when a change is made, ensuring clean, columnar files with no extra merge logic at query time. This suits batch-style, read-optimized analytics workloads where write frequency is low.
- Merge-on-Read, in contrast, introduces flexibility for write-intensive and latency-sensitive workloads by avoiding expensive writes. Instead of rewriting files for every change, MoR tables store updates in delta logs (Hudi), delete files (Iceberg V2), or deletion vectors (Delta Lake). Reads then stitch together the base data files with these changes to present an up-to-date view. This tradeoff favors streaming or near real-time workloads where low write latency is critical.

## Bash

- 내가 자주 쓰는 명령
```bash
# 이전 디렉토리로 이동
cd -

# 바로 직전 실행한 명령 고쳐서 실행
^jg^jpg
!!:s/jg/jpg/

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
- CDPATH
- pushd, popd, dirs, dirs -p, dirs -v

## ClickHouse

- Initially, a custom database driver was written for ClickHouse, but we ended up switching to the excellent ch-go low level library, which directly reads Blocks from ClickHouse in a columnar format. This had a dramatic effect on performance in comparison to the standard Go driver. Combined with the framework optimisations above, we now ingest millions of rows per second with a single ClickHouse connection. (https://blog.cloudflare.com/building-jetflow-a-framework-for-flexible-performant-data-pipelines-at-cloudflare/)

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
- git repack –adf [--path-walk or –window]
  - 경로 비교할 때 앞 16글자만 보는 것이 디폴트라서 파일을 단순히 옮겨도 전체 파일을 다시 푸시할 수 있다.
  - window로 비교 길이를 늘리거나 path-walk로 비교 방법을 바꿔서 다시 압축하면 용량 절감 효과가 매우 클 수 있다.
  - git survey로 비효율적인 저장 상황을 살펴볼 수 있다.


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

## Python

- Context Manager
  - `__enter__`, `__exit__`을 구현하면 된다.

## SQL

- Anti Join보다 Not In이나 Not Exists가 낫다.
  - 데이터 베이스가 지원을 하지 않을 수 있다.
  - NULL 처리가 애매하다.
  - 조인에 사용되는 키에 인덱스가 없다면 느릴 수 있다.
  - Not In, Not Exists가 더 자주 사용되어 익숙하고 최적화가 잘 된다.
 
## React

### 컴포넌트
- no props
```typescript
function UserList() {
  return (
    <div>
      <h2>사용자 목록</h2>
      <p>여기에 사용자들이 표시됩니다</p>
    </div>
  );
}
```

- with props
```typescript
function UserCard({ user }) {
  return (
    <div className="user-card">
      <h3>{user.name}</h3>
      <p>이메일: {user.email}</p>
      <p>가입일: {user.createdAt}</p>
    </div>
  );
}
```

- React fragment

React 컴포넌트는 여러 개의 HTML 요소를 반환할 때, 반드시 하나의 부모 요소로 감싸야 한다는 규칙이 있다. 예전에는 불필요한 `<div>` 태그로 감싸야만 했다. **Fragment (<>...</>)**는 이렇게 불필요한 태그를 생성하지 않고, 여러 요소를 하나로 묶어주는 역할을 하는 '투명한' 포장지 같은 것이다. 실제 웹페이지의 HTML 구조에는 아무런 영향을 주지 않아 더 깔끔하고 효율적이다.

```typescript
function UserCard({ user }) {
  return (
    <>
      <h1>Hello</h1>
      <p>This is React Demo</p>
    </>    
  );
}
```

### export

- default export
  - 파일(모듈)에서 대표가 되는 단 하나만 내보낼 때 사용한다
  - 가져올 때(import) 중괄호 {} 없이 원하는 이름으로 가져올 수 있다. (예: `import Main from './App'`)
  - 주로 React 컴포넌트에서 사용

```typescript
// utils.ts
function calculateTotal(items) {
  return item.reduce((sum, item) => sum + item.price, 0);
}

export default calculateTotal;

// App.ts
import calculateTotal from './utils';
// 또는 다른 이름으로 가져오기 가능
import calc from './utils';
import anyName from './utils';
```

- named export
  - 파일에서 여러 개를 내보낼 때 사용한다.
  - 가져올 때(import) 반드시 중괄호 {} 안에 원래 이름 그대로 사용해야 한다. (예: `import { MyButton, MyInput } from './components'`)
  - 유틸리티 함수, 상수 등에서 주로 사용

```typescript
// helpers.ts
export function formatPrice(price) {
  return `\${price.toLocaleString()}`;
}

export function formatDate(date) {
  return date.toLocaleDateString('ko-KR');
}

const DISCOUNT_RATE = 0.15

export { formatPrice, formatDate, DISCOUNT_RATE };

// api.ts
import { formatPrice, formatDate, DISCOUNT_RATE } from './helpers'
```

### React Hook

**React Hook(훅)**은 함수형 컴포넌트에서 React의 핵심 기능(예: 상태 관리, 생명주기)을 "걸어서(hooking)" 사용할 수 있게 해주는 특별한 함수다.

과거에는 상태를 관리하려면 복잡한 '클래스 컴포넌트'를 사용해야만 했다. 하지만 Hook이 도입된 이후로는 간결한 '함수형 컴포넌트' 내에서 useState, useEffect 같은 Hook을 사용하여 상태를 만들고 데이터를 불러오는 등 다양한 작업을 할 수 있게 되었다.

Hook은 항상 use로 시작하는 이름을 가지며(useState, useEffect, useContext 등), React의 기능을 함수 안으로 가져오는 역할을 한다.

- 상태 관리 (useState)

```typescript
import { useState } from 'react';

function DataTable() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(false);
  const [filter, setFilter] = useState('');

  const adduser = (newUser) => {
    setUsers([...users, newUser]);
  };

  const deleteUser = (userId) => {
    setUsers(users.filter(user => user.id !== userid))
  }

  return (
    <div>
      <input type="text"
        value={filter}
        onChange={(e) => setFilter(e.target.value)}
        placeholder="이름으로 검색..."
      />

      {loading ? (
        <p>로딩 중...</p>
      ) : (
        <div>
          {users.filter(user => user.name.includes(filter))
                .map(user => (<UserCard key={user.id} user={user} />))
          }
        </div>
      )}
    </div>
  );
}
```

- API 호출 (useEffect)

```typescript
import { useState, useEffect } from 'react';

function Dashboard() {
  const [stats, setStats] = useState(null);
  const [error, setError] = useState(null);

  useEffect(() => {
    // 컴포넌트 마운트 시 데이터 로드
    loadDashboardData();
  }, []); // 빈 배열. 한 번만 실행

  const loadDashboardData = async() () => {
    try {
      setLoading(true);
      const response = await fetch('/api/dashboard');
      const data = await response.json();
      setStats(data);
    } catch (err) {
      setError(err.message);
    } finally {
      setLoading(false);
    }
  };

  if (error) return <div>오류: {error}</div>;
  if (!stats) return <div>로딩 중...</div>;

  return (
    <div>
      <h1>대시보드</h1>
      <div>총 사용자: {stats.totalUsers}</div>
      <div>오늘 가입: {stats.todaySignups}</div>
    </div>
  );
}
```

- useCallback

### 폼 처리

```typescript
function CreateUserForm() {
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    role: 'user'
  });

  const handleChange = (e) => {
    const { name, value } = e.target;
    setFormData(prev => ({
      ...prev,
      [name]: value
    }));
  };

  const handleSubmit = async (e) => {
    e.preventDefault();

    try {
      const response = await fech('/api/users', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(formData),
      });

      if (response.ok) {
        alert('사용자 생성 완료');
        setFormData({ name: '', email: '', role: 'user' });
      }
    } catch (err) {
      alert('오류 발생: ' + error.message);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label>이름:</label>
        <input
          type="text"
          name="name"
          value={formData.name}
          onChange={handleCange}
          required
        />
      </div>

      <div>
        <label>이메일:</label>
        <input
          type="email"
          name="email"
          value={formData.email}
          onChange={handleCange}
          required
        />
      </div>

      <div>
        <label>역할:</label>
        <select name="role" value={formData.role} onChange={handleChange}>
          <option value="user">사용자</option>
          <option value="admin">관리자</option>
        </select>
      </div>

      <button type="submit">생성</button>
    </form>
  )
}
```

### 간단한 라우팅 (react-router)

```typescript
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">대시보드</Link>
        <Link to="/users">사용자 관리</Link>
        <Link to="/logs">로그</Link>
      </nav>

      <Routes>
        <Route path="/" element={<Dashboard />} />
        <Route path="/users" element={<UserManagement />} />
        <Route path="/logs" element={<LogViewer />} />
      </Routes>
    </BrowserRouter>
  );
}
```

### 조건부 렌더링 & 리스트

```typescript
function AdminPanel({ user }) {
  return (
    <div>
      {user.isAdmin && (
        <div>
          <h3>관리자 메뉴</h3>
          <button>시스템 설정</button>
        </div>
      )}

      <div>
        <h3>최근 활동</h3>
        {user.activities.length === 0 ? (
          <p>활동이 없습니다</p>
        ) : (
          <ul>
            <user.activities.map(activity => (
              <li key={activity.id}>
                {activity.type}: {activity.description}
              </li>
            ))>
          </ul>
        )}
      </div>
    </div>
  );
}
```

### 커스텀 훅

```typescript
// 데이터 페칭 훅
function useApi(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  const refetch = async () => {
    setLoading(true);
    setError(null);

    try {
      const response = await fetch(url);
      const result = await response.json();
      setData(result);
    } catch (err) {
      setERror(err.message);
    } finally {
      setLoading(false);
    }
  };

  useEffect(() => {
    refetch();
  }, [url]);

  return { data, loading, erro, refetch };
}

// 사용법
function UserList() {
  const { data: users, loading, error, refetch } = useApi('/api/users');

  if (loading) return <div>로딩 중...</div>;
  if (error) return <div>오류: {error}</div>;

  return (
    <div>
      <button onClick={refetch}>새로고침</button>
      {users?.map(user => (
        <UserCard key={user.id} user={user} />
      ))}
    </div>
  );
}
```

### Recoil
