---
layout: post
title: Monthly Retrospect - 2020.APR
description: "2020년 4월 정리"
tags:
  - Retrospect
# image: '../../assets/images/spa_structure.png'
# comments: true
share: true
---

# Summary

- 5월 릴리즈 준비
    - 대기, 대기, 대기...
        - 앞의 라이브러리(?) 단에서 진행되어야 테스트 해 볼 수 있는 이슈가 이번 릴리즈의 메인 피쳐가 있었는데, 하나 테스트 해보고 나서 하나 버그가 나면 고쳐서 배포하는 과정이 꽤 오래 걸려서 대기가 많았다.
        - 서버나 라이브러리 작업이 먼저 진행되고 나면 그 후에 진행할 수 있는 일들이 많아서 거의 가장 마지막 단계에서 대기해야 하는 시간이 생기는데 결국 업무 프로세스나 배포 프로세스를 개선할 방법을 찾아야 조금이라도 해결이 될 것 같다. 안드로이드 개발자분과도 관련해서 대화를 좀 나눴었는데 프로세스 개선이 쉬운 것만은 아니라서 잘 될 지는 모르겠다.
- 커뮤니케이션
    - 다양한 피드백을 이제 너무 고민하지 않고 신속하게 할 수 있게 되었는데, 상대방과 나에 대한 신뢰가 쌓여서 그런 것 일까..? 좋은 건지 나쁜 건지 잘 모르겠다.
- 여행
    - 양양에 다녀왔다.
        - 생각보다 너무너무 좋았다. 마지막까지 걱정하면서 안가고 싶다고 이야기 했었는데 최대한 차 안, 방 안에만 있기로 서로 신신당부를 한 뒤 걱정 속에 갔다. 실제로 첫날은 밤에 걱정으로 잠을 못이룸(최고의 걱정쟁이..). 그래도 다행히 별 일 없이 다녀왔고, 낙산사와 그 앞의 바다가 너무 멋졌다. 친구들과 낮에 누워서 본 드라마 <Years & Years>도 기억에 남는다
        - 여행을 하면 돈도 들고, 다녀와서 일상으로 돌아오는 과정이 힘들어서 잘 안가곤 했는데 친구들 등살덕분에 용기내어 다녀오길 잘 한 것 같다. 이때 이후로 음식을 잘 소화 못하던 문제도 해결되고 스트레스도 엄청 경감되어서 잘 지내고 있다.

## 새로운 테마

- 재택근무
    - 재택으로 늘어난 내 시간을 잘 사용하기 위해 노력 중이다. 그래서 미뤄 둔 Data Visualization 책과 여러가지 책들을 조금씩이라도 읽고 있다.
- Component Reactivity & Event flow
    - 프론트엔드의 상태관리와 반응성에 관해 계속 걱정했었는데 조금씩 챙겨볼 수 있게 되었다. 특히 이번에 회사에서 만든 피쳐가 컴포넌트 내부에서 iframe을 통해 다시 통신과 컴포넌트 업데이트를 진행해야 해서 조금 복잡하고 애매한 상황들이 많이 생겨서 공부를 더 해보고 있다.
    - Vue mastery의 Reactivity 관련 강의를 보고 있다.

## 공부 및 작업

- 기억에 남는 회사 작업
    - iframe - drag and drop
    - 플랫폼 팀에 기여하기: 회의, 컨벤션 논의, 피드백 등 회사에서 팀원들과 함께 필요하다고 생각했던 문서를 쓰고 제안했다.
    - 개발환경이 yarn으로 바뀌고 패키지 캐싱이 잘 되어 배포가 엄청나게 빨라졌다. PnP 등에 대해서 다시 한 번 살펴봐야 한다.
    - vuex 공부하고 적용하기: 그동안 자주 안써봤는데 공부해서 적용을 잘 할 수 있었다. 단순히 기술 적용을 한 게 아니라 필요한 곳을 잘찾아 알맞게 적용한 것 같아서 만족스럽다.
- 기타
    - recursive merge — git
    - vuex, flux 공부

## 문화 생활

- <Years & Years> 근미래 아포칼립스로 정말 볼 만 하다.
- <Knock Down The House> from Netflx. <Years & Years> 보고 보면 딱이다. 그나마 희망적인.. AOC가 정말 멋졌다.

## 책

- <Interactive Data Visualization for the Web>
    - 조금씩 계속 읽고 있음. 앞 부분은 웹과 그 기반 기술에 대한 기본 사항들을 아주 잘 정리해놔서 한번 정리하기 좋았다.
- <나는 LINE 개발자 입니다>
    - 단순히 동기부여 뿐만 아니라 개발자로 성장하고 일하는데 필요한 여러가지 구체적인 팁들이 있어서 좋았다. 특히 처음에 들어온 멤버를 위해 정리해 둔 문서들이라든지, CHANGELOG를 읽는 것, 영문으로 문서 읽기, 그리고 가장 많이 나온 장애 후속 대응이 인상깊었다.
    - 나도 우리 플랫폼 팀에라도 위키 등을 만들면 좋을 것 같다는 생각을 하고 있다.
        - 처음 오는 사람을 위한 문서
        - 그동안 핫픽스를 진행했거나 크리티컬한 문제가 되었던 이슈들 모음
            - 나라면 regex method를 통해 정렬하다가 예외처리 빠트린 것(2020.1 핫픽스), input date의 min/max 값 같은 경우가 생각난다.

        → 이 부분은 제안했고, 팀원들도 좋아해주어서 진행해봐야 한다.

- <Vue.js 코딩 공작소>
    - vuex 부분을 읽었고 대체로 전부 다 본 거 같다.
- <IT에 몸담은 이들을 위한 지적생산기술>
    - 사실 이런 책에 특별한 내용이 있을 거라는 기대가 없어서 크게 기대 없이 조금 봤는데 나쁘지 않아서 틈틈이 읽어보고자 한다.

## 다음 달에 해보고 싶은 것

### 회사

- ref와 이벤트 버스를 컴포넌트 개선으로 제거하는 작업을 하고 싶었으나, iframe 문제 해결 때문에 오히려 더 사용하는 상황도 있었다. 언제 사용하고 언제 사용하지 않을지에 대해 정리해보면 좋을 것 같다.
- nextTick도 마찬가지다. 막연히 사용하면 안좋을 거라고 생각했는데 언제 사용해야 하고 언제 사용하면 안될지 등을 다시 한 번 체크해봐야 한다.

### 기타

- <코어 자바스크립트> 읽기

### 머리에 넣고 싶은 것들

- Vue reactivity
- JS advanced
