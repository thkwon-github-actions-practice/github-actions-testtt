## 3장 다른 개발자의 코드 계약

> 자신이 작성한 코드를 다른 개발자가 작업해야 하고 반대로 다른 개발자가 작업한 코드를 자신이 작업해야 한다.
### 논의 사항  

객체지향에 맞게 명확한 목적을 가진 클래스가 설계했다면 주석이 필요 없을까요?

하위단부터 추론이 가능한 1단계 이름부터 잘 설계되었다면 클래스를 거슬러 올라가는 불편함은 있겠지만 목적이 분명하다면 주석이 필요 없을 것 같다는 생각이 듭니다.  

### 책의 내용 및 정리

핵심 주제  

* 다른 개발자들이 코드와 어떻게 상호작용하는지
* 코드 계약과 코드 계약의 세부 조항
* 세부 조항을 최소화하는 것이 어떻게 오용과 예측을 벗어나는 코드를 예방하는 데 도움이 되는지  
* 세부 조항을 피할 수 없다면 체크와 어서션을 어떻게 사용할 수 있는가?  

#### 자신의 코드와 다른 개발자의 코드  

1장에서 설명한 `예측 가능한 코드를 작성하라`와 `코드를 오용하기 어렵게 만들어라` 이 두가지 원칙은 다른 사람과 상호작용할 때 일어날 수 있는 일이다.  

따라서 협업의 경우에는 아래 규칙을 고려하는 것이 좋다.  

1. 자신에게 명백하다고 해서 다른 사람에게도 명백한 것은 아니다.  
2. 다른 개발자는 무의식중에 여러분의 코드를 망가뜨릴 수 있다.  
3. 시간이 지남에 따라 자신의 코드를 기억하지 못한다.  

**자신에게 명백하다고 해서 다른 사람에게도 명백한 것은 아니다.**  

자신의 로직에 너무 익숙해져 모든 것이 분명해 보이기 때문에 과정에 대해서 망각하게 된다.  

어느 시점부터는 다른 개발자가 작성한 코드와 상호작용하거나 변경할 수 있다는 점을 인지해야 한다.  

그렇다고 코드에 주석을 많이 달라는 것이 아닌 코드 자체를 읽기 쉽게 만들어야 한다.(본인이든 남이든)  

**다른 개발자는 무의식중에 여러분의 코드를 망가뜨릴 수 있다.**  

내가 작성한 코드는 생각보다 많은 의존성을 가지게 될 것이다.  

또한 코드자체도 환경이나 요구사항으로 인해 많이 변화할 것이기 때문에 병합전에 이런 문제를 제대로 확인하고 넘어가야 한다.  

의도지 않게 문제가 발생하게 되면 찾기 쉽지 않기 때문에.. 

**시간이 지남에 따라 자신의 코드를 기억하지 못한다.**  

당장 저번달 작성한 코드도 기억안나고 읽히지도 않기 때문에..ㅜ  

#### 여러분이 작성한 코드의 사용법을 다른 사람들은 어떻게 아는가?  

API 공개수준이외에도 내가 작성한 코드가 무슨 목적을 가지고 있는지 파악해야 한다.  

* 여러 가지 상황에서 어떤 함수를 호출해야 하는지  
* 클래스가 무엇을 나타내는지 그리고 언제 사용되어야 하는지  
* 어떤 값을 인수로 사용해야 하는지
* 코드가 수행하는 동작이 무엇인지
* 어떤 값을 반환하는지

> 1년이 지나면 자신이 작성한 코드라도 까먹기 때문에 미래의 자신은 본질적으로 다른 개발자라고 간주한다.  

따라서 다른 개발자가 내가 작성한 코드를 알아내기 위해선 다음과 같은 추리를 한다.  

1. 함수, 클래스, 열거형 등의 이름을 살펴본다.
2. 함수와 생성자의 매개변수 유형 또는 반환값의 유형 같은 데이터 유형을 살펴본다.
3. 함수/클래스 수준의 문서나 주석문을 읽어본다.
4. 직접 와서 묻거나 채팅/이메일을 통해 물어본다.
5. 여러분이 작성한 함수와 클래스의 자세한 구현 코드를 읽는다.  

이름 짓기의 경우 농담식으로 가장 오래걸리는 코딩작업이라고 한다.  

그만큼 다른 개발자(미래의 나)가 볼 때 직관성 띄기 때문에 바로바로 추론이 가능하다.  

멘토님의 말대로 클래스 이름과 퍼블릭 메서드만 나열해도 해당 클래스의 목적이 보여야 한다.  

#### 코드 계약  

계약에 의한 프로그래밍(programming by contract) 또는 계약에 의한 디자인(design by contract)라는 용어를 접해본적이 있을 것이다.  

~~나는 없다..~~  

이 방법론은 서로 다른 코드 간의 상호작용을 마치 계약처럼 생각한다는 점이다.  

계약은 3가지 범주로 나뉜다.  

* 선결 조건: 코드를 호출하기 전에 사실이어야 하는 것, 예를 들어 시스템이 어떤 상태에 있어야 하는지, 코드에 어떤 입력을 공급해야 하는지와 같은 사항  
* 사후 조건: 코드가 호출된 후에 사실이어야 하는 것, 예를 들어 시스템이 새로운 상태에 놓인다든지..  
* 불변 사항: 코드가 호출되기 전과 후에 시스템 상태를 비교해서 변경되지 않아야 하는 사항  

개발자가 계약의 일부 혹은 모든 조건을 알지 못하면 코드 계약에 문제가 발생한다.  

따라서 계약내용이 무엇일지, 코드를 사용하는 사람이 계약을 파악하고 따라갈 수 있을지에 대한 생각을 해야한다.  

코드를 오용할 수 있는 방법이 많을수록 실제로 오용되고 버그가 많이 있음을 시사한다.  

따라서 방어적인 프로그래밍 자세를 취하는게 좋아보인다.  

세부조항으로 문서나 주석을 통해 경고하는 것 보다 애초에 불가능하게 만드는 것이 좋다.  

내부적으로 예외를 많이 두어서 다른 방향으로 오용된다면 다른 개발자는 버그라고 생각  

*책에서는 생성자를 가려서 애초에 원하는 방법으로 객체를 생성하게 막아둠*  

#### 상태와 가변성  

객체지향에서 상태는 객체가 담고있는 어떤 값이나 데이터를 말한다. 이러한 상태를 생성 이후에 수정이 가능하다면 가변적, 반대로 수정이 불가능 하다면 불변적이라고 칭한다.  

### 느낀점

세부조항의 부분이 많이 생각하게 된다.  

이전에 기본 c라이브러리 함수를 구현한 적이 있는데 완벽한 함수를 만들겠다고 null에대한 예외처리 등 들어오는 값에 대한 예외를 되게 크게 잡았다.  

이후에 그게 틀렸다는 것만 알고 있었는데 이제와서 정리가 되는 것 같다.(의도하지 않은 동작, 오용)

지금 생각해보면 좋은 경험이였다.  

뒤쪽의 체크, 어서션은 읽어도 이해가 잘 되지 않아서 어려웠다..ㅠ  