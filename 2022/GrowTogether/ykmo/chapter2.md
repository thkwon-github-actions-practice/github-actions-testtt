# 함께

이번 챕터는 협업에 대한 내용을 다루고 있습니다. 주로 어떻게 협업 해야 좋은 효과가 나오는지 여러 연구 사례를 통해 정리되어 있습니다.

주의 : 일부 내용은 맥주 한캔 마시고 썼습니다. 역시 알코올은 창작 활동의 원동력이 아닐까요?

논의할 점은 글 가장 마지막에 작성하였습니다.

### 소프트웨어 관리자의 우선순위

먼저 조엘 스폴스키라는 이름을 봐서 매우 반가웠습니다. 이전 회사에서 인상깊게 읽었던 책이였거든요. 조엘 온 소프트웨어를 인상 깊게 보았거든요. 저자가 말한 것 처럼 조엘 테스트를 해보았습니다.

1. 소스 컨트롤을 사용하는가?

→ Git 사용중입니다.

1. 한 번에 빌드를 만들어 낼 수 있는가?

→ yarn 스크립트 한방이면 바로 빌드 할 수 있죠.

1. 일일 빌드를 만드는가

→ 일일..? 은 아니고 PR을 올리면 그때마다 빌드가 돌아요

1. 버그 데이터베이스를 가지고 있는가?

→ 이 부분은 좀 모호하네요. JIRA에 리포팅된 이슈 목록이 있습니다만 버그 DB라고 부를 수 있을까요

1. 새로운 코드를 작성하기 전에 버그를 고치는가?

→ `저에게 시간과 예산이 더 있었다면..`

1. 최신 업데이트 된 스케줄이 있는가?

→ YES

1. 스펙(제품 명세)이 있는가?

→ YES

1. 프로그래머가 조용한 환경에서 일하는가?

→ So..So? 그러나 저는 조용하기만한 환경에서 일하는거 싫습니다. 예를 들어볼까요? 저희 회사 3층에 시니어 개발자분이자 Tech Leader 역할을 하시는 분이 계시고 있습니다. 이니셜이 KJF인데요 (마침 저희 띵끄어바웃소프트웨어 리더님 깃허브 계정 이니셜도 KJF네요 ㅎㅎ) 항상 small talk, lightning talk를 즐기시는 분입니다. 거기에 같이 계신 유니티 개발자분들도 자유로운 분위기에서 의견을 공유하곤 합니다-부럽습니다.)

대화를 하다보면 여러 아이디어가 떠오르기도하고, 정리되지 않던 부분이 정리된다던지, 몰랐던 부분을 알아가는 즐거움이 있습니다. 혹시 대화에 지친다면? 그럴때는 이어폰을 쓰면되니까요. 너무 조용하기만 한 환경은 사절이에요.

1. 돈이 되는 한 최고의 툴을 사용하는가?

→ 네니오. 듀얼 모티터, 가급적 최신 스펙의 PC쓰고 있지만 모니터 2개로 모자라서 사비로 +1 해서 쓰고 있습니다. 지급받은 PC가 있긴 있는데 역시 뭐니뭐니해도 개발자는 mac book이죠. 특히 m1이요. 저도 회사에서 m1 pro, m1 max pro 쓰고싶습니다. 당근마켓에서 노트북 2대씩 사용하게 해준다는데 제가 다니는 회사도 좀 그렇게 해줬으면 좋겠습니다. 개인 맥북 들고다니는거 매우 귀찮아요.

1. 테스터가 있는가?

→ 이런걸 버그로 리포팅한다고? 이걸 버그로? ㅇㅇㅇ??? 으으으으음?? 아니 테스터님 이 기능은 이렇게 쓰라고 한게 아니에요! !@$# 라고 대화하는 매우 꼼꼼하신 테스터님이 있습니다.

1. 채용 면접 때 후보가 코드를 짜게 해보는가?

→ 저는 입사할 때 포트폴리오로 대체해서 보지는 않았지만 바뀐 채용 프로세스 부터는 필수라네요

1. 복도 사용성 테스트

→ 아니요!

작가가 말하길.. 조엘의 테스트를 맹신하는건 위험하다고 말합니다. 특히 관리적인 측면에서요. 관리자의 입장에서 가장 쉽게 개선 할 수 있는건 좋은 도구를 도입하는 것입니다. 그러나 좋은 도구를 도입하는건 약 3배의 효과를 가지고 오지만 관리(관리자 자신)을 개선하면 64배의 효과를 가지고 올 수 있다고 합니다.

반대하는 점 : 좀.. 맹신이라도 했으면 좋겠습니다. 적어도 소프트웨어를 개발하는 회사라면 저 테스트를 표준삼아 자격 증명이라도 해야된다고 생각합니다. 저정도를 통과 못한다면 과연 ‘개발 회사' 라는 타이틀을 붙여도 될까요? 저는 글쎄요..? 인간적으로 듀얼 모니터에 최신 개발 PC정도는 지급해줘야하지 않을까요? 데스크탑에 싱글 모니터로 개발하는건 죄악입니다.

### 협력을 통한 추상화

이 챕터에서도 대화를 하라는 이야기가 핵심입니다. 저도 동감하구요. 대화를 통해 자신이 인지하고 있던 부분의 추상화 레벨이 높아지고 해상도가 높아지는 경험을 종종 하곤 합니다.

### 신뢰를 깎는 공유인가 신뢰를 쌓는 공유인가

사실... 이 챕터는 작자가 무엇을 말하고 싶은지 잘 모르겠습니다. 어중간한 공유는 아예 안하는것만 못하다. 할꺼면 최대한 많이 공유를 하라는 말인것 같습니다.

### 객관성의 주관성

모든 의사결정에는 결국 인간의 감정을 배제할 수 없으며 객관적이라는 것들은 사실 주관적이라는걸 말하고 있습니다. 뇌에서 감정을 담당하는 부분이 다치면 의사 결정을 제대로 못한다는 부분은 흥미로웠습니다. 특히 MBTI 유형으로 애자일을 설명하는 부분도 재미있었네요 (저는 INFJ입니다)

“애자일 이거 정말 새롭고 이거하면 진짜 좋아요. 고객과 우호적 관계를 이어 나갈수 있구요. 팀원들 모두 신뢰하면서 즐겁게 일할 수 있습니다. 누군가를 비난하거나 하는 일이 없을 겁니다.” 쓰고보니 글에서 약냄새가 올라옵니다.

### 이것도 모르세요?

이전 까지 이야기가 “대화가 중요해!” 였다면 이번 챕터는 “그렇다면 어떻게 대화해야할 까?” 에 대해 다루었습니다. 저 나름대로 이때까지 다른사람들에게 잘 알려주고 있다고 느꼈는데 행동을 유도하는 대화 부분에서 좀 더 나은 방향을 찾을 수 있었습니다.

### 하향식 접근의 함정

최근들어 탑 다운 방식에 대한 거부감을 이 챕터를 보고 정리 할 수 있었습니다. 전문가일수록 탑 다운-바텀 업 방식을 자유롭게 왔다갔다 하고, 반대로 비 전문가일 수록 탑 다운방식으로 일을 한다는점이 매우 인상깊었습니다.

실제로 개발 할 때 탑 다운방식으로 개발한것들은 어딘가 나사가 하나 빠져있다던지, 검토되었어야하는 부분이 제대로 검토되지 않아 나중에 문제가 많이 발생했던 반면, 탑 다운 - 바텀 업 방식을 자유롭게 왔다 갔다하면서 의견을 주고받으며 개발했던 부분은 나중에 문제가 적게 발생했던 경험이 있습니다.

### 전문가팀이 실패하는 이유

전문가도 실패할 수 있다. 무계획으로 가면..

### 구글이 밝힌 탁월한 팀의 비밀 & 쾌속 학습팀

1장 - 자라기에서도 언급되고 이책에서 일관적으로 말하는 부분이 실수에 대한 이야기입니다. 실수를 비난하지 말고 실수를 잘 관리하라는거죠. 실수를 비난하기 시작하면 개인에게 불안감이 커지고 불안감은 마치 전염병처럼 팀을 감염시킵니다. 그 결과는 불을 보듯 뻔하게 팀의 역량을 떨어트리게 됩니다.

### 프로젝트 확률론

생각보다 개발자가 굉장히 긍정주의자라는걸 알게되었습니다. 개발자는 보통 비관주의자가 아닐까 생각했는데요. 돌이켜보니 저도 긍정적인 마인드로 일정을 산정해 왔던 것 같습니다. “2달이면 끝날 수 있어요!” → 2달 안에 끝내긴 했는데 근무 시간이 야근으로 폭발했던 케이스도 있고 “2달 좀 넘지 싶어요~” → 6달 걸린 경우도 있었습니다.

### 논의해볼 점

여러분이 일하시는 업무 환경은 어떤가요? 장비 이야기도 좋고 같이 일하시는 사람에 대한 이야기도 좋습니다.

여러분은 일정 산정하는데 보통 어떻게 하시나요? 어떤 과정을 거치시는지 궁금합니다.
