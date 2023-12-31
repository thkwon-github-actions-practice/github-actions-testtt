## 1. 서론

소프트웨어 아키텍트란 무슨 직업일까..?

다른 직업에 비해 커리어패스가 불분명한지..?

1. 많은 사람들이 직업 자체에 대한 정의를 잡지 않았으며 추상적으로 말하곤 한다.  

> 아키텍처는 중요한 것들에 관한 것이다. 그게 무엇이든 말이다.

2. 소프트웨어 아키텍트는 매우 방대한 분야를 포괄하며 업무의 범위또한 매우 넓다.  

3. 소프트웨어 개발 생태계는 워낙 빠르게 발전하는 분야이고 소프트웨어 아키텍처는 끊임없이 변화하기 때문

**소프트웨어 아키텍처는 본질 자체가 동적이다.**

4. 소프트웨어 아키텍처에 관한 자료는 대부분 역사적인 연관성을 강조한다.

정리하면 소프트웨어 아키텍트는 **끊임없이 변화하는 생태계안에서 뭔가 결정을 내리는 사람**들입니다.

아키텍처를 공부하는 사람들이 명심해야 하는 부분은 **예술**과 마찬가지로 콘텍스트로서만 이해할 수 있다는 것입니다.  

모든 아키텍처는 그 콘텍스트의 결과물이라는 사실.

### 1.1 소프트웨아 아키텍처란?

시스템의 청사진, 이정표정도의 개념이고, 아키텍트는 시스템을 `분석`한다면 과연 무엇을 분석한다는 것 일까?

아키텍처를 바라보는 한 가지 방법으로 아키텍처 특성, 아키텍처 결정, 설계 원칙, 시스템 구조의 형태로 보는 방법

1. 시스템 구조란?

마이크로서비스, 레이어드, 마이크로 커널 같은 아키텍처 스타일을 말한다.

2. 아키텍처 특성이란?

일반적으로 시스템의 기능과 직교하는 성공 기준을 결정

가용성, 신뢰성, 시험성, 확장성, 보안, 민첩성, 내고장성, 탄력성, 복구성, 성능, 배포성, 학습성..  

나열된 특성이 시스템 기능에 관한 지식을 필요로 하는 것은 아니지만, 시스템이 올바르게 동작하기 위해서는 반드시 필요한 것이다.

3. 아키텍처 결정이란?

아키텍처 결정은 시스템 구축에 필요한 규칙들을 정의한 것

> ex) 아키텍트가 레이어드 아키텍처에서는 프레젠테이션 레이어가 데이터베이스를 직접 호출하지 못하게 비지니스와 서비스 레이어에서만 데이터베이스를 액세스할 수 있다고 결정하는 식이다.

4. 설계 원칙이란?

아키텍처 결정이 반드시 지켜야 할 규칙이라면 설계 원칙은 가이드라인이다.

### 1.2 아키텍트에 대한 기대치

앞서 말한 것과 같이 아키텍트의 역할은 단순하게 정의하기 어렵기 때문에 대부분의 사람들이 아키텍트에게 바라는 `기대치`에 집중한다.

역할, 직책, 직무 상관없이 소프트웨어 아키텍트에게 바라는 핵심적인 요구사항은 다음과 같다.

1. 아키텍처 결정을 내린다.
2. 아키텍처를 지속적으로 분석한다.
3. 최신 트렌드를 계속 유지한다.
4. 아키텍처 결정의 컴플라이언스를 보장한다.
5. 다양한 기술과 경험에 노출된다.
6. 비지니스 도메인 지식을 보유한다.
7. 대인 관계 기술이 뛰어나다.
8. 정치를 이해하고 처세를 잘한다.

한마디로 뛰어난 사람..!  

유능한 소프트웨어 아키텍트가 되려면 이렇게 사람들이 자신에게 바라는 요구사항을 충분히 실천하려는 마음가짐을 가져야 한다.

#### 1.2.1 아키텍처 결정을 내린다

아키텍트는 아키텍처와 설계 원칙을 결정하고 팀, 부서뿐만 아니라 회사 전체의 기술 결정을 가이드하는 사람입니다.

첫 번째 요구사항은의 키워드는 `가이드`이다.

아키텍트는 **기술 선택을 가이드하는 사람**이지, 정해주는 사람이 아니다..!

이러한 과정은 생각보다 어렵기 때문에 자신이 내린 결정에 대한 자문을 해봐야 한다.

#### 1.2.2 아키텍처를 지속적으로 분석한다

아키텍트는 끊임없이 아키텍처와 현재 기술 환경을 분석하고 이를 개선하기 위한 해결 방안을 제시합니다.

3년전에 정의한 아키텍처가 지금도 얼마나 현실성 있는지 평가하는 아키텍처 역동성에 관한 요구사항이다.

경험에 비추어 봐도 예전 아키텍터를 지속적으로 분석하는 데 에너지를 집중하는 아키텍트는 별로 보지 못했다.

그래서 대부분의 아키텍처 구조가 쇠락하는 양상을 보이며 특히 성능, 가용성, 확장성 등의 필수 아키텍처 특성에 영향을 미치는 코드를 개발자가 작성하거나 설계를 변경할 때 이런 증상이 나타난다..

여기서도 TDD 교조주의에 관한 내용이 나오는 것 같다.

개발자의 위치에서의 테스팅과 아키텍처의 거시적 관점이 다르다.  

따라서 아키텍트라면 지속적인 분석을 통해 애플리케이션을 계속 적절하게 유지할 수 있는 능력을 갖고 있어야 한다.

#### 1.2.3 최신 트렌드를 계속 유지한다

아키텍트는 항상 최신 기술과 업계 트렌드를 따라가야 합니다.

아키텍트는 최신 기술과 업계 트렌드를 따라가야 하는, 한층 더 중요한 요구사항을 달성해야 한다.

아키텍트가 결정한 것들은 대개 오래 지속되고 바꾸기도 어렵다,,!

#### 1.2.4 아키텍처 결정의 컴플라이언스를 보장한다

아키텍트는 아키텍처 결정과 설계 원칙의 컴플라이언스를 보장해야 한다.

*컴플라이언스 보장이란, 아키텍트가 정의하고 문서화하여 전달한 아키텍처 결정과 설계 원칙들을 개발팀이 제대로 준수하고 있는지 지속적으로 확인한다는 뜻*

#### 1.2.5 다양한 기술과 경험에 노출된다

아키텍트는 다양한 기술, 프레임워크, 플랫폼, 환경에 노출되어야 합니다.

아키텍트가 모든 프레임워크, 플랫폼, 언어에 통달해야 할 필요는 없지만, 적어도 다양한 기술을 거리낌없이 쓸 줄 알아야 한다..

그러려면 아키텍트 자신이 가장 익숙한 영역을 점점 넓혀가는 것이 가장 좋다.

한 가지 기술이나 플랫폼에만 올인하는 것은 안일한 태도..

#### 1.2.6 비지니스 도메인 지식을 보유한다

아키텍트는 어느 수준 이상의 비즈니스 도메인 전문가여야 한다.

유능한 소프트웨어 아키텍트는 기술은 물론이고 문제 영역의 비즈니스 도메인도 잘 알고 있다.

*해결하고자 하는 문제 영역, 핵심 비즈니스 요구사항*

#### 1.2.7 대인 관계 기술이 뛰어나다

아키텍트는 팀워크, 조정, 리더십을 포함한 대인관계 기술이 뛰어나야 합니다.

#### 1.2.8 정치를 이해하고 처세를 잘한다

아키텍트는 기업 내부의 정치적 분위기를 이해하고 적절하게 잘 처신할 줄 알아야 합니다.

### 1.3 아키텍처의 교차점 그리고

소프트웨어 아키텍처는 지난 10년 동안 더 많은 책임과 관점을 아우르는 방향으로 확대되었습니다..

페츠닷컴의 사례처럼 탄력성이 필요한 이유와 사례가 만들어낸 반면교사..?

#### 1.3.1 엔지니어링 프랙티스

과거 소프트웨어 아키텍처는 소프트웨어를 제작하는 개발 프로세스와 분리돼 있었습니다.  

폭포수 모델, (스크럼, 익스트림 프로그래밍, 린, 크리스털 같은)애자일등 소프트웨어를 구축하는 인기 있는 방법론은 소프트웨어 아키텍처에 그리 큰 영향을 끼치지 못했습니다.

그러나 발전을 거듭하며 엔지니어링 프랙티스와 소프트웨어 개발 프로세스는 구분을 해야함을 깨닫게 되었습니다.

프로세스는 팀을 어떻게 구성하고 관리하는지 회의는 어떻게 하고 워크플로 조직은 어떻게 운영할지 등 사람을 조직하고 상호작용하는 총체적인 기법입니다.

반면 소프트웨어 엔지니어링 프랙티스는 프로세스와 무관하게 가시적이고 반복 가능하 혜택을 주는 실천론입니다.

지속적 통합은 특정 프로세스에 의존하지 않고 검증된 엔지니어링 프랙티스입니다.

엔지니어링 프랙티스에 집중하는 것은 중요하다

1. 소프트웨어 개발 분야는 보다 성숙한 다른 엔지니어링 체계에 있는 많은 특성들이 빠져 있습니다.
2. 소프트웨어 개발의 아킬레스 건 중 하나는 추정이다.

*추정에 대한 공감.*

> '알려진 기지의 것들', 즉 우리가 알고 있다는 사실을 알고 있는 것  
> '알려진 미지의 것들', 즉 우리가 모르고 있다는 사실을 알고 있는 것들  
> '알려지지 않은 미지의 것들' 즉 우리가 모른다는 사실도 모르는 것

여기서 `알려지지 않은 미지의 것들`은 소프트웨어에서 필연적인 것이다.  

때문에 빅 디자인 업 프린트(설계부터 확실하게)를 실천하기 어렵다..

> 모든 아키텍처는 알려지지 않은 것들 때문에 자꾸 되풍이 되는데, 애자일은 단지 이것을 인지해서 더 빨리 수행하는 것이다.

#### 1.3.2 운영/데브옵스

데브옵스의 출현과 더불어 최근 두드러진 아키텍처와 유관 분야 간의 차이점은 아키텍처 공리를 다시 음미한 결과입니다..?

오랫동안 외주를 맡기는 형태로 진행되다 최근에 운영문제와 아키텍처를 결합한 새로운 형태의 아키텍처를 실험하기 시작 -> 마이크로서비스

마이크로서비스 아키텍처 스타일을 정립한 아키텍트들은 운영 관심사는 운영으로 처리해야 더 매끄럽다는 사실을 깨닫게 되었습니다.

#### 1.3.3 프로세스

소프트웨어 아키텍처는 소프트웨어 개발 프로세스에 거의 직교적이라는 공리가 있습니다..

소프트웨어를 구축하는 방법은 사실 소프트웨어 아키텍처에 별다른 영향을 끼치지 않습니다.

#### 1.3.4 데이터

중요한 어플리케이션의 개발은 일반적으로 관계형 데이터베이스 형태의 외부 데이터 스토리지가 큰 비중을 차지하지만, 많은 소프트웨어 아키텍처 도서는 이런 아키텍처의 중요한 영역을 너무 가볍게 다루는 경향이 있다..

코드와 데이터는 공생관계여서 상대방이 없으면 무용지물.

### 1.4 소프트웨어 아키텍처 법칙

소프트웨어 아키텍처의 범위는 거의 무한에 가까울 정도로 광할하지만 모든 것을 통합하는 요소는 존재한다.

* 제 1법칙: 소프트웨어 아키텍터의 모든 것은 다 트레이드오프다.
* 제 1정리: 아키텍트가 트레이드오프 아닌 뭔가를 발견했다고 생각했다면 그것은 아직 트레이드오프를 발견하지 못했다는 증거일 가능성이 높다.
* 제 2법칙: '어떻게'보다 '왜'가 더 중요하다.

### 느낀점

각오는 하고 읽었지만 처음보는 단어도 많고 내용도 어렵다고 걱정해서 그런지 무서웠는데.. 읽어보니 생각보다 잘 읽혀서 다행이다..

물론 서론이라 뒷 부분의 자세한 내용까지는 모르지만 한번 쓱 읽어봐도 처음보는 단어들 빼고는 잘 설명이 되어 있다..!

#### 논의사항

책에 나온 아키텍트에 대한 기대치말고 여러분들이 아키텍트를 볼 때 기대하는 추가적인 부분이나 중요하다고 생각하는 부분이 있을까요?
