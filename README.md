# memo

**여러 곳에 흩어진 지식과 정보를 저에게 맡게 가공한 메모입니다. 정확하지 않은 정보가 포함될 수 있으니 주의해주세요.**

## 마음에 드는 시간 관리 기법
* 2분 규칙
  * 2분 내 끝나는 일은 즉시 처리하여 작은 업무의 누적을 방지
  * 미루지 않고 즉시 실행함으로써 관성을 만들고 큰 작업으로 연결됨
* Eat the frog
  * 하루의 가장 어려운 일을 먼저 처리하여 성취감과 동력을 확보
  * 아침 시간대의 높은 집중력을 활용하는 전략임
* Ivy Lee 방법
  * 하루 6가지 최우선 과제를 기록하고 순서대로 처리
  * 단순하지만 강력한 우선순위 관리 기법임


## 기억하고 싶은 말

1. 되고 싶은 사람을 가까이에 두라. - 미스터 비스트
1. S급들과 일하려면 그들에게 자유를 주면 된다. - 스티브 잡스
1. 그 사람을 위해 일하고 싶을 때 그 사람을 채용한다. - 마크 주커버그
1. 아무것도 하지 않는 시간이 중요하다.
1. 의사들은 가난한 환자들에게 무관심했고, 간호사들의 긴급출동 호출에도 느그하게 대응했다. 그들은 항상 무기력해보이고 모든 것을 따분하고 지루하게 여기는 것처럼 보였다. 한번은 과장이 병실을 돌다가 어떤 환자의 상태를 유심히 살폈다. 그러다가 갑자기 주니어 의사들을 모두 호출했다. 그 환자는 보통의 환자들에게 볼 수 없는 특이한 병이었고 모든 의사들은 새로운 케이스를 연구하기 위해 모여들었다. 그리고 그 옆에서는 평범한 환자들이 죽어가고 있었다 - 1800년대말 프랑스에서 있었던 일이라고 한다
1. 셔츠 앞에 적힌 팀의 이름을 위해서 경기를 해라. 그러면 사람들은 그 셔츠 뒤에 적힌 당신의 이름을 기억할 것이다.
1. 학습에는 의도가 필요하다
1. One of the real challenges here is the way that A.I. undermines the human value of attention, and the individuality that flows from that. - nytimes
1. 혼자서 오래 글을 쓰던 사람들은 인정의 계기가 없으면 자기에 대해서 계속 의심을 하게 되잖아요. - 현호정x하미나 라이브 북토크

## 어딘가에 넣기 애매한 말

1. 라이브 서비스의 데이터를 처리하는 경우 어뷰징, DDoS로 데이터양이 폭증할 수 있으므로 이에 대한 대응책이 있어야 한다.
1. Designing for large scale can be deferred by setting the right expectations with customers, and by adding guardrails like product limits and rate limits. Focusing on launching initial versions of products with just a few essential parts, maybe two or three components, gives us something to ship, test, and learn from quickly. We can always add complexity later, but only once it’s clear we need it. (https://blog.cloudflare.com/timescaledb-art/)
1. Unlike most traditional SQL databases, Impala eschews these exhaustive search query optimization strategies to simplify query planning. This is an emerging trend adopted by several database systems including Google’s F1 and Youtube’s Procella, which take a similar non-exhaustive approach to query optimization. This means that small queries can be planned quickly, avoiding situations where it takes longer to plan a query than to execute it. Impala’s planner simplifies planning in several ways. (https://www.cloudera.com/blog/technical/keeping-small-queries-fast-short-query-optimizations-in-apache-impala.html)
1. Impala’s planner does not do exhaustive cost-based optimization. Instead, it makes cost-based decisions with more limited scope (for example when comparing join strategies) and applies rule-based and heuristic optimizations for common query patterns. Exhaustive cost-based query planning depends on having up to date and reliable statistics which are expensive to generate and even harder to maintain, making their existence unrealistic in real workloads. Research has shown that, when statistics are unreliable, exhaustive optimizers can spend a lot of time planning queries and still produce very bad plans.
1. The new Catalog design means that Impala coordinators will only load the metadata that they need instead of a full snapshot of all the tables. A new event notification callback from the HMS will inform the catalog service of any metadata changes in order to automatically update the state. See the performance results below for an example of how metadata caching helps reduce latency.
1. Memory-optimized: When processing the data, Impala tries to perform everything in-memory, going so far as optimizing for CPU caches and not just memory in DRAM. With the plentiful amounts of RAM on modern servers, the vast majority of queries can be executed entirely in memory, avoiding bottlenecks like disk I/O operations. This doesn’t mean Impala is in-memory only; if memory is running low for a query, various memory-conservation strategies kick in, including spilling intermediate query results to disk. Thus very memory-intensive queries can run to completion, but other queries do not pay any performance penalty.
1. Runtime Filtering: When performing a join between two tables, any rows from one table that don’t match the join condition in the other table aren’t returned by the join operation. However before those rows get to the join operation they have to be read from storage and materialized in memory, just to be later discarded by the join. Runtime filtering is a technique to dynamically determine which rows would definitely not meet the join criteria and avoid bringing them to the join node in the first place. This technique is also used heavily by recent versions of Microsoft’s SQL Server and UW’s Quickstep. The research from these groups has provided a formal proof that a lightweight query optimization approach combined with careful placement of runtime filters will produce more optimal query plans in linear time as compared to a more complex query optimizer for the space of queries that follow a star or snowflake schema design!
1. Code Generation: Impala’s “codegen” feature provides incredible performance improvements and efficiencies by converting expensive parts of a query directly into machine code specialized just for the operation of that particular query. However this works a lot like compiling code for a programming language like C or C++, there is some time spent compiling the code before it can be used. This overhead upfront could be dramatically worthwhile when that code is going to be executed many thousands of times for each row of processed data. Compiling small chunks of a query directly with LLVM is a lot more efficient than compiling a full C or C++ program, but still takes 10s or 100s of milliseconds., For a query that isn’t accessing many rows, the compilation overhead can outweigh the benefits. Impala is aware of this tradeoff and tries to intelligently enable “codegen” based on the amount of data being accessed. We also recently added the ability for this compilation to take place asynchronously, so that the query can start producing results even before compilation is complete.


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

### Expert Generalist

출처 : https://martinfowler.com/articles/expert-generalist.html

```
(전략)

We've always felt that such desires are wrong-headed. The characteristics that we've observed separating effective software developers from the chaff aren't things that depend on the specifics of tooling. We rather appreciate such things as: the knowledge of core concepts and patterns of programming, a knack for decomposing complex work-items into small, testable pieces, and the ability to collaborate with both other programmers and those who will benefit from the software.

We think that the notion of mechanical sympathy has a broader sense in software, in that we do need to cultivate such a sympathy for any adjacent domain to the ones we are working on. When working on a database design, we need such a sympathy for the user-interface so we can construct a design that will work smoothly with the user-experience. A user-experience designer needs such a sympathy with software constraints so when choosing between similarly valuable user flows, they take into account how hard it is to build them.

(후략)
```

## 단위 테스트

* 테스트 더블(test double) : 소프트웨어 테스트 자동화에서 사용되는 소프트웨어로, 테스트가 프로덕션 코드에 의존하지 않도록 의존성을 충족시키는 역할을 한다.
  * "단위 테스트의 기술" 저자들은 테스트 더블보다 페이크(fake)가 단어가 짧아서 선호한다고 한다.
* 스텁(stub)과 목(mock)
  * 스텁은 내부로 들어오는 의존성을, 목은 외부로 나가는 의존성을 끊어준다(충족시킨다).
    * 스텁 예시 : 데이터베이스 질의 결과가 필요한 메서드를 테스트할 때 데이터베이스 질의 결과를 스텁으로 대체해서 데이터베이스의 실제 상태와는 무관하게 테스트할 수 있다. 이 때 메서드의 호출 여부는 검증하지 않는다.
    * 목 예시 : 외부 시스템과의 상호작용을 시뮬레이션하고 호출 여부나 인수를 검증하는데 사용한다. 목은 하나의 테스트에서 하나만 사용하는 것이 좋다.
  * 둘을 구분없이 부르는 경우가 흔하지만 이럴 경우 스텁이나 목을 잘못 사용하여 테스트를 유지보수하게 어렵게 만들 수 있다.
* 스텁과 목 활용 방법
  * 스텁이나 목을 사용할 때는 제어의 역전(Inversion of Control), 의존성 주입(Dependency Injection)을 활용해서 의존성을 주입한다. 그 방법에는 모듈형, 함수형, 객체지향형이 있다.
    * 모듈형 : 내장된 의존서을 쉽게 교체할 수 없을 때 테스트에서 모듈을 교체하는 방법으로 테스트할 수 있다.
    * 함수형 : 대체로 간결한 코드로 테스트를 작성할 수 있는 대신 함수를 일급 함수로 다루는 방식에 대한 이해가 필요하다. 간결하기 때문에 많은 사람들이 선택하는 방법이다. 함수를 매개변수로 전달하거나 함수를 생성하는 팩토리 함수를 전달할 수 있다.
    * 객체지향형 : 대체로 장황한 편이다. 의존성을 생성자로 전달하는데 파이썬처럼 덕 타이핑을 지원하는 경우 덜 장황하게 의존성을 전달할 수 있다.
  * "단위 테스트의 기술" 저자들은 테스트에서는 의존성 주입을 위해 프레임워크을 남용하면 테스트 코드가 오히려 복잡해지기 때문에 팩토리 함수나 헬퍼 함수를 만드는 것을 선호한다고 한다.
  * 격리 프레임워크를 활용하면 스텁과 목을 쉽게 만들 수 있는데 오남용하지 않도록 주의해야 한다. 테스트에서 여러 스텁을 사용하는 것은 괜찮지만 종료점을 대체하는 목은 하나만 사용하는 것이 좋다. 특히 목을 남용하기 쉬운데 목은 종료점이 서드 파티 의존성 호출에 대해서는 유용하지만 종료점이 반환 값이나 상태 변화일 때는 목을 사용하지 않는 편이 좋다. 
  * 변경이 잦아 격리 프레임워크로 만든 스텁으로 테스트가 자주 깨지거나 스텁을 여러 곳에서 활용하는 경우 스텁을 간단하게 직접 구현하는 편이 나을 수 있다.
* 비동기 코드를 테스트하는 방법
  * 진입점(entrypoint) 분리 : 비동기 함수 호출 결과를 받아서 처리하는 로직을 순수 함수로 분리하여 테스트한다.
  * 어댑터 분리 : 비동기 요소를 의존성으로 생각해서 비동기 요소를 분리하고 추상화해서 테스트에서는 동기로 대체한다. 
  * 자바스크립트의 타이머는 다음 방법을 활용할 수 있다.
    * 몽키 패치(monek patch) : 몽키 패치로 타이머를 테스트에서 동적으로 대체하는 방법으로 강타입 언어에서는 대단히 어려울 수 있다.
    * 프레임워크로 비활성화 : Jest같은 프레임워크는 타이머를 비활성화하는 방법을 제공한다.
* 테스트를 유지보수하기 쉽게 만드는 법칙
  * 언제 실행하든 테스트 내에서 사용된 값은 변하지 않아야 하고, 검증도 매번 같아야 한다. 따라서 이전과 같은 결과를 보장해야 한다.
  *  테스트에서 여러 스텁을 사용하는 것은 괜찮지만 종료점을 대체하는 목은 하나만 사용하는 것이 좋다.
  * 종료점이 아닌 내부 함수나 스텁을 호출했는지 검증하는 것은 잘못된 대상을 검증하는 것이므로 하지 말아야 한다.
  * 테스트에서 자주 사용되는 객체 생성은 팩퇴 함수나 헬퍼 함수를 활용한다.
  * before같은 초기화 함수는 오남용하기 쉬우므로 팩토리 함수나 헬퍼 함수를 활용한다.
  * 테스트 이름은 "진입점, 테스트하는 상황, 종료점에서 기대하는 동작" 세 가지를 넣는 것이 좋다. 그렇지 않으면 테스트 코드르를 읽어야 테스트 내용을 알 수 있다.  
* TDD에 대한 사례
  * 

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
- Module
  - 목표
    - 단일 통합 런타임 rt.jar의 종말
    - JDK 내부 구성 요소의 적절한 캡슐화 및 보호
  - 모듈 그래프
    - module-info.java (Module descriptor)에 명시된 모듈 의존성은 컴파일러와 런타임이 신뢰할 수 있다
  - module-info.java
    - exports <패키지이름> : 어떤 패키지가 모듈의 공용 API로 간주되는지를 나타내기 위한 키워드
    - exports <패키지이름> to ...
    - requires <모듈이름>
  - jmod describe $JAVA_HOME/jmods/java.base.jmod
  - jimage list $JAVA_HOME/lib/modules
  - 전이성
    - 전이성이란 모듈 A가 모듈 B를 요구하고, 모듈 B가 모듈 C를 요구할 때, 모듈 A가 자동으로 모듈 C에도 접근할 수 있게 되는 의존성 전파 메커니즘이다.
    - A가 C의 API를 직접 사용하지 않고 B만 사용한다면, A는 C를 requires할 필요가 없다.
    - 이처럼 자바 모듈 시스템에서는 기본적으로 직접 선언한 의존성만 사용할 수 있으며, 전이적 의존성을 사용하려면 `requires transitive` 키워드를 통해 명시적으로 re-export해야 한다.
    - 캡슐화와 의존성 관리를 위해 transitive는 꼭 필요한 경우(API에서 다른 모듈의 타입을 노출하는 경우)에만 사용하는 것이 좋다.
- G1 GC
  - 참고 자료
    - https://www.oracle.com/technetwork/tutorials/tutorials-1876574.html
    - https://docs.oracle.com/en/java/javase/17/gctuning/garbage-first-g1-garbage-collector1.html
    - https://www.oracle.com/technical-resources/articles/java/g1gc.html
    - https://www.redhat.com/en/blog/part-1-introduction-g1-garbage-collector
    - https://www.redhat.com/en/blog/collecting-and-reading-g1-garbage-collector-logs-part-2
  - 목표
    - 예측 가능한 중지 시간 목표를 설정하여 수백 밀리초를 초과하지 않도록 하고, 긴 가비지 컬렉션 중지를 방지합니다.
    - At its heart, the goal of the G1 collector is to achieve a predictable soft-target pause time, defined through -XX:MaxGCPauseMillis, while also maintaining consistent application throughput.
    - A general rule with G1 is that the higher the pause time target, the achievable throughput, and overall latency become higher. The lower the pause time target, the achievable throughput and overall latency become lower.
  - 활성화 : -XX:+UseG1GC
  - 특징
    - 위에서 G1의 새로운 개념인 '영역(region)'에 대해 언급했습니다. 간단히 말해, 영역은 할당된 공간 블록을 나타내며, 동일한 세대의 다른 영역과 연속성을 유지할 필요 없이 모든 세대의 객체를 수용할 수 있습니다. G1에서는 기존의 젊은 세대(Young generation)와 노년 세대(Tenured generation)가 여전히 존재합니다. 젊은 세대는 새로 할당된 모든 객체가 시작되는 에덴 공간(Eden space)과, 수집 과정에서 살아있는 에덴 객체가 복사되는 생존자 공간(Survivor space)으로 구성됩니다. 객체는 수거되거나 XX:MaxTenuringThreshold(기본값 15)로 정의된 충분한 연령에 도달하여 승격될 때까지 생존자 공간에 남아 있습니다. 노년 세대는 생존자 공간에서 XX:MaxTenuringThreshold에 도달한 객체가 승격되는 노년 공간으로 구성됩니다. 물론 이에 대한 예외가 있으며, 이는 글 후반부에 다루겠습니다. 이 영역 크기는 JVM 시작 시 계산 및 정의됩니다. 가능한 한 2048개에 가까운 영역을 가지는 원칙에 기반하며, 각 영역 크기는 1~64MB 사이의 2의 거듭제곱 단위로 설정됩니다.
    - When setting the region size, it’s important to understand the number of regions your heap-to-size ratio will create because the fewer the regions, the less flexibility G1 has and the longer it takes to scan, mark and collect each of them.
    - When the aforementioned young collection takes place, dead objects are collected and any remaining live objects are evacuated and compacted into the Survivor space. G1 has an explicit hard-margin, defined by the G1ReservePercent (default 10%), that results in a percentage of the heap always being available for the Survivor space during evacuation.
    - When young collection occurs
      - It reaches a configurable soft-margin known as the InitiatingHeapOccupancyPercent (IHOP).
      - It reaches its configurable hard-margin (G1ReservePercent)
      - It encounters a humongous allocation (this is the exception I referred to earlier, more on this at the end).
    - 실시간 수집기가 아니므로 설정된 일시 중지 시간 목표를 더 긴 시간 동안 높은 확률로 충족시키려 시도하지만, 특정 일시 중지에 대해 항상 절대적인 확신을 가지고 달성하는 것은 아닙니다.
    - 애플리케이션은 항상 젊은 세대, 즉 에덴 영역에 할당합니다. 단, 거대한 객체는 예외로 하여 직접 노년 세대에 속하는 것으로 할당됩니다.
  - 가비지 컬렉션 사이클
    - Young-only phase
      - 일반적인 Young collection과 같다. eden의 live 객체는 survivor로 evacuated된다. 그러다 threshold를 만족하면 old로 승격된다.
      - 이 단계는 Stop-the-world다.
      - Young generation의 region과 Humongous region만 회수한다.
      - Old generation이 Initiating Heap Occupancy threshold를 넘어서면 Space reclamation phase로 전환 시작
      - Concurrent start : 일반적인 Young collection과 보존할 Old generation marking을 동시에 수행
      - Remark
        - Snapshot-At-The-Beginning
        - It takes a virtual snapshot of the heap at the time of the Initial Mark pause, when all objects that were live at the start of marking are considered live for the remainder of marking. This means that objects that become dead (unreachable) during marking are still considered live for the purpose of space-reclamation (with some exceptions). This may cause some additional memory wrongly retained compared to other collectors. However, SATB potentially provides better latency during the Remark pause. The too conservatively considered live objects during that marking will be reclaimed during the next marking.
      - Cleanup
    - Space reclamation phase
      - Young generation region, Humoungous region에 더해 Old generation region을 회수한다.
    - G1 old collection - Concurrent marking cycle phases
      1. initial mark (STW) : old에 참조를 갖는 survivor region을 mark한다.
      1. root region scanning : old에 참조를 갖는 survivor region을 scan한다. STW가 아니다.
      1. concurrent marking
        - 모든 힙에서 live 객체를 찾는다.
        - evacuation 단계에서 어떤 region을 회수하는 것이 최선일지 알아내기 위한 liveness를 계산한다.
      1. remark (STW)
        - Snapshot-at-the-beginning 알고리즘으로 힙의 live 객체 marking을 완료한다.
        - 모든 region에 대해 region liveness를 계산한다.
        - 완전히 비어있는 region을 회수한다.
      1. cleaup (STW and concurrent)
        - region과 RSets을 정리한다. (STW)
        - region을 free list에 등록하는데 이건 concurrent로 동작한다.
      1. copying (STW) : G1은 liveness가 가장 낮은 region을 우선 선택해서 회수한다. live 객체를 미사용 region으로 복사한다. young generation에서만 일어나면 로그에는 "GC pause (young)"으로 남고, young과 old 모두에서 일어나면 "GC Pause (mixed)"로 로그가 남는다.
  - G1 GC는 non-humongous region은 eden에서 survivor, survivor에서 old로 복사한다.
  - G1 GC는 humongous region은 더 이상 사용하지 않으면 회수하고, 아직 사용 중이면 그대로 둔다.
  - Collection set : 회수할 리전들
  - 주요 플래그들
    - -XX:G1PeriodicGCInterval
    - -XX:NewSize
    - -XX:MaxNewSize
    - -XX:InitiatingHeapOccupancyPercent
    - -XX:-G1UseAdaptiveIHOP
  - Evacuation failure
  - Humoungous object
    - region 크가의 절반 이상인 객체
    - Cleanup pause나 Full GC에서만 회수된다.
    - -XX:G1EagerReclaimHumongousObjects : Humongous object가 원시 타입의 배열이라면 어느 단계에서든 회수를 시도한다.
    - Humongous object 할당할 때마다 IHOP을 확인한다.
    - Humongous objects are allocated to a special humongous region directly within the Old generation. This is because the cost to evacuate and copy such an object across the young generations can be too high.
    - Humongous allocations always trigger a concurrent marking cycle, whether the IHOP criteria is met or not.
  - Class unloading이 필요한 이유 : 내부적으로 계속 재배포가 일어나거나 리플렉션으로 임시 클래스를 만드는 애플리케이션에서 이를 정리하지 않으면 Metaspace가 가득차게 된다.
  - Remembered Sets (RSets) : 해당 region을 가리키는 객체 참조를 추적한다. region당 하나가 존재한다.
  - Collection Sets (CSets) : GC에서 수집될 region 집합을 가리킨다. GC 동안 CSet의 모든 live 객체는 evacuated(copied/moved)된다.
  - G1에서 Full GC가 발생하는 이유
    - Metaspace full
    - to-space exhausted
  - 권장
    - Young generation의 크기를 설정하지 마라 : -Xmn, -XX:NewRation 등을 사용하면 pause-time goal을 오버라이드해버린다.
    - Pause time goals : G1 GC는 일관된 pause-time을 갖는 incremental gc지만 대신 오버헤드가 기존 gc보다 크다. 기존의 Throughput collector가 애플리케이션 실행 시간 99%, GC 시간 1%였다면 G1 GC는 pause time을 최소화하는 대신 애플리케이션 실행 시간 90%, GC 시간 10%를 목표로 한다. 그래서 pause-time을 너무 낮게 설정하면 gc 오버헤드가 커질 수 있으므로 주의가 필요하다.
    - GC 로그에 "to-space overflow/exhausted"가 보이면 충분한 메모리가 없다는 의미이다.
    - 튜닝이 필요하면 다음 옵션을 조정해보라
      - `-XX:InitiatingHeapOccupancyPercent` : marking threshold
      - `-XX:G1MixedGCLiveThresholdPercent`, `-XX:G1HeapWastePercent` : Mixed GC 관련 조정
      - `-XX:G1MixedGCCountTarget`, `-XX:G1OldCSetRegionThresholdPercent` : old region의 CSet 조정
  - G1 - Good Throughput, controllable latency, suitable for long lived services where heap sizes are below 16GB
  - ZGC - Good Throughput, ultra-low latency, suitable for long lived services where heap sizes are above 4GB
  - https://www.youtube.com/watch?v=L68zxvl2LPY에 따르면 G1은 밸런스가 좋고, Generation ZGC가 아닌 일반 ZGC는 tail latency가 커지는 문제가 있어서 Generation ZGC를 사용해야 한다.

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
- 패키지 관리: PDM
  - PEP 582 지원
    - 기존에 사용하던 venv, virtualenv는 번거롭고 가상환경을 활성화하는 것을 잊기 쉽다.
    - PEP 582는 node_modules처럼 `__pypackages__` 폴더를 만들어서 패키지를 관리하는 프로젝트 로컬 패키지 개념을 도입했다.
  - PEP 621 지원
    - 여러 곳에 흩어진 프로젝트 메타데이터를 pyproject.toml 파일 하나에 다 모으는 표준 스키마를 제정했다.
    - PDM, Hatch 등은 PEP 621을 완벽히 지원한다.
  - 사용법
  ```bash
  mkdir my-project
  cd my-project
  
  pdm init
  
  # 기본 의존성 추가
  pdm add fastapi uvicorn
  
  # 개발 의존성 추가
  pdm add -dG dev pytest black isort mypy
  
  # 특정 그룹으로 의존성 추가
  pdm add -dG test pytestcov pytest-asyncio
  
  # 의존성 보기
  pdm list
  pdm list --tree
  
  # 의존성 정보 보기
  pdm info fastapi
  
  # 개발 코드 작성
  mkdir -p src/my-project
  touch src/my-project/main.py
  
  # 테스트 코드 작성
  mkdir -p tests/my-project
  
  # 개발 서버 실행
  pdm run start
  
  # 테스트 실행
  pdm run test
  
  # 의존성 업데이트
  pdm update
  
  # 캐시 정리
  pdm cache clear
  ```

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

### VS Code

- 단축키
  - 파일 및 탐색
    - Ctrl + P - 파일 빠르게 열기
    - Ctrl + Shift + P - 명령 팔레트 열기
    - Ctrl + B - 사이드바 토글
    - Ctrl + ` - 터미널 토글
  - 편집
    - Ctrl + D - 같은 단어 다중 선택
    - Alt + Click - 다중 커서
    - Ctrl + / - 주석 토글
    - Alt + 위/아래 - 줄 이동
    - Shift + Alt + 위/아래 - 줄 복사
  - 코드
    - Ctrl + Shift + O - 심볼로 이동
    - F12 - 정의로 이동
    - Alt + F12 - 정의 미리보기
    - F5 - Debugging
    - Ctrl + F5 - Run without debugging
  - 기타
    - Ctrl + Shift + E - 파일 탐색기 포커스
    - Ctrl + 1 - 첫 번째 에디터 포커스
    - Ctrl + Alt + I - 코파일럿 포커스