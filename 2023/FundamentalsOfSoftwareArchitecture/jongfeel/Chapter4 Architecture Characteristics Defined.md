## CHAPTER 4 아키텍처 특성 정의

```
논의내용)
여기 소개된 아키텍처 특성 중에 자신이 하고 있는 일에서 큰 비중을 차지하고 있는 특성이 어떤 것이 있는지 얘기해 보면 좋겠습니다.

저의 경우는 최근에 구조적인 아키텍처 특성에서 재사용성과 이식성에 대한 작업을 했는데 기존 홀로렌즈2 기반(UWP)의 제품을 메타 퀘스트 프로(Android)로 전환하는 작업에서 아키텍처의 특성을 살려서 했던 경험이 있습니다. 
```

어떤 문제를 소프트웨어로 해결하려면 아키텍트는 먼저 시스템 요구사항을 취합하고 그것을 구현하는 데 필요한 다양한 기술을 소프트웨어 개발 프로세스에 따라 정의한다.

```
의견)
어떤 문제를 소프트웨어로 해결한다는 측면에서 많은 함축적 의미를 담고 있다고 본다.
이건 기술적인 문제를 넘어선 컴퓨팅 사고 능력과 문제 해결을 위한 도메인 지식과 요구사항을 해결할 수 있는 경험적인 능력을 포함한다고 생각한다.
```

성공적인 아키텍처 구축에 중차대한 관심사임을 나타내고 시스템을 전체적으로 바라보며 그 중요성을 폄하하지 않는 아키텍처 특성architecture characteristic이라는 용어를 선호한다.

아키텍처 특성은 다음 세 가지 기준을 충족한다.

- 비도메인nondomain 설계 고려 사항을 명시한다. (명시적)
- 설계의 구조적 측면에 영향을 미친다. (암묵적)
- 애플리케이션 성공에 (절대적으로) 중요하다. (아키텍처 특성)

**비도메인 설계 고려 사항을 명시한다**

애플리케이션 설계 시 애플리케이션으로 처리할 일은 구체적인 요구사항으로 정리한다.
아키텍처 특성은 이 요구사항을 구현하는 방법, 어떤 선택을 하게 된 이유오 관련된 운영/설계 기준을 명시한다.

**설계의 구조적 측면에 영향을 미친다**

아키텍처 특성을 기술하는 주된 이유는, '이 아키텍처 특성은 어떤 특별한 구조적 요소를 고려해야 하는가?' 하는 설계 고려 사항 떄문이다.

결제 시스템의 두 가지 사례

- 서드파티 결제 프로세서: 결제 처리를 한 곳에서 처리한다면 아키텍트가 특별히 구조에 신경 쓸 일은 없다.
- 애플리케이션 내부 결제 처리: 애플리케이션이 직접 결제 처리를 한다면 중요한 보안 문제를 구조적으로 분리하기 위해 특정한 모듈이나 컴포넌트, 서비스를 설계해야 한다.

**애플리케이션 성공에 (절대적으로) 중요하다**

지원하는 아키텍처 특성을 한 가지만 늘려도 그만큼 설계 복잡도는 가중된다. 가급적 아키텍처 특성을 적게 선정하는 일도 아키텍트의 중요한 책무이다.

아키텍처 특성에서 암묵적 아키텍처 특성은 요구사항 정의서에는 거의 안 나오지만 프로젝트 성공을 위해 꼭 필요한 특성들이다. 예로 가용성, 신뢰성, 보안은 거의 모든 애플리케이션의 근간이지만 설계 문서에는 좀처럼 등장하지 않는다.

### 4.1 아키텍처 특성 (일부) 목록

아키텍처 특성은 모듈성 같은 저수준 코드의 특성부터 확장성, 탄력성 같은 복잡한 운영 문제까지 소프트웨어 시스템의 넓은 범위에 고루 존재한다.

#### 4.1.1 운영 아키텍처 특성

운영 아키텍처 특성operational architecture charcteristic은 성능, 확장성, 탄력성, 가용성, 신뢰성 등의 능력을 말한다.

가용성availabiltiy
연속성continuity
성능performance
복구성recoverability
신뢰성/안전reliability/safety
견고성robustness
확장성scalability

운영 아키텍처 특성은 운영 및 데브옵스와 많은 부분에서 중첩되며, 많은 소프트웨어 프로젝트에서 이런 관심사는 교차점을 형성한다.

#### 4.1.2 구조 아키텍처 특성

아키텍트는 코드 구조에도 심혈을 기울여야 하며, 일반적으로 우수한 모듈성, 컴포넌트 간 커플링 제어, 가독성 높은 코드, 그 밖의 내부 품질 평가 등 코드 품질 문제를 전담한다.

설정성configurability
신장성extensiblity
설치성intallability
활용성/재사용leverageability/reuse
지역성locality
유지보수성maintainability
이식성portability
지원성supportability
업그레이드성upgradeability

#### 4.1.3 아키텍처 공통 특성

쉽게 분류할 수 있는 범주에 속하는 아키텍처 특성들도 있는 반면, 중요한 설계 제약조건과 고려 사항은 대부분 따로 분류하기가 어려운 경우가 많다.

접근성accessilility
보관성archivability
인증authentication
인가authorization
합법성legal
프라이버시privacy
보안security
사용성/성취성usability/archievability

아키텍처 특성은 불완전한 목록일 수 밖에 없고, 소프트웨어마다 고유한 팩터를 바탕으로 중요한 아키텍처 특성이 도출될 수도 있다.

완벽한 표준 목록은 없지만 국제 표준 기가International Organization for Standardization(ISO)가 발표한 기능별 목록을 확인해 보면 여태까지 나열한 특성들과 중복되거나 카테고리 목록이 불완전한 편이다

ISO 정의에서 일부 발췌한 용어를 정리한다.

**성능 효율**

알려진 조건에서 리소스 양에 비례하는 성능 측정값, 시간 특징time behaviour, 리소스 사용resource utilization, 능력capacity 등이 포한된다.

**호환성compatibility**

제품, 시스템, 컴포넌트가 다른 제품, 시스템, 컴포넌트와 정보를 교환하고 동일한 하드웨어/소프트웨어 환경을 공유하면서 필요한 기능을 수행할 수 있는 정도, 공존coexistence(환경과 리소스를 다른 제품과 공유하면서 효율적으로 필요한 기능을 수행할 수 있음)과 상호운용성interoperability(둘 이상의 시스템에 정보를 교환, 활용 가능한 정도)이 포함된다.

**사용성usability**

유저가 시스템을 원하는 목적에 맞게 효과적으로, 효율적으로, 만족스럽게 사용할 수 있는 정도, 적합성 인지도, 학습성, 유저 에러 방지, 접근성이 포함된다.

**신뢰성reliability**

주어진 기간 동안 특정 조건에서 시스템이 기능하는 정도, 성숙도maturity, 가용성availability, 내고장성fault tolerance, 복구성recoverability이 포함된다.

**보안security**

사람들, 다른 제품, 시스템이 자신의 인증 레벨에 맞게 데이터를 엑세스할 수 있게끔 소프트웨어가 정보를 보호하는 정도, 기빌성confidentiality, 무결성integrity, 부인 방지nonrepudiation, 책임 소재accountability, 진위authenticity가 포함된다.

**유지보수성maintainability**

개발자가 얼마나 효율적으로 소프트웨어를 고쳐 개선/발전시키고 계속 변화하는 환경이나 요구사항에 맞게 적용할 수 있는가를 나타낸다. 모듈성modularity, 재사용성reusability, 분석성analyzability, 수정성modifiability, 시험성testability이 포함된다.

**이식성portability**

개발자가 하드웨어, 소프트웨어, 또는 다른 운용 환경에 있는 시스템, 제품, 컴포넌트를 다른 곳에 옮길 수 있는 정도, 적응성adaptability, 서치성intallability, 교체성replaceability이 포함된다.

**기능 적합성functional suitability**

주어진 조건에서 제품이나 시스템을 가동할 때 명시/암묵적인 요구사항을 충족하는 정도, 이 특성은 아래의 하위 특성들로 나뉘어진다.

- 기능 완전성functional completeness: 제공되는 기능들이 전체 작업과 유저 목표를 얼마나 커버하는가?
- 기능 정확성functional correctness: 제품이나 시스템이 올바른 결과를 어느 정도로 정확하게 제공하는가?
- 기능 타당성functional appropriateness: 주어진 작업과 목표를 얼마나 쉽게 달성할 수 있는가?

소프트웨어 아키텍처는 모호한 것들 투성이이지만, 도메인 주도 설계 분야의 조언을 따르고 실천하길 권장하며, 동료들끼리 용어 때문에 오해하는 일이 없도록 서로 보편적인 언어를 정해서 사용해야 한다.

### 4.2 트레이드오프 및 나쁜 것 중에서 제일 나은 아키텍처

여기에서 언급한 아키텍처 특성들은 일부만 애플리케이션에서 지원 가능하다.

- 지원되는 특성마다 설계 노력이 필요하고 구조적으로도 지원돼야 한다.
- 각 아키텍처 특성이 다른 특성에 영향을 미치는 경우가 많다는 사실이 더 큰 문제이다.

시스템을 설계하며 모든 아키텍처 특성을 빠짐없이 최상으로 반영하기란 불가능에 가깝다. 아키텍트가 내린 결정은 상충된느 여러 문제들이 뒤얽힌 트레이드오프로 귀결되는 경우가 많다.

아키텍처 특성을 너무 욕심내면 모든 비즈니스 문제를 해결하려고 시도하는 일반적인 솔루션이 되어 버린다. 그런 아키텍처는 설계하기가 대단히 까다롭기 때문에 실현 가능성이 낮다.

아키텍트는 가능한 한 아키텍처 설계를 꾸준히 조금씩 반복해보는 게 좋다. 반복의 가치는 애자일 소프트웨어 개발에서도 가장 중요한 교훈 중 하나로, 아키텍처뿐만 아니라 모든 레벨의 소프트웨어 개발에도 적용된다.