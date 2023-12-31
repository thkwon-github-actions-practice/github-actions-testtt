## 4. 아키텍처 특성 정의

어떤 문제를 소프트웨어로 해결하려면 아키텍트는 먼저 시스팀 요구사항을 취합하고 그것을 구현하 데 다양한 기술을 소프트웨어 개발 프로세스에 따라 정한다.  

그러나 이밖에도 아키텍트는 소프트웨어 솔루션을 설계할 때 많은 부분을 고려해야 한다.

아키텍트는 개발팀과 함께 도메인 또는 비즈니스 요구사항을 정의할 수 있지만, 주로 소프트웨어로 처리할 일 중 도메인 기능과 직접적인 관련이 없는 모든 것들  

즉 아키텍처 특성을 정의, 발견, 분석하는 일을 한다.

아키텍처 특성은 다음 세 가지 기준을 충족한다.

* 비도메인 설계 고려 사항을 명시한다.
* 설계의 구조적 측면에 영향을 미친다.
* 애플리케이션 성공에 (절대적으로) 중요하다.

**비도메인 설계 고려 사항을 명시한다.**  

애플리케이션 설계 시 애플리케이션으로 처리할 일은 구체적인 요구사항으로 정리한다.

아키텍처 특성은 이 요구사항을 구현하는 방법, 어떤 선택을 하게 된 이유와 관련된 운영/설계 기준을 명시한다.

**설계의 구조적 측면에 영향을 미친다.**

프로젝트 담당 아키텍트가 아키텍처 특성을 기술하는 주된 이유는 '이 아키텍처 특성은 어떤 특별한 구조적 요소를 고려해야 하는가?'하는 설계 고려 사항 때문이다.  

**애플리케이션 성공에 (절대적으로) 중요하다.**

애플리케이션이 무수히 많은 아키텍처 특성을 전부 다 지원할 수 있겠지만, 사실 그러면 안된다.  

지원하는 아키텍처 특성을 한 가지만 늘려도 그만큼 설계 복잡도는 가중되니까요. 가급적 아키텍처 특성을 적게 선정하는 일도 아키텍트의 중요한 책무이다.

우리는 아키텍처 특성을 명시적특성과 암묵적특성으로 분류합니다.

암묵적 특성은 요구사항 정의서에는 거의 안나오지만 프로젝트 성공을 위해 꼭 필요한 특성들이다.

명시적 아키텍처 특성은 요구사항 정의서나 다른 지침서에 기재된다.

### 4.1 아키텍처 특성 목록

아키텍처 특성은 모듈성 같은 저수준 코드의 특성부터 확장성, 탄력성 같은 복잡한 운영 문제까지 소프트웨어 시스템의 넓은 범위에 골고루 존재한다.

규모와 범위는 방대하지만 아키텍트는 보통 아키텍처 특성을 넓은 범주로 나눈다.  

#### 4.1.1 운영 아키텍처 특성

운영 아키텍처 특성은 성능, 확장성, 탄력성, 가용성, 신뢰성 등의 능력을 말한다.

|용어| 정의|
|---|---|
|가용성| 시스템이 얼마나 오랫동안 사용 가능해야 하나?|
|연속성|재해복구능력|
|성능|스트레스 테스트, 피크 분석, 기능의 사용 빈도 분석, 필요 용량, 응답 시간|
|복구성|비즈니스 연속성 요구사항|
|신뢰성/안전|시스템에 페일 세이프가 필요한가?|
|견고성|프로그램 실행 중 인터넷 접속 끊김, 정전, 하드웨어 등 에러 및 경계조건을 감당하는 능력|
|확장성|유저 수, 요청 수가 늘어나도 시스템이 그에 맞는 성능을 발휘 하는 능력|

운영 아키텍처 특성은 운영 및 데브옵스와 많은 부분에서 중첩되며, 많은 소프트웨어 프로젝트에서 이런 관심사는 교차점을 형성한다.

#### 4.1.2 구조 아키텍처 특성

아키텍처는 코드 구조에도 심혈을 기울여야 하며, 일반적으로 우수한 모듈성, 컴포넌트 간 커플링 제어, 가독성 높은 코드, 그 밖의 내부 품질 평가 등 코드 품질 문제를 전담합니다.

|용어| 정의|
|---|---|
|설정성|최종 유저가 소프트웨어 설정을 쉽게 바꿀 수 있는가?|
|신장성|새로운 기능을 삽입하는 일의 중요성|
|설치성|필요한 모든 플랫폼에 시스템을 얼마나 쉽게 설치할 수 있는가?|
|활용성/재사용|공통 컴포넌트를 여러 제품에서 활용할 수 있나?|
|지역성|데이터를 입력/조회하는 화면에서 다국어가 지원되는가?|
|유지보수성|시스템을 얼마나 쉽게 변경/개선할 수 있나?|
|이식성|하나 이상의 플랫폼에서 시스템을 실행할 수 있나?|
|지원성|애플리케이션은 어느 정도의 기술 지원을 필요로 하나?|
|업그레이드성|이 애플리케이션의 구 버전을 새 버전으로 쉽고 빠르게 업그레이드 할 수 있는가?|

#### 4.1.3 아키텍처 공통 특성

쉽게 분류할 수 있는 범주에 속하는 아키텍처 특성들도 있는 반면, 중요한 설계 제약조건과 고려사항은 대부분 따로 분류하기 어려운 경우가 많다.  

|용어| 정의|
|---|---|
|접근성|색맹,청각 장애인 등 모든 유저가 접근하는 데 불편함이 없나?|
|보관성|데이터를 따로 아카이빙해야 하나, 아니면 일정 시간 경과 후 삭제해야 하나|
|인증|유저가 본인이 맞다는 것을 증명하기 위해 필요한 보안 요구사항|
|인가|유저가 애플리케이션에서 정해진 기능만 사용할 수 있도록 강제하는 보안 요구사항|
|합법성|시스템 운영상 법적 제약조건이 있는가?|
|프라이버시|회사 내부 임직원의 트랜잭션을 외부에 드러내지 않는 기능|
|보안|데이터를 암호화한 후 데이터베이스에 보관해야 하나?|
|사용성/성취성|유저가 애플리케이션을 이용하여 원하는 목적을 달성하기 위해 필요한 교육/훈련 수준|

*아키텍처 특성은 어떻게 나열해도 불완전한 목록이 될 수밖에 없고, 소프트웨어마다 고유한 팩터를 바탕으로 중요한 아키텍처 특성이 도출될 수도 있다.*

실제로 ISO에서 정의한 목록을 봐도 비슷하거나 목록자체가 불완전한 모습을 볼 수 있다.

### 4.2 트레이드오프 및 나쁜 것 중에서 제일 나은 아키텍처

지금까지 열거한 아키텍처 특성들은 여러 가지 이유로 일부만 애플리케이션에서 지원 가능하다.

1. 지원되는 특성마다 설계 노력이 필요하고 구조적으로도 지원되어야 한다.
2. 각 아키텍처 특성이 다른 특성에 영향을 미치는 경우가 많다는 사실이 더 큰 문제이다.

아키텍트가 설계하기로 결정한 아키텍처 특성 하나하나가 전체 설계를 복잡하게 만들 가능성을 폼고 있다.

따라서 시스템을 설계하며 모든 아키텍처 특성을 빠짐없이 최상으로 반영하기란 불가능에 가깝고 아키텍트가 내린 결정은 상충되는 여러 문제들이 뒤얽힌 트레이드오프로 귀결되는 경우가 많다.

> "최고의 아키텍처를 고집하지 말고 나쁜 것 중에서 제일 나은 아키텍처를 선택해라"

아키텍처 특성을 너무 욕심내면 모든 비즈니스 문제를 해결하려고 시도하는 일반적인 솔루션이 되어버린다.

그러나 그런 아키텍처는 설계하기가 대단히 까다롭다.  

아키텍트가 좋은 아키텍처를 설계하기 위해선 꾸준하게 설계를 해보는 것이 좋다.

반복의 가치는 애자일 소프트웨어 개발에서도 가장 중요한 교훈중 하나로 아키텍처뿐만 아니라 모든 레벨의 소프트웨어 개발에서도 적용된다.

### 느낀점

처음 아키텍처 특성을 읽어가며 적고 나서 모든 걸 반영하고 싶어하는 욕심 그리고 정답에 가까워지고 싶어하는 생각을 했는데..

트레이드오프, 불가능에 가깝다는 이야기..

항상 최악이라는 것이 아니라 그 때 선택할 수 있는 최선의 아키텍처를 설계하기 위해서 항상 노력하고 다양한 방면으로 기술을 쌓아야 한다..

#### 논의사항

다들 경험해보신 적 있으신지 모르겠지만, 아키텍처뿐만 아니라 뭔가 정답 코드가 있을 것 같고, 개발에서 제대로된 패스나 좋은 구조,,?를 욕심내고 그런 것에 대한 강박을 가진 적이 있는데.. 다들 그런 생각에서 벗어나신 경험이나 계기가 궁금합니다.  
