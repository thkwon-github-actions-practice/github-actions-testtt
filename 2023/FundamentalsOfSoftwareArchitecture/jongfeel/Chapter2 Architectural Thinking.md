## CHAPTER 2 아키텍처 사고

```
논의주제)
아키텍트가 실무에서 감을 잃지 않도록 하는 방법에 대해 얘기한게 너무 와 닿아서 감동 받았습니다. 실제 코드리뷰 부분은 제가 코드를 작성하는 시간이 없는 걸 대체해 주는 좋은 포인트라고 생각했는데 여기서도 언급해서 좋은 부분이라고 봅니다.

각자 실무에서 감을 잃지 않기 위해 책에 언급한 것 포함 별도로 하고 있는 것이 있다면 얘기해 보면 좋을 것 같습니다.
아키텍트 관점이어서 생각하기 어려울 수 있지만 평소에 실무 감을 잃었다고 생각했을 때의 포인트를 잡아 보면 좋을 것 같네요.
```

개발자와 다른 관점에서 주변을 바라보는 것을 아키텍처 사고architectural thinking라고 한다.

### 2.1 아키텍처 대 설계

아키텍처와 설계의 차이점은 모호한 경우가 많다.
아키텍트처럼 사고한다는 건 비즈니스와 기술 문제를 해결하기 위해 아키텍처와 설계의 차이점을 알고 이 둘을 긴밀하게 통합한 솔루션을 모색하는 것이다.

전통적인 아키텍트의 책임과 개발자의 책임의 관계는 다음과 같다.

아키텍트는 비즈니스 요구사항을 분석해서 아키테처 특성을 도출/정의하고 어떤 아키텍처 패턴과 스타일이 해당 문제 영역에 가장 알맞는지 선택하여 컴포넌트(시스템 구성 요소)를 만든다.

개발팀은 각 컴포넌트의 클래스 다이어그램을 그리고 UI 화면을 만들고 소스 코드를 개발/테스트 한다.

하지만 이 역할 모델은 문제가 많은데 아키텍트와 개발자를 나누는 물리적 장벽을 통하는 단방향 화살표는 아키텍처와 연관된 모든 문제의 원인이다. 아키텍트가 내린 결정이 개발팀에서 전혀 쓸무가 없는 경우가 있어도 개발팀이 아키텍처를 변경하기로 결정한 내용이 다시 아키텍트에게 전달되는 일은 거의 없다. 아키텍트와 개발팀은 단절되어 있으므로 아키텍처는 의도한 대로 진행되지 않는다.

제대로 된 아키텍처를 만들려면 아키텍트와 개발자가 양방향으로 소통하는 관계를 정립해야 한다.
아키텍트는 팀 내 개발자를 멘토링/코치하는 역할도 수행할 수 있도록 가상의 동일한 팀에 소속되어 있어야 한다.

최근 시스템 아키텍처는 매 프로젝트 단계, 매 이터레이션 단계 마다 끊임없이 변화하고 발전하기 때문에 아키텍트와 개발팀이 똘똘 뭉쳐야 한다.

아키텍처와 설계의 경계는 없다. 모두 소프트웨어 프로젝트 생명 주기의 일부로서 항상 서로 동기화 되어 있어야 한다. 

```
의견)
이 부분은 로버트 마틴의 <클린 아키텍처> 에도 나온 내용인데 아키텍처와 설계를 부분 지을 수 있는 경계는 없다고 했다.
이 책에서도 이런 결론이 나온건 어찌 보면 뿌듯하다고 할까? 그런 느낌을 많이 받는다.
```

### 2.2 기술 폭

개발자는 업무를 진행하기 위해 기술 깊이technical depth를 확보해야 하지만
소프트웨어 아키텍트는 아키텍처 시각을 유지하기 위해 기술 폭technical breadth을 갖춰야 한다.

내가 알고 있는 것stuff you know
자바 프로그래머가 자바를 아는 것과 같이 전문 기술자가 일상 업무 수행에 사용하는 기술, 프레임워크, 언어, 도구를 뜻함

내가 모른다는 사실을 아는 것stuff you know you don't know
전에 한번 들어봤거나 얕은 지식은 갖고 있지만 실무 경험은 거의 전무한 기술

내가 모른다는 사실조차 모르는 것stuff you don't know you don't know
기술자가 해결하려는 문제에 완벽한 정답임에도 불구하고 그 존재조차 알지 못하는 절대 다수의 기술, 도구, 프레임워크, 언어

개발자는 초기에 피라미드 꼭대기를 넓혀 경험과 전문성을 쌓는 데 주력한다.
그러다 보면 중간 영역이 넓어지고 관련 기술과 아티팩트를 더 많이 접하면서 '내가 모른다는 사실을 아는 것'이 점점 늘어난다.

피라미드 꼭대기를 넓히는 것은 본인에게 이롭기도 하지만 계속 유지해야 할 필요가 있다. 
이건 시간을 들여 전문성을 유지해야 하는 영역이고 이 크기가 바로 기술의 깊이라고 얘기할 수 있다.

반면 아키텍트로 진로를 바꾸면 지식의 성격이 달라진다.
아키텍트의 가치는 기술에 대한 폭넓은 이해와 그 기술을 사용해서 특정한 문제를 해결하는 것이다.
즉 한가지 문제만 해결 가능한 전문 지식 보다는, 문제 해결이 가능한 다섯 가지의 솔루션을 알고 있는 게 더 중요하다.
아키텍트의 기술 폭은 바로 꼭대기와 중간 영역인데 이 중간 영역이 아래 영역을 얼마나 더 멀리 관통하는가이다.

![image](https://user-images.githubusercontent.com/17442457/229576398-210dba4c-aed6-4c05-a12e-78a42ac25a10.png)

아키텍트는 깊이 보다는 폭이 중요하므로 폭넓은 솔루션을 두루 꿰고 있어야 한다.
아키텍트는 어렵게 얻은 기술을 일부 희생하더라도 자신의 포트폴리오를 넓히는 데 시간을 투자하는 게 더 현명하다.

```
의견)
내가 한 가지 기술, 언어, 프레임워크만 경험해 보지 않은 건 어떻게 보면 아키텍트로 방향을 바꾸기 위한 좋은 발판이지 않나 생각해 본다.
```

개발자가 아키텍트로 전환하려면 관점부터 바궈야 하는데, 많은 사람들이 어려워 하므로 두 가지 역효과가 일어난다.

- 아키텍트가 되어 다양한 분야에서 전문성을 유지하려고 하지만 어느 하나도 성공하지 못하고 지쳐버린다
- 김빠진 전문성stale expertise이 나타난다. 즉 자신의 낡은 정보가 아직도 첨단을 달리고 있는 것처럼 그릇된 인식에 사로잡히게 된다.

개발자에서 아키텍트로 자리를 옮긴 경우라면 지식 습득에 관한 기존 사고 방식을 바꾸는 게 좋다.

**꽁꽁 언 원시인' 안티패턴**

Frozen Caveman Anti-Pattern은 어떤 아키텍처든 가장 비합리적인 관심사로 회귀하려는 아키텍트가 이 안티패턴에 해당한다.
일반적으로 과거의 나쁜 결정이나 예기치 못한 사고에 파묻혀 버려 그 이후로 극도의 경계심을 갖게 된 아키특트에서 두드러진다.
진짜 기술 리스크와 리스크처럼보이는 기술 리스크의 차이를 이해하는 것은 아키텍트가 평생 학습해야 할 주제이다. 

```
의견)
이건 내가 정말 경계하는 부분이기도 하고 항상 조심하는 부분이기도 하다.
일례로 요즘 CI/CD 해야 한다고 했을떄 젠킨스를 언급하면 '응?' 이라고 한번 되묻는다.
10년 15년 전에도 썼던 젠킨스는 지금도 좋을 수 있지만 github actions를 비롯한 새로운 기술의 폭을 넓혀 봤는지에 대한 생각을 해보면 뜨끔할 수도 있다.
```

### 2.3 트레이드오프 분석

아키텍트처럼 생각하는 것은 기술 여부와 상관없이 모든 솔루션의 트레이드오프를 분석하여 최선의 솔루션을 결정하는 일이다.

> 아키텍처는 구글링해도 안 되는 것이다

아키텍처는 모든 게 다 트레이드오프이다. 불행하게도 사실이 그렇다.
배포 환경, 비즈니스 동인, 회사 문화, 예산, 기간, 개발자 스킬 세트 등 여러 팩터들이 영향을 미친다.
여기에서 아키텍처가 어렵다는 얘기가 나오는 건, 저마다 다른 환경, 상황, 문제를 안고 있기 때문이다.

> 아키텍처는 정답도, 오답도 없다. 오직 트레이드오프만 있을 뿐

아키텍처적으로 사고하려면 각 방안의 트레이드오프를 분석하고 주어진 상황에서 가장 나은 선택을 해야 한다.

클로저 프로그래밍 언어의 창시자인 리치 히키Rich Hickey는 이런 말을 했다.

> 프로그래머는 장점은 잘 알지만 트레이드오프는 하나도 모른다. 아키텍트는 둘 다 잘 알아야 한다.

소프트웨어 아키텍처는 만사가 트레이드오프(장점과 단점)를 갖고 있다는 점이 중요하다.
아키텍트다운 사고란, 이런 트레이드오프를 분석하고 '신장성과 보안 중에 어느 것이 더 중요한가?'를 떠올려보는 것이다.
여러 솔루션 중 선택하는 것은 언제나 비즈니스 동인, 환경 등 다양한 팩터에 좌우된다.

### 2.4 비즈니스 동인의 이해

아키텍처 사고는 성공적인 시스템 구축에 필요한 비즈니스 동인을 이해하고 요구사항을 (확장성, 성능, 가용성 드으이) 아키텍처 특성으로 해석하는 것이다.
따라서 어느 정도의 비즈니스 도메인 지식을 갖고서 비즈니스 핵심 인사들과 원만하고 협력적인 관계를 유지해야 하는 아키텍트 업무는 쉬운 일이 아니다. 

### 2.5 아키텍처와 코딩 실무 간 균형 맞추기

코딩 실무와 소프트웨어 아키텍처의 균형을 맞추는 것도 어려운 일 중의 하나이다.
아키텍트는 코딩 실무를 하면서 어느 정도 기술 깊이는 유지해야 한다고 믿기 때문이다. 쉬워 보이지만 어려운 일이다.

코딩 실무와 소프트웨어 아키텍처의 균형을 맞추는 팁은 병목 트랩bottleneck trap에 빠지면 안된다는 것이다.
병목 트랩은 아키텍트가 프로젝트의 크리티컬 패스에 있는 코드의 소유권을 갖고 있는 경우이다.
아키텍트는 풀타임 개발자가 아니므로 개발자의 역할과 아키텍트의 역할의 균형을 잘 맞춰야 한다.

이런 병목 트랩에 안 빠지려면 개발 일은 개발팀에 넘기고 비즈니스 기능을 코딩하는 작업에 집중에서 1~3회 이터레이션을 수행하는 것이 좋다.
이렇게 하는 것의 긍정적인 측면은

- 아키텍트는 프로덕션 코드를 실제로 작성하는 실무 경험을 쌓게 된다
- 크리티컬 패스와 프레임워크 코드를 개발팀에 분산시키고 소유권을 부여해서 시스템의 어려운 부분을 더 잘 이해할 수 있다
- (중요한 장점) 개발팀에서 작업 중인 비즈니스 코드를 직접 작성함으로써 개발자들이 프로세스, 절차, 개발 환경, 어느 부분에서 가장 큰 고통을 겪고 있는지 체험할 수 있다

아키텍트가 '집에서 코딩 연습'을 하지 않고 실무 능력을 유지하는 방법은 여러가지가 있다.

- 개념 증명proff-of-concept를 자주 해본다. 그리고 PoC 작업을 할 때는 가능한 프로덕션 수준의 고품질 코드를 작성하는게 좋다
  - 아키텍트가 쓰고 버리는 PoC 코드는 오히려 레퍼런스 아키텍처가 되거나 다른 사람들이 참조하는 샘플이 되는 경우가 있다
  - 아키텍트는 프로덕션 수준의 PoC 코드를 작성해 보면서 나쁜 코딩 습관이 배기 전에 좋은 코드를 작성하는 습관을 들이게 된다
- 개발팀이 중요한 유저 스토리 작업을 할 수 있도록 기술 부채 스토리나 아키텍처 스토리에 전념한다
- 이터레이션을 하면서 버그를 잡는 일 역시 개발팀을 도와주면서 실무 능력을 유지하기에 좋은 방법이다 
- CLI 도구나 분석기를 만들어서 개발팀의 일상 업무를 간소화하거나 자동화 하는 것도 실무 능력을 유지하면서 개발팀이 효율적으로 일하게 만드는 방법이다.
- 자주 코드리뷰를 한다. 코드 리뷰를 수행하면 아키텍처 컴플라이언스를 보장할 수 있고 경험이 많지 않은 팀원을 멘토링하고 코치할 수 있는 기회가 생기는 등 여러모로 장점이 생긴다.