# 4장 실용주의 편집증


# Topic 23 계약에 의한 설계

## 키워드

- 계약
- DBC
- 의미론적 불변식

## 중요문장

- DBC는 단순하지만 강력한 기법으로, 프로그램의 정확성을 보장하기 위해 소프트웨어 모듈의 권리와 책임을 문서화하고 합의하는 데에 초점을 맞춘다.
- 정확한 프로그램이란 무엇인가? 자신이 하는 일이라고 주장하는 것보다 많지도 적지도 않게 딱 그만큼만 하는 프로그램이다. 이 주장을 문서화하고 검증하는 것이 ‘계약에 의한 설계'의 핵심이다
- 무슨 일이 벌어지든지 확실한 점은 계약에 부응하지 못하는 것은 버그라는 것이다.
- 코드를 작성하기 전에 유효한 입력 범위가 무엇인지, 경계 조건이 무엇인지, 루틴이 뭘 전달한다고 약속하는지, 혹은 더 중요하게는 무엇을 약속하지 않는지 등을 나열하는 것 만으로도 더 나은 소프트웨어를 작성하는 데에 엄청난 도움이 된다.
- DBC 방식을 사용하여 선행 조건과 후행 조건, 불변식을 검증하면 더 일찍 멈추고, 문제에 대한 보다 정확한 정보를 알려줄 수 있을 것이다.
- 어겨서는 안 되는 고정된 규칙인 요구사항과 경영진이 바뀌면 얼마든지 없어질 수 있는 단순한 정책을 혼동하지 말아야 한다.
- 소프트웨어를 설계하게 되면 계약 역시 설계하도록 하라.

## 내 생각

- DBC 라는 이름을 붙이고, 풀어서 설명하고 있지만, 내가 이해한 바로는 단순하게 주어진 문제에 대해서 어떻게 개발할 것인지 정하는 과정, 약속을 말하는 것이라고 생각한다 즉, 우리는 무의식 중에 항상 DBC를 실천하고 있다. PO, 디자이너, 프론트엔드 개발자 분들과 논의하면서 어떻게 구현할지 정하는 것 자체가 DBC라고 말하는 것과 별다른 것이 없기 때문이다.
- 현실에서 좀 더 보강하면 좋을 것 같은 부분은 선행조건, 후행 조건, 불변식을 검증하는 부분이다. 사실 현실에서는 이 정도까지 서로 간에 협의하진 않고 대개의 경우 개발자의 재량에 맡긴다. 그리고 개발자는 따로 기술해두지 않고 머리속 뇌피셜을 기준으로 코드를 작성하곤 한다.
- 나 같은 경우에 의도한건 아니지만, 개발 티켓을 처리할 때, 문제,해결,조건,절차,검증 의 다섯단계로 나누어서 항상 미리 쭉 티켓 description을 적는다. 적으면서 문제에 대해서 확실히 이해하고, 애매한 부분이 있다면 다시 논의해서 명확하게 다시 기술한다 이런 방법을 할 때 단점은 개발하는 도중도중에 변경사항이 있을 때마다 문서 또한 수정을 해주어야 한다는 것이다. 그래서 나의 경우는 금방변경가능한 수정은 수정하지만, 이전과 비교해서 너무나도 큰 변화가 있거나 할 때는, ~~수정을 하지 않거나..~~ 새롭게 다시 적는다 문서로써 무결하게 유지하기 위해서 적는다기 보다는, 내 생각을 정리하는 목적으로 사용한다. 대신에 상위레벨인 인수조건에 대해서는 확실하게 유지하려고 노력한다. 장점은 내가 해결할 문제에 대해서 description을 작성하면서 머릿속으로 어떻게 할지 정리를 할 수 있다는 것이다. 미리 생각해보고 구현을 시뮬레이션해보는 과정에서 코드를 작성하는 과정에서 나올 문제상황들을 미리 경험하고, 생각해볼 수 있다. 여기서 기술을 잘 해놓으면 코드작성은 사실상 고민할 것 없이 기술한 내용을 그대로 코드로 옮기면 되고, DBC 로 정해진 내용대로 코드도 작성되게 된다

## 의논 해볼 내용

- 의식적으로 DBC를 지키기위해 실천하고 있는 것이 있다면 공유해보자


# Topic 24 죽은 프로그램은 거짓말을 하지 않는다

## 키워드

- 일찍 터지게 만들어라

## 중요문장

- 있을 수 없는 일이 발생했을 때 우리는 그 사실을 알아야 한다
- 실용주의 프로그래머는 만약에 오류가 발생했다면 정말로 뭔가 나쁜 일이 생긴 것이라고 자신에게 이야기 한다
- 방금 있을 수 없는 일이 발생했다는 것을 코드가 발견했다면 프로그램은 더는 유효하지 않다고 할 수 있다. 이 시점 이후로 하는 일은 모두 수상쩍은 게 된다. 되도록 빨리 종료할 일이다. 일반적으로 죽은 프로그램이 끼치는 피해는 이상한 상태의 프로그램이 끼치는 피해보다 훨씬 적은 법이다.

## 내 생각

- 회사에서 업무를 하기 전까지는 있을 수 없는 일이 발생했을 때 그 사실을 알기위해서 오류를 발생시키는게 낫다 라는 말을 전혀 이해하고 있지 못하였다.
- 오류가 발생한다면, catch 하여서 exception handling을 반드시 해주어야하는걸로 착각하고 있었다
- but, 회사 업무를 하면 할 수록, 있을 수 없는 일에 대해서 에러를 발생시키는 것이 매우 중요함을 경험을 통해 이해할 수 있었다. 코드에 대해서 있을 수 없는 일은 발생할 수 있다. 이럴 때, exception handling으로 에러를 감추기 보다는 적극적으로 드러내서, 뭔가 문제가 있다는 것을 인지할 수 있어야 한다 그래야 문제를 인지하고 디버그 할 수있는 기회가 생기기 때문이다 그런 관점에서 책에서 미리 종료시켜야한다는 말에 매우 동의한다
- 또한, 오류를 적극적으로 드러나게 해주는 코드가 의도도 훨씬 정확하게 드러낸다고 생각한다. 일어날 수 있는 일과 일어나면 안되는 일을 드러낼 수 있기 때문이다

## 의논 해볼 내용

- 나의 경우, 의도를 더 드러내고, 있을 수 없는 일이 발생했을 때 더 빠르게 인지하기 위해서 에러를 발생시키는 것에 적극적인데 반해서, 모든 경우에 exception handling을 통해서 에러를 제어하려고 하는 관점도 있는 것 같다. 본인은 어떤쪽에 더 가까운지 얘기해보자


# Topic 25 단정적 프로그래밍

## 키워드

- 단정

## 중요문장

- 하지만 물론 그런 일은 절대 일어나지 않을거야 라는 생각이든다면 그런 일을 확인하는 코드를 추가하라 가장 간단하게 추가하는 방법은 단정문을 사용하는 것이다.

## 내 생각

- 단정문을 사용하는 이유에 대해서는 충분히 공감을 하였으나, 현업 코드에서는 단정문을 활용하는 예를 사실 거의 보지 못하였다.(예전코드에서는 몇번 봄..)
- IMHO, 굳이 단언문을 쓰지 않고도 충분히 의도를 드러내는데 문제가 없다고 생각한다. 예를들면, 가드절 같은 것으로도 충분히 성공할 수 있는조건, 그렇지 않은 조건을 표현할 수 있다. 또한 코드 가독성도 해친다고 생각한다
- 나 같은 경우 테스트 코드에서도 given 조건에 단언문을 쓰는것을 선호하지 않는다. given 조건 자체가 코드작성하는 사람이 정하는 조건이기 때문에, 이것 자체가 테스트의 의도를 드러내는 것인데, 단언문을 통해 굳이 중복해서 의도를 드러낼 필요가 없기 때문이다 그래서 사실상 테스트 코드의 then 부분에서를 제외하고 코드에서 단언문을 쓰는 경우는 나의경우는 없다
- 그럼에도 불구하고, 좀 더 잘 쓸 수 있는 방향은 없을까? 에 대해서 고민은 필요할 것 같고, 다른 개발자분들이 단언문을 쓰지 않는, 쓰는 이유에 대해서도 한번 문의해보면 좋을 것 같다

## 의논 해볼 내용

- 단정문을 코드에 사용해서 도움이 된 사례가 있다면 공유를 해보자


# Topic 26 리소스 사용의 균형

## 키워드

- 리소스

## 중요문장

- 리소스를 할당하는 함수나 객체가 리소스를 해제하는 책임 역시 져야 한다는 뜻일 뿐이다.
- “자신이 시작한 것은 자신이 끝내라” 팁이 가르쳐 주는 것은 이상적으로 말해서 리소스를 할당하는 루틴이 해제 역시 책임져야 한다는 것이다.
- 잘 모르겠을 땐 언제나 스코프를 줄이는 편이 낫다.
- 리소스를 할당하는 것이 언제나 그 리소스를 해제할 책임까지 져야 한다.

## 내 생각

- 이부분을 읽으면서, 최근에 회사에서 http, redis connection 관련해서 리소스 해제를 명시적으로 해주지 않아서 생기는 문제가 있었던 것이 생각났다. 무심코 리소스해제에 대한 생각없이 사용하다가 장애상황을 경험하게 된 것인데, 개인적으로 connection 관리와 관련해서 이론적으로도 소홀하게 알고있었고, 큰문제가 있을것이라고 생각하지 않은게 부끄러웠다

## 의논 해볼 내용

- 리소스 할당 해제를 명확하게 하지 않아서 본인이 일으킨 문제가 있다면 공유해보자


# Topic 27 헤드라이트를 앞서가지 말라

## 키워드

- 작은 단계

## 중요문장

- 언제나 신중하게 작은 단계들을 밟아라. 더 진행하기 전에 피드백을 확인하고 조정하라. 피드백의 빈도를 여러분의 제한 속도라고 생각하라. ‘너무 큰' 단계나 작업은 하지 않게 될 것이다.
- 여기서 피드백이란 무엇을 말하는 걸까? 여러분의 행동을 독립적으로 확증하거나 반증하는 것이라면 모두 피드백이다.
- 여러분의 코드를 더 적절한 무언가로 대체하기 쉽게 설계하라. 코드를 교체할 수 있도록 하면 응집도나 결합도, DRY에도 도움이 되고, 전반적으로 더 나은 설계가 탄생할 것이다.

## 내 생각

- 너무 급하게 앞서가지 말고 차근차근히 단계를 밟아 나가자 단계를 밟아 나가는 과정과정에 피드백을 통해서 개선할점을 인지하고 개선하면서 나아가자 라고 글의 전반적인 내용을 이해하였다.
- 사실 너무 당연한 얘기인데, 잘 못하고 있는 것이기도 하다. 그래도 나는 25분 뽀모도로 테크닉을 통해서 이를 적극 실천해보려하고 있다.
- 최근에 김창준님이 올려주신 글 중에 일을 더 잘하기 위한 방법에 대한 글이 있었는데, 1시간에 한번씩 강제적으로 회고를 하고 개선점을 도출해서, 바로 적용해보는 내용이였다. 책에서 말하는 작은 단계, 피드백 주기, 피드백 빈도 등의 얘기와 일맥 상통한 것으로 이해되었고, 더불어서 내가 진행하고 있는 25분 뽀모도로 테크닉 또한 일맥상통한 것으로 이해할 수 있었다

## 의논 해볼 내용

- 책 에서나오는 헤드라이트를 앞서가는 바람에 문제를 겪은게 있다면 공유해보면 좋을 것 같다