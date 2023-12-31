## CHAPTER 18 최적의 아키텍처 스타일 선정

```
인상깊은 내용)
아키텍처 결정 기준에서 중요한 내용을 다루고 있다고 느꼈으며
어떤 시스템을 구현하고 싶은지에 따라 트레이드오프가 따르는 결정이 필요하다고 느꼈다.
도메인이나 기술적인 부분을 제외하고 외적인 기준에서 "조직 문제", "프로세스, 팀, 운영 문제에 관한 지식" 등도 충분히 고려해서 결정 기준에 넣어야 하는 부분도 흥미로웠다.
```

최적의 아키텍처 스타일은 상황에 따라 다르다. 조직 내부의 수많은 팩터들과 어떤 소프트웨어를 구축하는지에 따라 맥락이 달라지므로, 아키텍처 특성, 도메인 고려 사항, 전략적 목표, 그 밖의 다양한 것들의 트레이드오프를 고려하고 분석한 마지막 결과로 아키텍처 스타일을 선택해야 한다.

### 18.1 아키텍처 '유행'은 계속 변한다

아키텍처 스타일은 여러 가지 팩터들로 인해 그때그때 계속 변한다.

#### 과거를 돌아보다

새로운 아키텍처 설계는 과거 아키텍처 스타일에서 발견된 결함이 반영된 경우가 많다. 

#### 생태계의 변화

끊임없는 변화는 소프트웨어 개발 생태계의 바람직한 특성이다. 시간에 따라 불변인 것은 하나도 없다.

#### 새로운 기능

새로운 기능이 출현하면 아키텍처는 단순히 어떤 도구를 다른 도구로 대체하는 정도가 아닌, 완전히 새로운 패러다임으로 전환될 수 있다. 생태계가 지속적으로 변화하면서 새로운 도구과 기능들 역시 수시로 등장한다. 아키텍트는 새로운 도구는 물론 새로운 패러다임 역시 예의주시해야 한다.

#### 가속

생태계는 끊임없이 변할 뿐만 아니라 그 변화의 속도도 계속 빨라지고 있다. 새로운 도구는 새로운 엔지니어링 프랙티스를 창출하고 이는 다시 새로운 설계와 기능으로 이어진다.

#### 도메인 변경

비즈니스가 계속 진화하고 타 회사와 합병되면서 개발자가 소프트웨어를 개발하는 도메인 역시 계속 변화한다.

#### 기술 변화

기술이 진화할수록 조직은 최소한 그 변화의 흐름의 일부라도 따라잡으려고 한다.

#### 외부 팩터

소프트웨어 개발과 관련된 요인이 조직의 변화를 가져오는 경우도 있다.

### 18.2 결정 기준

도메인 설계 구조의 원인이 될 만한 모든 요소를 종합적으로 고려해야 한다. 

#### 도메인

운영 아키텍처 특성에 영향을 미치는지 파악해야 한다. 아키텍트가 도메인 전문가일 필요는 없지만, 설계하는 도메인에서 중요한 파트에 대해 최소한의 지식은 갖고 있어야 한다.

#### 구조에 영향을 미치는 아키텍처 특성

도메인과 다른 외부 요소를 지원하는 데 필요한 아키텍처 특성을 정확하게 밝혀내야 한다.

#### 데이터 아키텍처

아키텍트와 DBA는 데이터베이스, 스키마 등 데이터에 관한 문제를 의논해야 한다. 데이터 설계가 아키텍처 설계에 미치는 영향도를 미리 파악해야 한다.

#### 조직 문제

특정 클라우드 이용료가 설계를 가로막는 장애물이 되거나, 개방형 솔루션과 통합 아키텍처에 무게를 둘 수 밖에 없는 경우 등

#### 프로세스, 팀, 운영 문제에 관한 지식

소프트웨어 개발 프로세스, 운영팀과의 소통 (또는 소통 결핍), QA 프로세스 등의 영향. 애자일 성숙도가 결여된 조직에서 애자일 기반 엔지니어링 프랙티스에 의존하는 아키텍처 스타일을 도입하면 큰 어려움이 따르게 된다.

#### 도메인/아키텍처 동형성

아키텍처의 토폴로지와 잘 맞는 문제 영역이 있다. 예로, 마이크로커널 아키텍처 스타일은 아키텍처적으로 플러그인 형태의 커스터마이징이 가능하므로 맞춤성이 필요한 시스템과 잘 어울린다.

#### 모놀리스냐 분산이냐

아키텍처 퀀텀 개념을 이요해서 단일 아키텍처 특성만으로도 설계에 부족함이 없는지 시스템 파트별로 상이한 아키텍처 특성이 필요한지 판단해야 한다.

#### 데이터를 어디에 둘 것인가?

모놀리식은 하나 또는 소수의 관계형 데이터베이스를 전제로 하지만, 분산 아키텍처에서는 어느 서비스가 어떤 데이터를 저장할 지 결정해야 한다. 아키텍트는 전체 아키텍처의 데이터 흐름에 대해 충분히 고려하고 설계해야 한다.

#### 서비스 간 통신은 동기, 비동기 중 어떤 스타일로 할 것인가?

아키텍트는 가급적 설계, 구현, 디버깅 문제가 비교적 적은 동기 통신을 기본으로 하되, 필요한 경우에 비동기 통신을 사용하는 것이 좋다.

> TIP Use synchronous by default, asynchronous when necessary.

### 18.3 모놀리스 사례 연구: 실리콘 샌드위치

실리콘 샌드위치를 도메인 분할된 컴포넌트와 기술 분할된 컴포넌트, 두 가지 상이한 컴포넌트로 설계를 했고 이 두 가지 설계를 비교해보면서 각각의 트레이드오프를 분석해 본다.

#### 18.3.1 모듈러 모놀리스

단일 퀀텀으로 배포된 단일 데이터베이스 기반의 도메인 중심 시스템이다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/dda82217-1d65-4931-9d5b-07136036dcf6)

단일 웹 기반 유저 인터페이스로 구현한 단일 관계형 데이터베이스 기반의 모놀리스이다. 도메인 컴포넌트 단위로 테이블과 기타 데이터베이스 자산을 분리하고 나중에 요구사항에 따라 분산 아키텍처로 쉽게 마이그레이션 될 수 있도록 설계해야 한다.

아키텍처 스타일 자체는 커스터마이징을 할 수 없기 때문에 원하는 기능이 생기면 도메인 설계의 일부로 넣어야 한다. 개발자가 개별적으로 커스터마이징한 결과물을 업로드할 수 있도록 override 엔드포인트를 설계했다.

#### 18.3.2 마이크로커널

아키텍처 특성 중 하나는 맞춤성이었으므로 도메인/아키텍처 동형성을 검토 후 마이크로커널 형태로 구현할 수도 있다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/0c4f8162-977f-4156-9aaf-da9f42cccaa9)

도메인과 데이터를 신중하게 동기화하면 나중에 분산 아키텍처로 코어를 마이그레이션 할 수 있다. 플러그인들이 다른 플러그인과 커플링될 일은 없으므로 각 플러그인 따로 떨어져 자신의 데이터를 유지할 수 있다.

프런트엔드를 위한 백엔드Backends for Frontends(BFF) 패턴을 응용해서 API 레이어를 마이크로커널 어댑터로 사용하는 독특한 설계 방법도 있다. 일반적은 정보는 백엔드가 제공하고 BFF 어댑터는 이 정보를 프런트엔드 장치에 적합한 포맷으로 바꾸는 것이다. BFF 어댑터를 만들면 마이크로커널 스타일만의 풍부한 유저 인터페이스가 가능하고 향후 다른 장치들까지 확장 지원이 가능하다.

실리콘 샌드위치는 엄청난 성능이나 탄력성을 요구하지 않고 오래 걸릴 작업이 없으므로 통신 방식은 동기식으로도 충분하다.

### 18.4 분산 아키텍처 사례 연구: GGG

아키텍처의 여러 부분에 따라 상이한 아키텍처 특성을 필요로 한다. 가용성 확장성의 경우 입찰자와 경매인 등 역할마다 다르다.

어느 정도의 규모, 탄력성, 성능, 그외 운영 아키텍처 특성이 요구사항에 명시되어 있으므로 세부적인 수준까지 고도의 커스터마이징이 가능한 패턴을 선택해야 한다.
저수준의 이벤트 기반 또는 마이크로서비스 아키텍처를 고려해 봤을 때, 이벤트 기반 아키텍처는 통신 스타일 즉 오케스트레이션 혹은 코레오그래피 방식이냐에 따라 구분하고,  마이크로서비스는 다양한 운영 아키텍처 특성을 보다 더 잘 지원한다.

마이크로서비스에서 성능 요구사항을 달성하는 건 쉽지 않지만, 아키텍트가 이 요건을 수용하도록 설계해서 약점을 보완할 수 있다. 예로, 마이크로서비스는 원래 속성상 높은 수준의 확장성을 제공하지만, 아키텍트는 오케스트레이션을 많이 사용하는지 과도한 데이터 분리를 하는지 파악해서 성능에 영향을 미치는 문제를 해결하는 방식으로 보완할 수 있다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/7c1a0a03-a32a-48f0-9861-40086aac22b1)

GGG의 세 가지 고유 인터페이스

- 입찰자: 온라인 경매에 참가한 많은 입찰자
- 경매인: 경매 당 한 사람
- 스트리머: 동영상 및 입찰 스트리밍 서비스

GGG의 아키텍처의 서비스들

- BidCapture: 온라인 입찰자의 입찰을 캡쳐해서 BidTracker로 비동기 전송
- BidStreamer: 입찰 정보를 읽기 전용 스트림으로 스트리밍
- BidTracker: AuctioneerCapure, BidCapture 양쪽에서 입찰을 추적
- AuctioneerCapture: 경매인을 위해 입찰을 캡쳐
- AuctionSession: 각 경매의 워크플로 관리
- Payment: 경매가 완료된 후 결제 정보를 처리하는 서드파티 결제 서비스
- VideoCaputure: 라이브 경매의 비디오 스트림을 캡쳐
- VideoStreamer: 경매 동영상을 온라인 입찰자에게 스트리밍

여기서 비동기 통신을 선택한 이유는 서비스마다 상이한 운영 아키텍처 특성을 감안한 결과이다.

최종 분석 결과로 5개의 퀀텀으로 설계할 수 있다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/0aa0a3cd-ca5c-4b11-bb03-9edf264984b7)

이 설계는 각 서비스에 대응되는 Payment, Auctioneer, Bidder, BidderStreams, BidTraker 퀀텀을 포함한다.

이것이 GGG 설계의 정답도 아니고 당연히 유일무이한 설계도 아니다. 심지어 이게 최선의 설계best possible design이라고도 생각할 수 없다. 적어도 트레이드오프가 가장 나쁜 것 중에서 제일 나은 설계라고 볼 수 있다. 마이크로서비스, 이벤트와 메시지를 잘 사용하면  향후 개발과 확장이 용이한 기반을 다질 수 있다.