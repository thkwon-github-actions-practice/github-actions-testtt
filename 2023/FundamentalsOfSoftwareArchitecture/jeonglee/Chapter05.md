## 5. 아키텍처 특성 식별

아키텍처를 구상하거나 기존 아키텍처의 타당성을 검증할 때 제일 먼저 해야하는 이은 아키텍처 특성을 식별하는 일 이다.  

아키텍처 특성을 정확하게 식별하기 위해선 해당 도메인을 잘 알고 있어야 하며, 도메인 이해관계자들과 협력하여 도메인 관점에서 중요한 것들을 결정해야 한다.

아키텍트는 적어도 **도메인 관심사**, **요구사항**, **암묵적 도메인 지식** 이렇게 세가지 출저에서 아키텍처 특성을 밝혀낸다.  

### 5.1 도메인 관심사에서 아키텍처 특성 도출

도메인 이해관계자와 협력해서 주요 아키텍처 특성을 정의하는 한 가지 팁은, 최종 목록을 가능한 한 짧게 하는 것이다.  

아키텍처에서 가장 흔한 실수, 안티패턴은 모든 아키텍처 특성을 지원하는 제네릭 아키텍처를 설계하려 하는 것이다.  

아키텍처 특성 하나하나가 시스템의 설계를 복잡하게 만드는 요인이기 때문에 너무 많은 아키텍처 특성을 수용하면 아키텍트, 개발자가 의도했던 문제 영역의 해결을 시도하기도 전에 아키텍처가 너무 복잡해져버린다.  

따라서 아키텍처 특성의 개수에 연연하지 말고 가급적 설계를 단순화하는게 좋다.  

아키텍트와 도메인 이해관계자는 애초에 다른 사람이기 때문에 의견과 시점이 다를 수 밖에 없다.  

가장 중요한 특성을 순위를 매겨 진행하게 되면 마찰과 갈등이 생겨서 만장일치로 돌아가는 경우가 적다.

따라서 최종 목록을 뽑은 뒤 각각 3개씩 뽑아서 좀 더 중요한 특성이 뭔지 고민해보는 시간을 가지는 것이 좋다.

아키텍처의 특성은 핵심 도메인 이해관계자들의 의견을 듣고 도메인 관점에서 무엇이 중요한지 의견을 교환하면서 정리 된다.

문제가 없어보이지만 도메인 이해관계자들과 아키텍트의 언어는 다르다.  

아키텍트는 확장성, 상호운용성, 내고장성, 학습성, 가용성을 운운하지만 이해관계자들은 인수병합, 고객 만족, 출시 시점등의 경쟁우위를 논한다.  

이러한 문제를 해결하기 위해 저자는 도메인 관심사를 아키텍처 특성으로 옮겨 적은 표를 제공한다.

|도메인 관심사|아키텍처 특성|
|:---|:---|
|인수 합병|상호운용성, 확장성, 적응성, 신장성|
|출시 시기|민첩성, 시험성, 배포성|
|유저 만족|성능, 가용성, 내고장성, 시험성, 배포성, 민첩성, 보안|
|경쟁 우위|민첩성, 시험성, 배포성, 확장성, 가용성, 내고장성|
|시간 및 예산|단순성, 실행성|

### 5.2 요구사항에서 아키텍처 특성 도출

요구사항 정의서에 명시된 문장에서 도출한 아키텍처 특성도 있다.  

*예상 유저수와 그에 따른 확장 문제는 보통 도메인 관심사에서 빠지지 않는 단골 손님이다..*

아키텍트가 알고 있는 도메인 지식에서 도출되는 특성들도 있는데, 이것이 아키텍트가 도메인 지식을 갖고 있으면 이로운 이유이다.  

초보 아키텍트가 도메인에 관한 설명을 보고 아키텍처 특성을 도출하는 연습을 할 수 있도록 아키텍처 카타를 고안했다.  

### 5.3 사례 연구: 실리콘 샌드위치

실리콘 샌드위치 카타를 예로 들어 아키텍트가 요구사항을 바탕으로 아키텍처 특성을 도출하는 방법을 알아보자

- 설명
  - 실리콘 샌드위치는 전국 가맹점을 보유한 샌드위치 브랜드로 온라인 주문 시스템을 구축하려 한다.
- 유저
  - 앞으로 수천명, 어쩌면 수백만 명에 달할 지도 모른다.
- 요구 사항
  - 유저가 주문을 하면 샌드위치를 픽업하러 갈 시간 및 상점까지 가는 경로를 전달받는다(교통 정보가 포함된 여러 외부 지도 서비스와 연계는 필수).
  - 배달 서비스가 가능한 지점은 기사를 보내 샌드위치를 유저에게 배달한다.
  - 모바일 기기에서도 이용 가능하다.
  - 전국 어느 지점이나 이용 가능한 프로모션/스페셜 행사를 제공한다.
  - 특정 지점에서만 이용 가능한 로컬 프로모션/스페셜 행사를 제공한다.
  - 온라인 결제, 대면 결제. 배송 시 결제 등 다양한 결제 옵션을 제공한다.
- 부가 콘텍스트
  - 샌드위치 지점은 가맹점이므로 소유자가 다 다르다.
  - 모회사는 머지않아 해외 시장도 진출할 계획이다.
  - 이 회사는 값싼 인력을 고용해 이윤을 최대화하는 것이 목표다.

요구사항 하나하나가 여러 아키텍처 특성과 연관이 있을 수 있고 없을 수 있다.  

여기서 아키텍트는 도메인 요구사항을 충족하는 전체 시스템을 코드 레벨로 설계하는 것이 아니라, 설계, 특히 구조와 관련이 있거나 영향을 미치는 것들을 찾아내는 것이다.  

먼저 아키텍처 특성이 될 만한 것과 암묵적인 것으로 분류한다.

#### 5.3.1 명시적 특성

명시적 아키텍처 트성은 필요한 설계의 일부로서 요구사항 정의서에 기술된다.  

아키텍트가 가장 먼저 봐야할 부분은 `유저 수`다.  

지금은 수천 명 정도라고 생각했지만 나중에 수백만명에 이를 수 있다고 한다.  

따라서 **확장성**, 즉 유의미한 성능 저하 없이 다수의 동시 유저를 처리하는 능력이 무엇보다 중요한 아키텍처 특성으로 보인다.  

순간적으로 폭증하는 유저 요청을 처리하려면 **탄력성**도 필요하다.

확장성과 탄력성은 한몸처럼 나타날 때도 많지만 제약조건은 각각 다르다.  

확장성은 좋지만 탄력성은 좋지 못한 시스템도 있다.  

*호텔 예약시스템*

그럼 샌드위치 시스템에선..? 점심시간에 몰리는 유저들을 생각하여 확장성도 고려해야 한다..

1. 유저가 주문을 하면 샌드위치를 픽업하러 갈 시간 및 상점까지 가는 경로를 전달받는다(교통 정보가 포함된 여러 외부 지도 서비스와 연계는 필수).

외부 지도 서비스는 연계 지점에 해당하므로 신뢰성과 같은 특성에 영향을 미칠 수 있다.  

서드파티 시스템에 의존하는 시스템은 서드파티 시스템 호출이 실패할 경우 전체 시스템 안정성이 타격을 입는다.  

그러나 아키텍트는 과도하게 특성을 설정하지 않도록 유의할 필요도 있다.  

외부 지도 서비스가 다운되면 실리콘 샌드위치 사이트 전체가 중단될까 교통정보가 빠진 덜 쓸모 있는 서비스가 제공될까?  

2. 배달 서비스가 가능한 지점은 기사를 보내 샌드위치를 유저에게 배달한다.

별다른 아키텍처 특성이 필요하지 않다.

3. 모바일 기기에서도 이용 가능하다.  

이 요구사항은 애플리케이션을 설계할 때 이식성이 좋은 웹 애플리케이션과 다양한 네이티브 웹 애플리케이션중 어느 쪽으로 개발할 것인가, 방향성을 결정하는 것처럼 큰 비중을 차지한다.

예산, 인력을 고민하여 아키텍처 특성을 정의할 수 있지만 아키텍트는 결코 혼자 움직여선 안 되며, UX 설계자, 도메인 담당자, 기타 도메인 이해관계자들과 충분한 협의를 거치는 것이 좋다.

4. 전국 어느 지점이나 이용 가능한 프로모션/스페셜 행사를 제공한다.
5. 특정 지점에서만 이용 가능한 로컬 프로모션/스페셜 행사를 제공한다.

4,5번은 프로모션과 스페셜 행사에 관한 커스터마이징 가능 여부에 관한 요구사항이다.

1번 요구사항은 유저 주소에 맞는 교통정보의 커스터마이징을 의미하므로 아키텍트는 이 세가지 요구사항을 토대로 맞춤성을 도출할 수 있다.  

6. 온라인 결제, 대면 결제, 배송 시 결제 등 다양한 결제 옵션을 제공한다.

온라인 결제는 보안이 당연하게 필요하지만 이 요구사항만 봐서는 어느정도의 보안이 필요한지 잘 모르겠다..

7. 샌드위치 지점은 가맹점이므로 소유자가 다 다르다.

이 요구사항은 아키텍처 비용에 제약을 가한다. 아키텍트는 단순하거나 기능이 조금 빠진 아키텍처로도 충분한지 타당서을 미리 확인해야 한다.

8. 모회사는 머지않아 해외 시장도 진출할 계획이다.

이 요구사항은 아키텍처의 국제화를 고려해야 한다.  

9. 이 회사는 값싼 인력을 고용해 이윤을 최대화하는 것이 목표다.

중요하지 않지만 아키텍처 특성보다 설계와 더 깊은 연관이 있다.

요구사항 정의서에서 도출한 세 번째 아키텍처 특성은 **성능**이다.  

#### 5.3.2 암묵적 특성

요구사항 정의서에는 따로 없는 아키텍처 특성도 있지만 이들은 각각 중요한 설계 요소가 된다.  

가용성은 시스템에서 마땅히 지원되어야 할 암묵적인 아키텍처 특성으로, 유저는 샌드위치 사이트에 접속할 수 있어야 한다.

마찬가지로 사이트를 문젱없이 사용하려면 신뢰성 역시 반드시 필요하다..  

보안은 모든 시스템에 공통적인 암묵적 특성이다.

아키텍처 특성은 서로 연관되어 움직이므로 중요도에 따라 우선순위는 매우 달라질 수 있다.  

실리콘 샌드위치의 마지막 아키텍처 특성으로는 요구사항 곳곳에 해당되는 맞춤성을 꼽을 수 있다.  

레시피, 로컬판매, 약도 등 문제 영역의 여러 부분을 유저의 의도에 맞게 다시 정의해야 하므로 커스터마이징이 원활하게 지원되는 아키텍처가 필요하다.

#### 설계 대 아키텍처, 그리고 트레이드오프

실리콘 샌드위치 카타에서 맞춤성을 시스템의 일부로 식별하는 아키텍트도 있겠지만, 문제는 이것이 아키텍처냐 설계냐,는 것이다. 아키텍처는 구조적 컴포넌트를 나타내지만, 설계는 아키텍처 내부에 속한다.  

아키텍트는 애플리케이션 스스로 커스텀 로직을 지원하도록 맞춤성을 아키텍처 구조 설계에 반영하지 않을 수 있다  

개발자는 어떤 방법을 쓰더라도 기능을 구현할 수 있으므로 아키텍트는 아키텍처 특성을 정확하게 발견하려고 너무 스트레스를 받을 필요는 없다.  

물론 중요한 구조적 요소를 정확하게 식별하면 단순 우아하게 설계가 가능하다.  

> **아키텍처에서 최고의 설계는 없다. 오직 나쁜 것중에서 제일 나은 트레이드오프들만 있을 뿐**

### 느낀점

아키텍트의 역할과 설계의 차이점이 조금 헷갈렸는데 설계보다는 좀 더 인지적인 능력이 많이 필요한 것 같다.  

책에서도 강조하는 커뮤니케이션적인 능력이 있어야 다른 파트와 소통하고 협업할 수 있을 것 같다.

#### 논의사항
