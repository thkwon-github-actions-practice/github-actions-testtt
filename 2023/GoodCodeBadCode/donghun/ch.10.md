# 10강 단위 테스트의 원칙

- 단위 테스트란?
    - 단위 테스트는 상대적으로 격리된 방식으로 코드의 구별되는 단위를 테스트하는 것에 관한 것이다.
    - 어떤 개발자는 단위 테스트의 대상이 되는 코드가 의존하는 코드를 차단하려고 하는 반면 다른 개발자들은 의존하는 코드를 포함해서 테스트를 하는 것을 선호한다?
    - 왜 이렇게 의견이 갈리는 걸까?
- 단위 테스트에 대한 정의를 일부로 고안해 내고 자신이 작성한 테스트가 그 정의에 부합하는지에 대해 너무 집착하지 않는 것이 좋다.
- 궁극적으로 중요한 점은 코드를 잘 테스트하고 이 작업을 유지보수할 수 있는 방법을 수행하는 것이다.

개인 생각

단위 테스트라는 이야기를 멘토님으로부터 처음 들었을 때 저는 별도의 테스트 프로젝트를 만들어서 특정 기능을 이곳에서 작성 후 실행하는 과정이라고 생각했었습니다.

일종의 더미 프로젝트라고 생각했었죠.

코드에 대한 테스트 코드를 작성해야 한다는 이야기를 듣고 난생 처음 작성한 테스트 코드는 부끄럽지만 아래와 같았습니다.

```csharp
object obj = new object();
Assert(obj, true)
```

객체 하나 생성해 놓고 객체가 null인지 아닌지만 테스트를 하는 어처구니 없는 코드를 작성했었죠.

테스트 코드에 대해서 이야기를 할 때면 개인적으로 이와 같은 에피소드가 생각납니다.

그렇게 아무것도 몰랐던 그때 그 시절이 생각나면서도 부단히 성장하기 위해 힘써 왔구나란 생각도 드는 주제입니다.

## 10.1 단위 테스트 기초

- 훌륭한 테스트를 하기 위해서는 테스트만 있다고 되는 것이 아니라, 좋은 테스트가 필요하다.

## 10.2 좋은 단위 테스트는 어떻게 작성할 수 있는가?

- 실제 코드가 작동하는지 확인하기 위해 테스트 코드를 작성하기만 하면 된다는 생각은 기만적인 것이다.
- 좋은 단위 테스트가 가져야 할 5가지 주요 기능은 아래와 같다.

### 10.2.1 훼손의 정확한 감지

- 단위 테스트의 가장 명확하고 주된 목표는 코드가 훼손되지 않았는지 확인하는 것이다.
- 즉 오직 코드가 훼손된 경우에만 테스트가 실패하도록 해야 한다.
    - 이를 위해서는 테스트가 플래키하지 않도록 만들어야 한다 → 코드 내적인 요소가 아닌 외적인 요소로 인해 테스트가 실패하지 않도록 만들어야 한다.

### 10.2.2 세부 구현 사항에 독립적

- 세부 구현(private 함수)에 대해서도 테스트 코드를 작성하게 되면 리팩터링 후 해당 테스트 코드가 실패할 가능성이 높다.
- 리팩터링을 올바르게 수행했다면 외부 동작은 변경이 없기 때문에 테스트 코드를 수정할 필요가 없다. 그럼에도 불구하고 테스트 코드가 실패한다면 리팩터링을 하면서 외부 동작을 바꾼 것으로 판단 가능하다.
    - 리팩터링을 하기 앞서 public api에 대한 테스트 코드가 있다면 리팩터링에 대한 안정성을 검증할 수 있기 때문에 좋아보인다.

### 10.2.3 잘 설명되는 실패

- 테스트가 실패했을 때 무엇이 잘못됐는지 알려주지 않으면 그것을 알아내기 위해 많은 시간을 낭비해야 한다.
- 테스트 실패를 잘 설명할 수 있는 좋은 방법 중 하나는 하나의 테스트 케이스는 한 가지 사항만 검사하고 각 테스트 케이스에 대해 서술적인 이름을 사용하는 것이다.

### 10.2.4 이해 가능한 테스트 코드

- 코드 변경에 따른 테스트 코드도 변경을 해야 하는데 이때 각각의 테스트 케이스가 무엇을 테스트하는지 그리고 어떻게 테스트하는지 이해하고 있어야 한다.
- 이를 위해서는 테스트 코드를 이해하기 쉽게 만들기 위해 노력해야 한다.
- 그리고 테스트 코드를 쉽게 만들기 위해 노력해야 하는 또다른 이유는 테스트 코드가 일종의 사용 설명서로 사용되기 때문이다.

### 10.2.5 쉽고 빠른 실행

- 테스트 코드 실행 시간이 너무 오래 걸리면 개발자의 작업 속도를 느리게 만든다.
- 테스트가 느리면 테스트가 힘든 작업이 되고 테스트가 힘들면 하고 싶지 않은 마음이 들 수 있다.

## 10.3 퍼블릭 API에 집중하되 중요한 동작은 무시하지 말라

- 퍼블릭 API가 의존하고 있는 세부 구현 사항이 변경되는 것은 테스트 코드에 큰 의미가 없다.
- 왜냐하면 퍼블릭 API가 의존하고 있는 세부 구현사항이 어떻게 변경이 되든 결국 퍼블릭 API가 동작하는 목적에만 집중을 하면 되기 때문이다. 다시 말해 세부 구현이 변경 되어도 퍼블릭 API의 의도가 변경되지만 않으면 된다(물론 퍼블릭 API가 변경 될 수도 있다. 이러면 곧바로 테스트 코드에도 반영을 해야 한다).

### 10.3.1 중요한 동작이 퍼블릭 API 외부에 있을 수 있다

- 독립적으로 동작하는 세부 구현 사항에 대해서 때에 따라 테스트가 필요할 수 있다.
- 즉, 세부 구현이라 할지라도 중요한 동작이라면 테스트를 할 필요가 있다.
    - 설정을 수행하고 원하는 부수 효과를 확인하기 위해서는 테스트가 세부 사항과 상호 작용해야 하는 경우가 있다.
- 가장 핵심은 코드의 모든 중요한 동작을 제대로 테스트 하는 것이다. 하지만 퍼블릭 API만으로는 이것을 할 수 없는 경우가 있다.

## 10.4 테스트 더블

- 의존성에 대한 대안으로 테스트 더블이 있다.
- 테스트 더블은 의존성을 시뮬레이션 하는 객체지만 데스트를 더 적합하게 사용할 수 있도록 만들어진다.

### 10.4.1 테스트 더블을 사용하는 이유

- 테스트 단순화
    - 테스트를 하기 앞서 많은 설정이 필요하거나 하위 의존성을 설정해야 할 수도 있다.
    - 테스트 더블을 사용하면 이러한 작업이 단순해진다.
- 테스트로부터 외부 세계 보호
    - 서버와 데이터 베이스에 값을 쓰게 되면 부수 효과를 발생시킬 수 있는데 이런 상황에서 테스트 더블을 사용하면 외부 시스템을 테스트 동작으로부터 보호할 수 있다.
- 외부로부터 테스트 보호
    - 외부세계로부터 얻는 값에 의존하는 테스트 코드의 경우 값이 변경될 수 있기 때문에 테스트 결과를 신뢰하기 어려울 수 있다.

Q) 테스트 더블을 사용해서 외부 세계로부터 보호할 수 있다는 것은 이해가 되는데요(예시가 직관적이라 그런 것 같습니다). 하지만 테스트를 단순화 시켜줄 수 있다는 점은 책의 예시로도 잘 이해가 되질 않네요. 

구체적으로 어떻게 이해를 하셨는지 궁금합니다.

### 10.4.2 목

- 목은 클래스나 인터페이스를 시뮬레이션하는 데 멤버 함수에 대한 호출을 기록하는 것 외에는 어떠한 일도 수행하지 않는다.
- 목을 구현할 때 인터페이스를 활용하면 테스트 환경과 외부 환경을 분리 시킬 수 있다.

개인적인 생각

직장 선배를 통해 추상적으로 들었던 테스트 코드에서 인터페이스를 활용하는 예제를 실제로 볼 수 있어서 좋았습니다.

책에서 나온 예제 말고 다른 방식으로 활용할 수 있는 방법이 있을지는 좀더 연구를 해봐야겠지만 테스트 대상이 되는 코드 내부 로직에서 외부 환경에 의존성이 있는 부분은 인터페이스를 상속 받은 목을 활용하는 방식은 충분히 실무에서도 적용할 수 있는 부분으로 보입니다.

### 10.4.3 스텁

- 스텁은 함수가 호출되면 미리 정해 놓은 값을 반환함으로써 함수를 시뮬레이션한다.
- 특정 테이스 케이스에 대해서 mock을 통해 얻을 값을 고정시킴으로 해당 테스트 케이스에 대해서 정상적으로 동작하는지 여부를 테스트 할 수 있다.

### 10.4.4 목과 스텁은 문제가 될 수 있다

- 목이나 스텁이 실제 의존성과는 다른 방식으로 동작하도록 서정되는 테스트는 실제적이지 않다.
    - 인터페이스를 상속 받아 구현한 목이 실제 코드의 동작과 같이 않는다면 실제 테스트와는 거리가 멀 수 있다.
- 구현 세부 사항과 테스트가 밀접하게 결합하여 리팩터링이 어려워질 수 있다.
    - 외부 동작은 그대로지만 세부 구현이 변경될 경우 이를 테스트 코드에 반영을 해주지 않으면 테스트는 실패할 수 있다.
- 저자의 의견은 목과 스텁을 최소한으로 사용하는 것을 권하고 있다. 그리고 페이크를 사용하는 것이 더 좋다고 한다.

### 10.4.5 페이크

- 페이크는 실제 의존성을 공개 API를 정확하게 시뮬레이션하지만 구현은 일반적으로 단순한데, 외부 시스템과 통신하는 대신 페이크 내의 멤버 변수에 상태를 저장한다.
    - 이때 필요한 멤버 변수는 외부 시스템을 통해 얻어야 하는 것을 저장하는 역할을 한다.
    - 페이크 객체의 생성자를 통해 멤버 변수 값을 할당해 주는 것을 고려해 보자.

### 10.4.6 목에 대한 의견

- 목 찬성론자(목 & 스텁) vs 고전주의자(페이크)
    - 목 접근법은 테스트 대상 코드가 어떻게 동작하는지를 확인하는 방면, 고전주의 접근법은 코드를 실행하는 결과가 무엇인지 확인하는 경향이 있다.
    - 즉, 과정에 집중하느냐(목 접근법) 결과에 집중하느냐(고전주의 접근법)의 차이로 보인다.
- 목 찬성론자 주장
    - 단위 테스트가 더욱 격리된다 → 테스트 대상이 되는 코드의 의존성을 최대한 낮출 수 있다.
    - 테스트 코드 작성이 더 쉬워진다 → 의존성을 고려하는 것보다 목 또는 스텁을 사용하면 의존성 설정이 필요 없다.
- 고전주의자
    - 목은 테스트 대상이 되는 코드가 실제로 유효한지 검증하지 않는다. 실제 코드가 문제가 있음에도 테스트 코드가 통과할 수 있다.
    - 페이크를 활용하면 테스트 대상이 되는 코드의 결과가 원하는 결과인지 검증하는 데 중점을 둔다.
    - 테스트 코드가 이를 어떤 방식으로 달성했는지는 중요하지 않다.
    - 테스트 대상의 동작이 변경 되었을 때에만 실패하고 세부 구현이 변경되었을 때는 실패하지 않는다.

개인적인 생각

단순히 목을 활용한다는 정도만 알고 있었지 저자와 마찬가지로 이렇게 접근 방식이 갈리는지 몰랐다.

다만 양쪽의 의견을 모두 들어볼 수 있어서 좋았다.

개인적으로 아직 어떤 방식이 더 좋다 나쁘다를 결정하기 보다 양쪽 방식을 일단 실무에서 활용하면서 피부로 느끼는 과정이 필요한 것 같다.

## 10.5 테스트 철학으로부터 신중하게 선택하라

- 테스트 철학과 방법론들
    - 테스트 주도 개발
    - 행동 주도 개발
    - 수용 테스트 주도 개발
- 결국 궁극적으로 달성하고자 하는 목표가 그 목표에 도달하기 위해 선택한 작업 방식보다 더 중요하다.
- 즉, 목적을 이루기 위한 도구 보다 목적 그 자체가 더 중요하다.
- 결국 달성하고자 하는 목표는 더욱 고품질의 소프트웨어를 생산하는 것이다.