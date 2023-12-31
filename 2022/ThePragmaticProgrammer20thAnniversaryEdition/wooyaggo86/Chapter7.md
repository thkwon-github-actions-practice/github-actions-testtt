# Chapter 7. While You Are Coding

preface
코딩은 단순한 mechenical한 작업이 아니다. 중요하다.

> Coding is not mechanical. If it were, all the CASE tools that
people pinned their hopes on way back in the early 1980s would
have replaced programmers long ago. 

Q. CASE tool이 어떤걸까요?

W. bog down 
Verb 교착 상태에 빠지다, 꼼짝 못하게 하다; 수렁에 빠지다, 늪에 가라앉히다; 가라앉다. (=cause to sink in a bog; delay, hinder, stall; sink in.)

Topic 37. 모든 결정이 의식적으로 이루어 지진 않는다. 무의식적으로 코드를 작성하는걸 경계하자.
Topic 38. ?? 어떻게 정리해야하지?
Topic 40. Pragmatic programmer 는 모든 코드를 critical하게 생각하고, 지속적으로 향상시킨다.
Topic 41. Testing은 단순히 버그를 찾는게 아니라 피드백을 받는것: Design, API, coupling, 기타 등등.
Topic 42. Property-based testing이 어떻게 버그 찾는지 도와주는가.
Topic 43. 나쁜 사람이 코드를 악용하는 걸 방지하자.
Topic 44. 소프트웨어 엔지니어링에서 가장 어려운 것. 이름 짓기.

## Topic 37. Listen to Your Lizard Brain
Lizard Brain

Instincts. learn through repetition.

 Instincts make you feel, not think.

W. innate
선천적인.

The trick is first to notice it is happening, and then to work out
why.
### FEAR OF THE BLANK PAGE
두려워하지 말자.

Two problem

1. there’s some kind of doubt lurking just below the
surface of perception.
2. you might simply be afraid that you’ll make a mistake.

왜 2번이 왜 Lizard brain과 관련이 있지?

W. reluctant
1.	꺼리는
2.	마지못한
3.	주저하는

W. prosaic
ADJECTIVE 평범한, 상상력이 없는 (=unimaginative), 따분한

### FIGHTING YOURSELF
코드를 바로 작성하려는 유혹에 저항하자.

### HOW TO TALK LIZARD
멈추고 내가 뭘 하고 있는지 정리하는 시간을 갖자.

## Topic 38. Programming by Coincidence

내가 하고 있는게 무슨일인지 정확히 알자.
가정들은 명확하게 확인하자.
'내가하고 있는 일을 다른 사람에게 코드레벨로 잘 설명할 수 있는가?'를 통해 나의 이해도를 파악하자.
문서화 하자.

## Topic 39. Algorithm Speed

내가 작성하는 코드의 실행시간을 Big O notation으로 표현할 수 있어야 한다.
빠른 알고리즘이 항상 좋은 솔루션은 아니다.

## Topic 40. Refactoring

언제 리펙토링을 해야하는가?
- Duplication
- Non-orthogonal design
- Outdated knowledge
- Usage
- Performance
- The Tests Pass

어떻게 Refactor 해야하는가?
At its heart, refactoring is redesign.

리팩토링이 해가 되지 않고 이득을 얻는 법.
1. Don’t try to refactor and add functionality at the same time.
2. Make sure you have good tests before you begin refactoring. Run
the tests as often as possible. That way you will know quickly if your
changes have broken anything.
3. Take short, deliberate steps: move a field from one class to another,
split a method, rename a variable. Refactoring often involves
making many localized changes that result in a larger-scale change.
If you keep your steps small, and test after each step, you will avoid
prolonged debugging.

## Topic 41. Test to Code
Testing을 어떻게 하는지 생각함으로써, API설계를 더 잘 할 수 있다.
C. -> API를 사용하는 사용자가 어떻게 사용할지 생각 함으로서, API 설계를 더 잘 할 수 있다.

testing is vital feedback that guides your coding.

Build End-to-End, Not Top-Down or Bottom Up.


## Topic 42. Property-Based Testing

They make you think about your code in terms of
invariants and contracts.

Q. 테스트에 randomness가 들어가는 것에 대해 명확한 pros/cons가 있는데, 이를 어떤 상황에서 잘 사용할 수 있을지가 판단이 어려울 것 같다. 모든 테스트에는 적합하지 않다고 생각이 든다.
Q. 어떤게 좋은 속성인지 알 수 있을까요?

## Topic 43. Stay Safe Out There

많은 경우 문제가 일어나는 이유. 
It's because the developers were careless.

좀 문제 있는 접근 아닌가?
마치 개발자가 좀만 잘하면 모든걸 다 문제없이 할 수 있다는 느낌이네.

왜 일정이 미뤄지는가? 개발자가 게을러서.
왜 성능이 안좋은가? 개발자가 부주의해서.
물론 이런 의도는 아니였겠지만..

### The Other 90%

Security through obscurity just doesn't work.

### Security Basic Principles

1. Minimize Attack Surface Area
  - Code complexity leads to attack vectors
  - Input data is an attack vector
  - Unauthenticated services are an attack vector
  - Authenticated services are an attack vector
  - Output data is an attack vector
  - Debugging info is an attack vector
2. Principle of Least Privilege
가능한 최소한의 권한만 부여하자.
> Every program and every privileged user of the system should operate using the least amount of privilege necessary to complete the job.— Jerome Saltzer, Communications of the ACM, 1974.
3. Secure Defaults
개인정보 전부 원하는 회사들이 많죠..
회사에게는 싫은 옵션..
4. Encrypt Sensitive Data
항상 man-in-the-middle(MITM)에 주의하자. 네트워크상 모든 데이터는 노출 될 수 있다.
확장해서 메모리 상에 있는 정보도 마찬가지.
5. Maintain Security Updates
모든 업데이트가 중요한 건 아니다.
하지만 최대한 안정성 있게, 가능한 빠르게 적용하자.

총평. 가능한 적게, 가능한 조금만.. 대응은 빠르게.
But.. is it business critical?

## Topic 44. Naming Things

이름 짓는건 어렵다.
특히 영어로 해야하는 제약 아래에서는..

We believe that things should be named according to the role
they play in your code. 
모든 코드는 어떤 역할을 하는가에 따라 적절하게 이름을 짓어야 한다. 짓기를 당한다고 해야하나.

There’s some science behind the idea that names are deeply 
meaningful.

과학이 있다네 . 신기하군.
 단어를 정말 빨리 읽고 이해한다. Strop effect를 통해 증명할 수 있는데 이게 뭐지?

 예제가 흥미롭네.

 https://learning.oreilly.com/api/v2/epubs/urn:orm:book:9780135956977/files/images/stroop_color.png
단어를 읽는게 색상을 인지하는 것 보다 어렵다.


### Honor the Culutre
Honor the local culture. 로마에서는 로마의 법을 따라라.
btw, google python coding style?


### Consistency
사람들이 자꾸 간과하는 것.
Q. How to handle conflict with local culture vs global culture?

코드리뷰도 하나의 convention을 소통하기 위한 커뮤니케이션 수단.
documentation이 너무 중요한데... 누가 이를 잘 지킬까...

총평. 이름을 잘 짓자.. 근데 너무 어렵다.
