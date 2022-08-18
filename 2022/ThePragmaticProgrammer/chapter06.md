# 6장 동시성

> 논의할 내용
> 

이번 챕터 읽으면서 동시성과 관련된 지식에 한계를 느끼게 되었습니다. 동시성과 관련한 학습 방법, 노하우 같은 것이 있다면 공유 부탁 드립니다 - 책 추천도 좋습니다

# Topic 33 시간적 결합 깨트리기

## 키워드

- 동시성
- 시간적 결합
- 활동 다이어 그램

## 중요 문장

- 동시성은 소프트웨어 동작방식이고, 병렬성은 하드웨어가 하는 것이다.
- 우리는 동시성을 확보해야 한다. 시간이나 순서에 의존하는 시간적 결합을 끊는 방법을 생각해 내야 한다.
- 활동 다이어그램을 사용하면 동시에 수행할 수 있는데도 아직 동시에 하고 있지 않은 활동들을 찾아내서 병렬성을 극대화할 수 있다.

## 내 생각

- 동시성은 성능과 관련하여 매우 중요한 이슈라고 생각한다. 무조건적으로 병렬적, 동시성을 가지도록 프로그래밍 하면 좋을 것 같지만, 모든것에 트레이드 오프가 있듯이 무조건적으로 동시성을 가지고 처리하는게 좋은 것은 아닐 것이다. 아직 동시성과 관련해서는 깊게 생각하면서 코드작성해본적이 없다 좀 더 공부하면서, 책의 문맥을 좀 더 잘 이해할 수 있으면 좋을 것 같다
- 여기서 말하는 시간적 결합은 무조건적으로 동기로 작동하는 것들을 말하는 것 같다. 회사 업무 도메인과 관련해서 가장 쉬운 예로는 주문을 생성해서 가게에 주문을 전달하는 것이 있다. 이 과정을 동기로 수행하게 되면 트랜잭션 타임이 지나치게 길어지게 되는 문제점이 있다. 그렇게 되면 책에 나온 바텐더 처럼 망하게 될 것이다 이런 비효율을 말한 것이 아닐까 싶다
- 이 topic의 내용은 아니지만, 세상은 비동기적이라는 말에 많은 공감이 되었다 우리 스스로 생각해보면, 비동기적으로 행동하는 것들이 굉장히 많다 예를 들면, 회사에 출근하면서, 미리 커피를 주문해두고 지나가면서 바로 테이크 아웃 해서 간다던가, 테스트 돌려놓고 잠시 다른 일을 하고 온다던가.. 등등 굉장히 많다. 이를 다 따져보면, 모두 효율성을 극대화하기 위한 노력들이다. 그렇다면 프로그래밍 세계에서도 내가 효율적으로 동작하도록 하고 싶다면, 당연스럽게도 분석을 통해서 비동기적으로 효율적으로 동작할 수 있도록 설계해야하는게 당연하지 않을까?
- 동시성과 병렬성을 잘 활용하기 위해서 activity diagram을 사용할 수 있는 것에 대해서는 책을 통해서 처음 알게 되었다 관련된 내용을 찾아보고 내 프로젝트에는 어떻게 적용할 수 있을지 고민해보자
- 책의 맨마지막 부분에 엘릭서의 컴파일로가 빌드하는 방식을 소개하면서, 병렬적으로 컴파일 하는 예시로 소개하고 있다.나도 개인적으로는 회사에서 python에서 pytest를 통해 테스트를 수행할 때, [pytest-dist](https://pytest-xdist.readthedocs.io/en/latest/) 로 CPU 자원을 활용해서 병렬적으로 테스트를 돌리고 있다 기존에 500개 ~600개 정도 있던 테스트 돌리는데 거의 5~6분정도 기다리던 것을 2분 대로 줄여 보았던 경험이 있다


# Topic 34 공유 상태는 틀린 상태

## 키워드

- 세마포어
- 뮤텍스
- 모니터

## 중요 문장

- 리소스를 공유하는 환경에서 동시성은 어렵다

## 내 생각

- 동시성에 대한 고민이 들게한 챕터 였다
- 아직까지는 추상화된 레이어 위에서 좀더 로우레벨적인 내용에 대해서는 많이 알지도 못하고 활용도 못하고 있다 자연스레 동시성에 대해서는 거의 고려하지 않게 되었다
- 이번을 계기로 공유상태에 대해서 좀 더 깊은 지식을 가질 수 있으면 좋을 것 같다

# Topic 35 액터와 프로세스

## 키워드

- 액터
- 프로세스

## 내 생각

- 이 챕터의 전반적인 내용은 잘 이해하지 못하였습니다. 다시 읽어볼 예정 입니다

# Topic 36 칠판

## 키워드

- 칠판

## 중요 문장

- 특정한 비즈니스 작업 처리를 시작할 때 고유한 추적 아이디(trace id)를 만들어서 붙이는 것이다.
- 시스템이 더 잘게 쪼개지고 전체 시스템이 아니라 개별 액터만 교체하여 시스템을 업데이트할 수 있다는 면에서 어느정도 보상 받는다. → MSA의 장점

## 내 생각

- 내가 동시성에 대한 이해가 많이 부족하다보니, 칠판에 대해서 예를 든 부분이 잘 이해가 되지 않았다
- 이 부분은 다시 읽고 이해하는데 집중해볼 필요가 있을 것 같다