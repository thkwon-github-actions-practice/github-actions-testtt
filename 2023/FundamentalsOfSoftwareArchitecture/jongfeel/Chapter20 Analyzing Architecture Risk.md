## CHAPTER 20 아키텍처 리스크 분석

```
논의 주제)
내용 정리 중간에 의견을 적기도 했지만
이벤트 스토밍을 경험한 걸 비춰봤을때 "xxx 스토밍"이라는 행위가
구성원들이 한 가지 주제를 가지고 집중해서 논의하고 이해해서 결정을 하는 좋은 방법이라고 느껴졌다.
다시 생각해 보면 브레인 스토밍도 여러 아이디어를 제시한다는 점에서 출발만 조금 다를 뿐
그 이후로 논의, 이해, 설득, 결정의 과정은 동일한 것으로 봐서 기회가 되면 잘 해봐야 겠다는 생각이 들었다.

다른 분들은 "XXX 스토밍" 경험이 있는지와 어떤 점이 좋았었는지 얘기해 보면 좋겠습니다.
```

아키텍처 리스크 분석은 아키텍트의 핵심 활동 중 하나로, 리스크를 꾸분히 분석하여 아키텍처의 내부 결함을 바로잡고 리스크를 줄이는 일이다.

### 20.1 리스크 매트릭스

리스크가 높고 낮음에 대한 분류는 주관적인 경우가 많아 리스크 매트릭스risk matrix를 활용하면 주관성을 낮추고 특정한 아키텍처 영역에서 리스크를 찾아내는 데 도움이 된다.

전체 리스크 영향도Overall impace of risk와 발생 가능성Likelihood of risk occuring 두 가지 차원으로 리스크를 평가한 뒤, 낮음(1), 중간(2), 높음(3) 등급을 매긴 것이다. 숫자와 매트릭스의 각 숫자를 곱하면 리스크를 객관적인 수치로 정량화할 수 있다. 1,2는 낮음 3,4는 중간, 6~9는 높음을 나타낸다.
인쇄된 책에서는 회색 음영으로 표기했지만, pdf 원본은 green, yellow, red 이다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/3ec741c7-7ba9-40f5-b93d-d836fe3835de)

> TIP 리스크 매트릭스로 리스크를 가늠할 때에는 먼저 영향도를 고려한 다음 발생 가능성 차원을 생각해 보자.

### 20.2 리스크 평가

리스크 매트릭스를 활용하면 리스크 평가risk assessment를 작성할 수 있다. 리스크 평가는 맥락에 따라 유의미한 평가 기준에 대해 전체 아키텍처 리스크를 요약한 리포트이다.

보통 서비스나 도메인 영역의 평가 기준assessment criteria이 포함된다. 20.1 챕터와 달리 흑백으로 인쇄하는 경우와 색약자를 배려해서 음영으로 나타내는게 좋다는 내용이 적혀 있다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/03cd228d-8a1f-48c4-9a30-81794ae2deba)

리스크 매트릭스로 정량화한 리스크는 평가 기준별로, 서비스 또는 도메인 영역별로 누적치를 계산할 수 있다. 상대 수치를 비교하면 어떤 리스크 범주나 도메인 영역에서 리스크가 개선됐는지 혹은 악화됐는지 파악할 수 있다.

그림의 모든 항목에 대한 리스크 분석 결과를 이런 방식으로 표현하는 경우는 거의 없다. 주어진 맥락에 맞게 전달하려는 메시지를 잘 표현하려면 필터링이 꼭 필요하다. 아래 그림과 같이 리스크가 높은 영역만 표시하면 전체적인 신호 대 잡음비signal-to-noise radio(SNR)가 개선되고 시스템이 좋은 상태인지 나쁜 상태인지 드러난다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/c3a85bab-ec9f-41da-85d5-4b3b85064ddf)

하지만 이 그림만 봐서는 특정 시점의 리스크 포착만 할 수 있을 뿐, 리스크의 방향성에 대해서는 알 수 없다. 방향을 표시하면 어느 방향이 좋은 쪽인지 알기가 어렵다는 문제도 있다.

따라서 리스크 등급 옆에 플러스(+), 마이너스(-) 같은 보편적인 방향 기호를 사용한다. 아래 그림에서 마이너스 부호는 상황이 나빠지고 리스크가 높아지는 추세이고, 플러스 부호는 점차 개선되는 중이다. 아무 부호도 없으면 리스크가 안정적이라서 특별한 상태 변화가 없다는 뜻이다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/183e1496-b04c-42ac-ad32-871bebc6ec76)

플러스, 마이너스도 헷갈린다면 진행 방향의 리스크 등급 번호와 화살표를 병기하는 것도 좋은 방법이다. 아래 그림은 방향이 명확하게 표시되므로 별도의 범례가 필요가 없다. 화살표에 색깔을 입히면 (빨간색은 악화, 초록색은 개선) 리스크의 방향성이 좀 더 분명해진다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/e23e2692-f10d-44ea-ac54-b7b40523df74)

리스크의 평가 기준을 객관적으로 분석하면 흐름이 보이고 방향성을 알 수 있다.

### 20.3 리스크 스토밍

아키텍트 한 사람이 리스크 영역을 모두 살펴보기 어렵고 완벽하게 알고 있기도 어렵기 때문에 리스크 스토밍risk storming을 하는 것이 좋다.

리스크 스토밍은 특정 범위 내에 있는 아키텍처 리스크를 찾아내는 협력적인 활동collaborative exercise이다. 아키텍트와 함께 개발자가 참여하면 구현 관점에서 리스크를 짚어볼 수 있으므로 아키텍처를 더 선명하게 이해할 수 있다.

리스크 스토밍의 수행 과정은 개별 파트individual part와 협력 파트collaborative part가 공존한다.
개발 파트는 리스크 매트릭스를 이용해서 각자 알아서 아키텍처 리스크를 할당한다.
협력 파트는 전체 참가자가 모여 리스크 영역에 대해 공감하고 어떻게 리스크를 줄일 수 있는지 논의한다.
여기서 두 파트 모두 아키텍처 다이어그램을 사용하고 최신 상태로 업데이트 해서 모든 참가자들이 볼 수 있게 관리한다.

아래 아키텍처를 보면서 리스크 스토밍 과정을 살펴본다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/f8884308-2adf-4b59-83a5-c27e270fee89)

리스크 스토밍은 식별identification, 합의consensus, 완화mitigation의 세 활동으로 이루어진다.
식별 활동은 개별적이고 비협력적으로 진행하고
합의와 완화는 모든 참가자가 모여 작업하는 협력적 활동이다.

#### 20.3.1 식별

각 참여자가 아키텍처 내부의 리스크 영역을 개인적을 식별하는 활동

- 아키텍트가 리스크 스토밍을 주관하고 아키텍처 다이어그램, 리스크 스토밍 분석 대상 영역, 협력 파트를 진행할 날짜와 장소를 정한다.
- 참가자는 리스크 매트릭스를 이용해 개별적으로 아키텍처를 분석하고 리스크를 낮음, 중간, 높음으로 분류한다.
- 참가자는 색상별 포스트잇 메모지에 리스크 번호를 각각 기재한다.

보통 한 가지 특정 부분만 분석하지만 인력, 일정 등의 사정에 따라 한번에 여러 부분을 분석하는 경우도 있다.

> TIP 리스크 스토밍은 가급적 한 가지 부분으로 제한한다. 그래야 참가자가 집중하고 동일한 아키텍처 영역에서 식별되는 다수의 리스크 영역과 헷갈리지 않는다.

#### 20.3.2 합의

합의는 참가자 모두가 아키텍처 내부의 리스크에 대해 뜻을 함께 한다는 목표를 생각해 보면 매우 협력적인 활동이다.
아키텍트는 모든 참가자에게 아키텍처 영역 다이어그래메 리스크를 배치해달라고 요청한다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/bf997b95-3c69-4b46-8151-e91e80a621dd)

포스트잇을 붙인 후에 협력 파트가 시작된다. 목표는 리스크 영역을 분석하고 그게 리스크가 맞는지 합의를 이끌어내는 것이다.

1 일래스틱 로드 밸런서: 두 명이 중간(3), 한 명이 높음(6)으로 식별
2 푸시 확장 서버: 한 명이 높음(9)
3 MySQL 데이터베이스: 세 명이 중간(3)
4 레디스 캐시: 한 명이 높음(9)
5 몽고DB 로깅: 세 명이 낮음(2)
6 다른 영역은 리스크가 없는 것으로 따로 포스트잇을 붙이지 않음

1번 일래스틱 로드 밸런서는 참가자별로 리스크 식별리 다르다. 참가자들이 서로 왜 그렇게 리스크를 식별했는지 이유를 묻고 설명을 한다. 각자의 생각에 대한 설명과 주장이 이어지게 되고 그러면 장시간 논의를 거쳐 마지막 참가자가 식별한 리스크 높음(6)을 중간(3)으로 낮추기로 한다. 하지만 앞의 두 참가자는 마지막 참가자가 식별한 리스크를 못봤을 가능성이 있으므로 합의 활동이 필요하다.

2번 푸시 확장 서버 역시 한 참가자만 리스크 높음(9)으로 식별했으므로 다른 두 참가자가 이유를 묻는다. 리스크 높음을 식별한 참가자는 예전에 부하가 큰 상황에서 푸시 확장 서버가 지속적으로 다운되는 현상을 목격했다는 대답을 하고 여기서 리스크 스토밍의 진가가 발휘단다고 볼 수 있다. 참가자들이 모여 이런 대화를 하지 않으면 아무도 그런 리스크가 있을 줄 몰랐을테니까

```
의견)
별 생각 없이 읽으면 너무도 당연한 얘기를 하고 있는게 아닌가...? 라고 생각할 수 있지만
하나의 제품/서비스의 아키텍처를 논하는 자리에는 다양한 개발자가 참여해서 의견을 나누게 되므로 확실히 책에서 언급한 리스크 스토밍의 진가를 얻게 될 가능성이 높다고 볼 수 있다.
비슷한 활동으로 이벤트 스토밍이라는 것도 있는데 아키텍처 레벨이 아닌 도메인 레벨에서 해볼 수 있는 활동으로 서로 의견을 물어 가면서 이벤트 중심의 데이터 흐름을 파악할 수 있으므로 제품/서비스에 대한 이해 및 개념 공유 측면에서 확실히 도움이 되는 활동이긴 하다.
```

4번은 흥미로운데, 한 명이 레디스 캐시가 리스크 높음(9)으로 식별했지만 다른 참가자는 아니라고 봤기 때문이다. 당연히 남은 두 참가자가 이유를 물었을 때 "레디스 캐시가 뭔가요?" 라는 반문을 한다면, 이 참가자에게 레디스는 알려지지 않았기 때문에 이 영역에서 리스크가 높은 것이라고 볼 수 있다.

> TIP 검증되지 않았거나 알려지지 않은 기술은 해당 부분에서 리스크 매트릭스를 사용할 수 없으니 가장 높은 리스크 등급(9)을 매기자

4번의 경우 개발자가 리스크 스토밍 세션에 참여하는 것이 얼마나 도움이 되는지 잘 나태낸 사례이다. 개발자는 아키텍처에 대해 더 많은 것을 알 수 있어서 좋고, 아키텍트는 한 참가자가 해당 기술을 전혀 몰랐다는 사실 자체가 리스크였음을 깨닫게 된다.

합의 활동은 모든 참가자가 의견을 함께 할 때 까지 반복하고 포스트잇을 모두 통합해서 아래 그림 처럼 최종 결과를 도출한다.

![image](https://github.com/jongfeel/BookReview/assets/17442457/811f26b1-21bb-4ec6-9360-5ef9134ab541)

#### 20.3.3 완화

아키텍처에서 리스크를 줄이려면 일반적으로 아키텍처의 특정 영역을 변경 또는 개선하는 작업이 필요하다.

합의와 마찬가지로 협력 파트인 완화 활동에서 참가자는 리스크를 줄이거나 없앨 방법을 모색한다. 아키텍처를 완전히 바꿔야 할 수도 있찌만, 처리량 병목 이슈를 줄이기 위해 배압 큐back pressure queue를 추가하는 등 간단한 아키텍처 리팩터링 만으로 해소되는 경우도 있다.

아키텍처를 어떻게 변경하든 모든 작업에는 추가 비용이 들어가므로 리스크를 줄이기 위해 그 맣난 비용을 부담할 가치가 있는지 결정한다. 참가자들이 데이터베이스를 클러스터링 하고 단일 데이터베이스를 물리적인 여러 서버로 분리하는 작업을 통해 데이터베이스 리스크를 완화할 수 있다고 의견을 모았다. 그러나 리스크를 줄이는 대가로 $20,000를 초과하는 솔루션 비용을 지불해야 한다면 아키텍트는 비즈니스 이해관계자들과 절충안을 논의해야 한다. 비용 대비 값어치가 없다고 하면 협의를 통해 클러스터링은 제외하고 물리 데이터베이스를 두 파트로 나누느 걸로 $8,000만 들여서 해결하는 걸로 리스크를 줄이자는 설득을 할 수 있다.

아키텍트와 비즈니스 이해관계자들간의 협상에도 리스크 스토밍은 상당한 영향을 미칠 수 있다.

### 20.4 애자일 스토리 리스크 분석

리스크 스토밍은 아키텍처는 물론, 다른 소프트웨어 개발 분야에도 응용할 수 있다.

스토리 그루밍story grooming(PO가 개발할 기능에 대해 대략적으로 팀원들과 리뷰하는 행위)을 하면서 애자일 이터레이션에 유저 스토리를 완료하는 데 전체적으로 어떤 리스크가 있는지 알아보는 용도로 활용할 수 있다.

이걸 리스크 매트릭스를 사용해서 스토리가 완료되지 않을 경우 전체 영향도와 스토리가 완료되지 않을 가능성으로 식별해서 만들어볼 수 있다. 동일한 아키텍처 리스크 매트릭스를 스토리에 활용해서 리스크가 높은 스토리를 찾아내고 그런 스토리를 주의 깊게 추적해서 우선 순위를 둔다.

### 20.5 리스크 스토밍 예시

리스크 스토밍을 통해 얼마나 강력한지, 어떻게 전체 시스템 아키텍처를 개선하는지 예제를 통해 살펴본다.

환자들의 다양한 건강 상태에 대해 간호사가 조언을 해주는 콜 센터 시스템이 있다.
요구사항은 다음과 같다.

- 질문을 받으면 간호사나 환자에게 의료 문제를 안내하는 서드파티 진단 엔진을 사용한다.
- 환자는 콜 센터에 전화를 걸어 간호사와 통화하거나 간호사 없이 직접 진단 엔진에 액세스하는 셀프 서비스 웹사이트를 이용한다.
- 전국적으로 250명의 간호사와 수십만 명에 달하는 셀프 서비스 환자를 동시에 지원할 수 있어야 한다.
- 간호사는 환자의 의무 기록을 열람할 수 있지만, 환자는 자신의 의무 기록을 볼 수 없다.
- 의무 기록에 관한 미국 의료 정보 보호법Health Insurance Portability and Accountability Act(HIPAA)를 준수해야 한다. 즉, 간호사 이외의 그 누구도 의무 기록을 열람할 수 없다.
- 전염병과 독감이 유행하는 시즌에 데이터 요청이 급증해도 시스템이 이를 감당해야 한다.
- 간호사 프로필(예: 외국어 가능)에 따라 통화가 연결되어야 한다.
- 서드파티 진단 엔진은 초당 약 500개의 요청을 처리할 수 있어야 한다.

아래 그림은 아키텍트가 설계한 고수준 아키텍처이다.

<img width="454" alt="image" src="https://github.com/jongfeel/BookReview/assets/17442457/8451a7b5-52d1-484e-bce8-9d0d4de83b56">

이 시스템은
사례 관리 서비스,
간호사 프로필 관리 서비스,
의무 기록 인터페이스,
외부 서드파티 진단 엔진,
이렇게 4개 주요 서비스로 구성된다.

아키텍트는 수 차례 아키텍처를 검토했고 구현할 준비가 되었다고 확신한다. 자가 평가 차원에서 한 번 더 요구사항을 살펴보고 아키텍처 다이어그램을 재검토한 다음 가용성, 탄력성, 보안 측면에서 어느 정도의 리스크가 있는지 살펴본다.

#### 20.5.1 가용성

1차 리스크 스토밍 세션에서는 가용성에 집중하기로 한다. 리스크 스토밍에 참가한 사람들은 식별, 협력 활동의 결과로 리스크 매트릭스를 만들어서 리스크 영역을 제시했다.

<img width="458" alt="image" src="https://github.com/jongfeel/BookReview/assets/17442457/975a2b6d-a300-4330-8cd1-a67b6a128cfc">

참가자들은 데이터베이스가 다운되면 간호사가 사례 기록을 수기로 작성할 수 있지만 데이터베이스를 사용할 수 없으니 통화 라우터는 작동하지 않으리란 점에 동의했다. 이런 리스크를 완화하려면 간호사 프로필 정보가 저장된 데이터베이스 클러스터와 단일 인스턴스 형태의 사례 기록용 데이터베이스 2개로 분리하는 것이 낫다는 결론을 내렸다.

외부 시스템은 마음대로 제어할 수 없기 때문에 가용성 관리가 훨씬 어렵다. 이런 리스크를 완화하는 방법은 시스템별로 SLA(서비스 수준 계약)나 SLO(서비스 수준 목표)가 명시된 문서를 확인해 보는 것이다. SLA는 법적 구속력이 있는 공식 계약서인 반면 SLO는 그렇지 않기 때문이다. 연구 결과 자료에 따르면 진단 엔진의 SLA가 99.99% 가용성을(연간 다운타임 52.60분), 의무 기록 시스템이 99.9% 가용성(연간 다운타임 8.77시간)을 보장한다고 나와 있다. 그렇다면 상대적으로 리스크가 없다고 봐도 무방하다.

이후 변경된 아키텍처 다이어그램을 업데이트 했다. 데이터베이스 분리와 SLA 명시가 되어 있다.

<img width="462" alt="image" src="https://github.com/jongfeel/BookReview/assets/17442457/fe58b085-af18-410d-97a6-6b6c922dcb23">

#### 20.5.2 탄력성

간호사는 250명에 불과하지만 셀프 서비스 파트도 진단 엔진과 간호사 정보를 액세스할 수 있으므로 진단 인터페이스에 요청이 몰릴 수 있다. 

모든 참가자는 만장일치로 진단 엔진 인터페이스를 리스크 높음(9)으로 식별했다.

앰뷸런스 패턴Ambulance Pattern을 응용하여 셀프 서비스 보다 간호사에게 더 높은 운선 순위를 부여하는 방법을 사용한다. 그러면 메시지 채널이 2개 필요한데, 리스크 완화에 도움은 되지만 대기 시간 문제는 여전히 남아 있다. 참가자들은 배압 지점을 제공하는 큐 기술 외에도 발병에 관한 특정 진단 질문을 캐시함으로써 진단 엔진 인터페이스에 도달하는 호출을 줄일 수 있다고 판단했다.

아래는 이런 의견이 반영된 아키텍처 다이어그램이다.

<img width="452" alt="image" src="https://github.com/jongfeel/BookReview/assets/17442457/91193302-b75e-4bb7-b6a9-c058162e1473">

#### 20.5.3 보안

HIPAA 규체 요구사항으로 의무 기록 열람은 간호사만 열람이 가능하도록 안전하게 관리해야 한다.

참가자는 전원 진단 시스템 API 게이트웨이를 리스크 높음(6)으로 식별했다. 그래서 유저 유형별(관리자, 셀프 서비스/진단, 간호사)로 API 게이트웨이를 사용하면 관리자용 웹 유저 인터페이스나 셀프 서비스용 유저 인터페이스의 호출이 의무 기록 시스템까지 도달하지 못하게 막을 수 있다는 의견을 냈고 이후 아래와 같은 최종 아키텍처를 완성했다.

<img width="461" alt="image" src="https://github.com/jongfeel/BookReview/assets/17442457/68993f1d-c030-4f9f-b6cb-8f06d3b28290">

리스크 스토밍은 1회성 프로세스가 아니라, 프로덕션에서 발생하기 전에 리스크 영역을 포작하고 미리 그 해결 방법을 찾는, 시스템이 살아 숨쉬는 내내 계속 반복하는 과정이다. 리스크 스토밍 활동을 얼마나 자주할지는 변경 빈도, 아키텍처 리팩터링 활동, 아키텍처의 점진적 개발 등 여러 팩터에 따라 달라진다. 일반적으로 주요 기능이 추가된 직후 혹은 매 이터레이션이 끝나는 시점에 특정 차원에 대해 리스크 스토밍을 한다.