# 2부 함께

## 논의할 내용 1

협력을 하는 내용에서 짝 프로그래밍 (pair programming)을 언급합니다. **실제 짝 프로그래밍을 하면서 얻은 경험에 대해 이야기 해보면 좋을 것 같습니다. 긍정적이던, 부정적이던 개인적인 경험을 얘기해 보면 좋을 것 같습니다.**

저의 경우는 초반에 짝 프로그래밍에 대한 이해도가 없는 상태에서 진행했을 때 다음과 같은 부정적인 경험을 얻었습니다.

- 쓸데 없는 오지랖으로 인한 사수-부사수 스타일로 다그치는 대화 진행
- 계획한 업무 미달성으로 인한 효율성 의심
- 서로 목표 의식 없이 진행한 짝 프로그래밍 시간의 의미 다시 생각

하지만 어떻게 진행하면 효과적인지 알게 된 이후로는 다음을 얻었습니다. 하지만 부정적인 경험에서 얻었던 비효율성은 완전히 제거하지는 못했습니다.

- 달성하려는 목표에 접근하기 위한 공동 작업 방향 공유
- 이후 자연스럽게 진행되는 짝 프로그래밍을 통해 각자 다르게 생각한 개발 프로세스 혹은 문법들에 대한 공유가 이루어 지면서 서로 수정 보완이 진행됨
- 서로 어디에 관심이 더 있는지 알게 되고, 공유가 되면 서로 보완해야 하는 점도 알게 되면서 여러가지를 서로 배우게 됨
  - 예) 설계-테스트-구현에 대한 상호 보완을 하다가 자연스럽게 익히는 리팩토링 기법 및 디버깅 기법 등

## 논의할 내용 2

구글이 밝힌 탁월한 팀의 비밀에서 심리적 안정감이라는 내용이 나옵니다.

실수를 용인하지 못하는 팀이나 그런 사람들과 일을 하면 위축되는 심리 상태가 지속되고 협력을 못하게 되니까 일을 못하게 된다는 자연스러운 결과로 이어지는데

**심리적 안정감이 얻지 못해서 일을 못할 정도의 경험이 있었다면 어느 정도였는지 얘기해 봤으면 좋겠습니다.**

저의 경우는 달성해야 하는 연구과제 목표를 여러 명이서 각자 알아서 자기 파트를 진행하고 있었습니다. 서로 협력하려는 일을 진행하려고 하면 일을 못한다는 인식을 가지고 있었던 팀에서 8개월간 일하면서 이 심리적 안정감이라는게 정말 중요하다는 걸 그 이후에 알게 되었습니다.

---

이후는 책 내용에 대한 간략한 정리 및 제 생각을 기록했습니다.

## 협력에 대한 이야기

린, 스타트업을 따로 나눠서 '열심히' 공부한 사례.

일을 나누려면 먼저 협력이 필요하고 서로를 잘 알고 난 이후에 나눠야 함.

## 소프트웨어 관리자의 개선 우선순위

개발팀 평가 테스트에 한번 테스트를 진행해 봄. 단순히 예/아니오로 대답이 나오는데 아니오로 대답이 나온 것을 적어 본다.

7. 스펙(제품 명세)이 있는가?
12. 복도 사용성 테스트를 하는가?

스펙의 중요성은 사실 알고 있지만, 실천해서 만들어내기가 어려운 환경이다 보니 아직 없다.
또한 복도 사용성 테스트의 경우는 일어나기가 쉽지가 않은데, 제품 자체에 대한 이해도가 떨어지는 사람도 있고 거기에 더해서 테스트 하는데 시간을 들이기에는 다들 너무 바쁜 사람들이 모여 있다.

관리자들은 도구, 사람, 시스템, 관리 순서대로 개선 노력을 진행한다. 사실 반대의 노력을 기울여야 비용면에서 개선 효과를 많이 얻을 수가 있다.

## 협력을 통한 추상화

추상화를 잘 하는 것은 프로그래밍을 하는데 있어서 중요한 포인트이다.

추상화가 이루어지고 난 이후에 협력이 진행된다면 문제를 해결하는데 더 나은 상황을 만든다 => 톱니바퀴 실험, 수학적 계산의 추상화를 서로 공유하고 협력해서 문제를 풀어냄

짝 프로그래밍을 통해 대화를 하고 대화를 하면서 추상화 개념에 접근한다. 그 이후에 구체화를 통해 코드를 작성하면서 검증, "아하" 포인트를 발견함.

의견) 실제 짝 프로그래밍의 생산성은 매우 좋다고 생각하는데, 각자 작업해야 하는 시간에 비해 1/2 속도를 가지지만 서로 협력해서 진행해야 한다는 점을 공유한다는 측면에서는 향후 생산적인 코드를 만들어낼 가능성이 높기 때문이다.

의견2) 짝 프로그래밍은 업무의 일부로 생각하고 진행하다가는 결국 안하게 된다. Self-organization team (자기 조직화된 팀) 에서 서로 협력하려는 마음을 가질 때 비로소 좋은 짝 프로그래밍의 경험을 얻을 수 있다. 사수-부사수 관계 혹은 질문-답변의 태도에서는 대체로 좋은 결과를 얻을 수가 없다.

## 신뢰를 깎는 공유인가 신뢰를 쌓는 공유인가

공유의 방법에 3가지가 있는데 그 중에 신뢰도가 높은 방법은 복수 공유이다.

- 하나 공유(share one): 하나의 아이디어 공유
- 최고 공유(share best): 여러개 아이디어 중에 잘한 것 공유
- 복수 공유(share multiple): 여러개 아이디어를 모두 공유

## 객관성의 주관성

객관적인 판단은 결국 상대적인 것이다. 판단의 기준은 사람이 만들고 감정을 배제할 수 없다. 결국 신뢰가 중요하다.

의견) MBTI가 나오는데 사실 이 책을 처음 읽었을 때만 해도 MBTI는 몰랐고 어떤 성격 테스트 중에 하나 정도로만 생각했었음, MBTI를 알고 나서 다시 보니까 매우 흥미로운 내용이라는 걸 알게 됨.

MBTI로 사람의 성향에 대해 예제를 들어 설명한 부분은 결국, 자료의 객관성을 확보하는데 노력을 들이지 말고 그 사람을 이해하려는 자세에서 출발해야 한다는 점을 객관적(?)으로 설명한 부분이라고 본다.

## 이것도 모르세요?

가장 도발적인 질문. 사실 조금 개발 경력 쌓이고 자기가 뭔가 할줄 안다고 생각하는 시점에서 누군가 잘 모르고 어리버리 하는 사람이 등장하면 속으로 혹은 실제로(?) 내 뱉는 말일 가능성이 높고 그 예시로 정규식에 대한 술퍼맨과 홍춘이의 대화로 설명하고 있다.

아무리 모른다고 해도 그 사람에 대해 이해하고 함께 협력할 방안을 모색해서 실제 좋은 방향으로의 행동을 이끌어 내는 대화를 해 나가는 것이 바람직하다는 것이 결론.

의견) 그런데 이것도 대화를 부드럽게 이어 나가는 기술과 경험을 가진 사람이라면 괜찮은데 그렇지 못한 사람이라면 서툴거나 어렵다고 느껴질 수 있는 부분이긴 함

## 하향식 접근의 함정

전문가라고 항상 top-down으로 일하지 않는다. 바통 터치가 가능한 전문가 조직에서는 사로 의사소통을 잘 하면서 top-down, bottom-up 방식을 섞어 추상화-구체화 단계를 오르락 내리락 하면서 작업함 => 여기서 "아하" 포인트를 발견함

## 전문가팀이 실패하는 이유

책의 마지막 네줄 정리로 요약 가능

1. 전문가들 모아서 팀 만든다고 잘하는 것 아니고
2. 오히려 성과가 떨어질 수 있고
3. 정보 공유하고 협력을 잘하기 위한 명시적인 도움이 필요하며
4. 소셜 스킬 등이 뛰어난 제너럴리스트가 있으면 도움이 된다

결국 전문가라고 해서 다 잘하는 게 아니고, 협력을 하지 않으면 안된다는 걸 강조해서 설명하고 있음.

## 구글이 밝힌 탁월한 팀의 비밀

구글이 밝힌 내용에 따르면 팀의 상호작용과 그 팀의 심리적 안정감이 상당히 중요하다는 걸 언급함.

`내 생각이나 의견, 질문, 걱정, 혹은 실수가 드러났을 때 처벌받거나 놀림받지 않을 거라는 믿음`이 심리적 안정감에 대한 설명.

## 의도적 수련의 일상적 예시

저자가 코칭할 때 수련했던 얘기와 등산할 때 얘기. 이해하고 넘어 갔습니다.

## 쾌속 학습팀

위기를 기회로 생각할 줄 아는 능력(?)이 중요한 듯. PHP로 하는 팀에서 자바를 써야 하는 상황이 온다면?

- 자바를 잘 하는 사람이 있는게 중요한 게 아니라, 자바를 학습해서 만들어 나가야 한다는 학습 태도가 중요
- 기회와 가능성, 큰 변화의 흐름에 동참하는 중요성과 즐거움으로 생각

글로는 정말 좋은 내용이긴 한데, 이게 현실에서 실제 가능한 사람을 만나기가 쉽지 않은 듯

다시 역으로 생각해 보면, 어떤 언어를 잘 하는 사람을 뽑기 보다는 뭔가를 배우는걸 즐기는 사람을 뽑는게 향후 학습을 잘 하는 팀을 꾸릴 때 좋은 팀원이라는 것은 확실히 알게 됨

### 결론

진정한 학습은 실행 속에서 이뤄지고, 진정한 실행은 학습을 수반한다 => 으아 이렇게 맞는 말을 하다니!

- 할 수 있는 걸 지금 당장, 30분이라도 하자
  - 워드 커닝햄: 작지만 유용한 프로그램들을 매일 작성할 것을 추천합니다
- 학습 공동체를 구축하자. 나와 함께 학습 환경을 만들 수 있는 사람과 함께하자

## 프로젝트 확률론

애자일에서는 팀이 서로 학습해서 배우고 공유하는 좋은 일이 일어나면 `또는` 확률로 바뀌게 되고,

서로 도와주지 않고 시행착오 조차 공유하지 않는 팀에서는 나쁜 일이 일어나고 그건 `그리고` 확률로 바뀌게 된다.

의견) 애자일을 해야 하는 이유를 꼭 이렇게 까지 설명하지 않아도 될 거 같은데, 뭔가 수치상으로 보여지는 근거가 필요한 사람들을 위해서 만든 예제인 거 같기도 함