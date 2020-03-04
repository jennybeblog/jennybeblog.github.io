---
layout: post
title: Monthly Retrospect - 2020.FEB
description: "2020년 2월 정리"
tags:
  - Retrospect
# image: '../../assets/images/spa_structure.png'
# comments: true
share: true
---

## 공부 및 작업

- 기억에 남는 개인 작업
    - 웹팩을 대대적으로 변경한 후 라우터 동작이 이상한 것을 파악했다. 리프레쉬나 url로 직접 접근을 하면 `cannot get /a`가 떴다. 그러다가 이미지가 제대로 보이지 않는 문제가 운영에서 발견되어 고치면서, vue-router의 history mode와 호환이 제대로 안됐음을 확인했다. 이 부분은 그때 고친 후 더 찾아보기로 하고 시간이 없어서 아직까지 찾아보지 못했다. 회사에서도 있었던 이슈 같아서 꼭 찾아볼 예정이다.
- 기억에 남는 회사 작업
    - 일단 대형 업데이트가 있었다. 그래서 정말 정신이 없었다.. 방금까지도 서버 핫픽스가 올라가서 스모크 테스트를 했다.
    - 이번에 올라간 부분에 완전히 구조와 코드를 뜯어고치다시피 한 커다란 컴포넌트 덩어리(라고 하기도 민망한)가 있었는데, 별 문제없이 작동하고 있어서 정말 다행이다. 앞으로 계속 리팩토링은 필요하겠지만, 큰 건이 일단락 됐다.
        - 전반적인 변경은 쿼리 단위와 컴포넌트 분리(무려 1개의 컴포넌트에서 5개로 쪼개졌다.)였다.
        - 나쁜 점은.. 테스트 코드를 붙일 시간이 없어서 없이 진행했다는 것이다. 5월 업데이트 전에 테스트 코드를 붙일 수 있을까..? 일단 다음 코드 변경에는 절대로 테스트 코드 없이 추가 대응을 하지 않고 싶다.
        - 아무튼 내게는 하나의 목표점과도 같은 꽤나 큰 작업이라 걱정도 많이 하고 힘들기도 많이 힘들었는데, 일단 잘 돌아가고 있고 목표한 바(위의 두가지 변경사항을 적용하면서 추가 피쳐들을 넣고 문제 없이 돌아가도록 한 것)를 이뤘다고 생각하기로 했다.
    - 전반적인 프로젝트의 구조에 대해서 생각해 볼 기회가 있었다. Vuex, Flux 패턴, Reactivity 등에 대해서 한 번 다시 공부를 하고 프로젝트를 리팩토링 해보고 싶다. 너무 큰 목표인가..
- 기타
    - [REST의 representation이란 무엇인가](https://blog.npcode.com/2017/04/03/rest%ec%9d%98-representation%ec%9d%b4%eb%9e%80-%eb%ac%b4%ec%97%87%ec%9d%b8%ea%b0%80/)라는 글을 읽었는데 매우 인상적이었다. payload가 사실상 리소스가 전달되는 게 아니라 "현재 애플리케이션 상태를 반영하는 내용"이라는 게 명확히 몰랐던 내용이라서 유용했다. 이 부분을 좀 더 알아보고 싶어졌다.
        > HTTP 메시지의 payload로 전달되는 모든 것은 하나의 representation이거나 적어도 그의 일부이다. PUT 메서드를 이용해 “welcome” 이란 텍스트를 전송해서, greeting 리소스의 representation을 업데이트하는 경우, 클라이언트가 서버로 전송한 “welcome”은 representation이다. 업데이트가 성공하여 서버가 “성공적으로 업데이트되었습니다”라는 메시지를 응답의 payload로 돌려보냈다면 이 메시지 역시 representation이다. “권한이 없습니다”라는 에러 메시지로 응답했다면 그 메시지도 역시 representation이다.

        그렇다. 성공시나 에러시의 메시지도 역시 representation이다. 그런데 앞에서 분명 representation은 어떤 “리소스”에 대한 상태를 담은 정보라고 했다. 그렇다면 도대체 “성공적으로 업데이트되었습니다”는 어떤 리소스에 대한 것인가? greeting 리소스의 representation은 “welcome”으로 업데이트되었으니 분명 그것은 아닐 것인데 대체 무엇일까?

        이론적으로 정확한 정답은 “Content-Location 헤더에 들어있는 uri가 가리키는 리소스”이다. 그러나 보통 Content-Location 헤더는 비어 있을 것이므로 현실적인 정답은 “uri를 모르는 어떤 리소스”이다. 그 메시지는 representation이 맞고, 어떤 존재하는 리소스에 대한 것이지만, 그 리소스를 가리키는 uri가 뭔지는 모른다. 이와 같은 representation을 unidentified representation이라고 하며, 어떤 payload가 unidentified representation인지 판단하는 방법은 RFC 7231의 “3.1.4.1. Identifying a Representation” 에 자세히 나와있다.

## 일의 메타

> 일에 대해 배운 것, 시도한 것, 느낀점들

### Output과 Impact에 대한 생각

고민이 많던 요즘, 우연찮게 [이런 글](https://theburningmonk.com/2019/11/how-to-break-the-senior-engineer-career-ceiling/)을 읽고, 고민에 대해서 메모를 적어보게 되었다.

> 요즘은 100%의 힘을 써서 100%(~80%)의 임팩트만 내는 식의 일 방식을 어떻게 벗어날 수 있을까?가 주요한 고민이다. 고민을 계속 하다보니깐 점점 구체적인 액션 플랜도 나오긴 하는데, 그럼 이제 당장 급하거나 짜치는 업무들을 쳐내는 시간을 쪼개서 장기적인 효율성을 위한 작업을 어떻게 해낼 것인가가 다음 고민이다. 일단 어떻게든 시간을 내서 해야겠다- 가 일단의 아이디어인데.. 고민을 하다보면 뭐가 좀 더 나올까?

글에 나오는 output과 impact에 대한 고민은 어디서 무엇을 하건 아마 유무형의 가치를 생산하고자 하는 한 계속 될 것 같다. 무조건 열심히 해서 결과를 내야한다는 결과지향주의적인 맥락은 아니고, 일은 적게 하고 확실한 효과를 내는 게 좋으니깐..? (자기기만일수도)

하여튼 현재 단계에서 달성 가능한 최대 output이 나오고 나면 바로 다음 단계의 output과 impact를 생각하게 된다. 그 과정에서 에너지를 들인만큼 impact를 가지는가에 대해 연결해서 생각하지 않을 수도 없다.

내가 이글의 정확한 타겟(Senior SWE) 독자는 아니지만, 요즘 하는 생각이랑 관련이 있는 것 같기도 하고 또 Senior/Principle이 뭘 해야하는지, 주변에 아무도 정확히 모르는 것 같은 와중 내용이 좋아서 글이 쭉쭉 읽혔다.

일단 (Important)Individual contributor(IC) 부터 되어야 할 수도 있지만, 요새는 그저 요구사항에 따른 output을 시간과 에너지를 짜내어서 여러개 내는 거 말고(‘releasing more features’), 좀 더 공들여서 도메인과 코드 베이스를 이해하고 더 나은 코드로 만드는 일을 병행하고 싶었는데, 그게 나에게나 팀에게나 프로덕트에게나 더 나은 임팩트가 되지 않을까 싶어서. 100% 120% 쥐어짜는 과정 속에서 (—물론 배우는 것도 있고 이런 생각을 하는 게 아직 경험도 많지 않은데 너무 이른가? 싶기도 하지만—)나오는 임팩트는 그다지 큰 것 같지 않다고 느낀다.

그 외에도 개인적으로 아래의 내용들이 인상깊었다.

> Writing more code or releasing more features alone doesn’t make you a better senior engineer. It’s about your ability to deliver a meaningful business impact through your execution. This is the change in mindset that will set you on your way to the next level.

> But the impacts you create by helping 10 engineers be 10% better would be an order of magnitude greater than your maximum output as an individual. That impact is also cumulative and longer-lasting as you help more and more engineers level up.

> You also need to be empathic to different people’s needs and constraints. The “right way” may be too far a stretch for some. It’s not your job to judge others for not reaching your lofty standards. But it is your job to help others improve, even if it means taking baby steps.

그러나 일단 제대로 된 Individual Contributor 부터 되어야겠지..

### 제품의 요구사항을 대하는 태도에 대하여 vs 그러나 코드 베이스는 어디로 가는가...

> "그렇기 때문에 초반에 확장성 있게(유연하게 대응 가능하도록) 프레임웍을 짜는게 서비스, 소프트웨어에선 특히 중요하죠."

지난 달에 했던 대화인데, 역시 또 한 달 사이에 경험과 생각은 끝없이 바뀌기 때문에.. 이 확장성있는 코드라는 것도 일정 정도는 기획과 요구사항의 최소한의 일관성이나 맥락, 일의 강도 등에 영향을 받는 것 같다는 생각을 한다.

대신 지난 달에 비해 일감이 왔을 때 바로 스트레스를 받거나 스스로 역량이 부족해서 생긴 이슈라고 생각하는 부분은 많이 줄었다. '프로덕트' 엔지니어로서 가져야 하는 마음가짐과, 프로덕트 '엔지니어'로서 하고 싶은 일을 어떻게 균형 맞추느냐가 참 중요한 것 같다.

난 모든 걸 엔지니어링적인 솔루션으로만 풀 수 있다고 생각하진 않는 편이고, 커뮤니케이션이 매우 중요한 직종이고 잘 해야 한다고 생각하는 사람이지만 여전히 급하게 짜느라 안좋은 모습이 된 프로덕트 코드가 좀 더 개선되어야 한다고 생각하고, 또 그렇게 하고 싶다. 지금으로선 일정에 맞추어 뭔가 해내는 게 내 역량 부족 때문인가 만 생각했는데, 최근 업데이트를 하면서 일의 우선순위와 상관없이 들어오는 일을 모두 처리했던 게 좀 아쉬운 부분이다. 그리고 대부분의 일감을은 시간을 들여서 천천히 본 뒤 해야하는데 그냥 건건이 생기는대로 딱 그 부분만 고치다보니 고쳐도 또 버그가 나고 또 버그가 나고 그런 것 같다.

그런데 한편으로는 역시 이게 시간확보 만으로 해결이 될까?라는 생각이 든다. 이미 프로덕트가 조금 성숙했으므로(더이상 뭐가 안되는 기능은 없다.) 이상적으로는, 10이라는 가용 자원에서 2 내지 3이 뉴 피쳐, 3이 운영 대응, 나머지 4-5 정도는 코드 개선에 사용해도 될 때가 아닌가. 그리고 처음부터 확장성있게 짜는 프로덕트도 있겠지만, 그렇지 못하는 경우라면 이후에 개선할 수 있는 기회가 주어져야 하는 것은 아닐까.

아직 주니어라 경험이 부족하기 때문에 나도 잘 모르겠다. 정답이 아니라(그런 건 없기도 하겠지만) 내 경험 안에서의 나름의 최선이나 이상적인 모습에 대해서 확신하기가 어렵다. 여기에 대해서 아직 생각이 정리되지가 않는다. 다음 달에는 좀 더 정리가 될까? 잘 모르겠다.

### 리팩토링 및 하고 싶은 부분

- 주요 기능에 테스트 코드 추가
- 모든 기획과 데이터 대조 정리
- Vue에서 eventbus, refs 등을 사용하는 방식 대신 store 사용하는 방식으로 고쳐보기
- helper function 리팩토링

## 공부

- 오브젝트 책 읽기: 중간에 서브 클래싱/서브 타이핑에 대한 발제를 했다. 많이 배울 수 있었다.
- 미적분 강의: 릴리즈 앞두었다는 이유로 또 여러가지 일정 때문에 많이 듣지 못했다. 이번 주에는 2개 정도 들어야겠다.
- "웹 앱 API 개발을 위한 GraphQL": 계속 조금씩 읽고 있는 중이다.

## 책

- "Vue.js 코딩 공작소"
- "손에 잡히는 10분 SQL"
    - 두 권은 이번 달에 꼭 다 읽고 싶은 책이다. 일일이 정독하지 않더라도 중요 부분을 쫙 훑고 싶다,
    - Vue 책을 통해서는 전반적으로 계속 사용하고 있는 Vue에 대한 지식을 정리, 고도화 하고 vuex를 다루는 방법까지 마스터 해보고 싶다.
    - SQL을 제대로 다루거나 배워본 적이 없어서 한 번 정도 짚고 넘어가고 싶어서 정리했다.

## 지난 달에 하고 싶었던 일들

- [x] 회사 일: 중요한 리팩토링 작업 무사히 마무리📍
    - [?] 과정도 계속 기록, 정리해보면 좋을 것 같다.
- [-] 밀린 개발 서적 독서
- [ ] 시작한 미적분 강의 꾸준히 계속 듣기
- [ ] "Interactive Data Visualization for the Web" 하나씩 따라하기

- 결국 전혀 안한 것들이 더 많네.. 회사 일 외에 시간을 낸다는 게 역시 쉬운 일은 아닌 것 같다.

## 다음 달에 해보고 싶은 것

- [ ] 회사 일: 위에서 이야기 한 것처럼 코드 개선 관련 작업들을 하고 싶다.
- [ ] 주문한 책들 읽기
- [ ] 미적분 강의
