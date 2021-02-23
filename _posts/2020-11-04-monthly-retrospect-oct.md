---
layout: post
title: Monthly Retrospect - 2020.OCT
description: "2020년 10월 정리"
tags:
  - Retrospect
share: false
---

# Summary

## 공부 및 작업

- 릴리즈

아마도 코로나 때문에 올해는 회고를 작성할 때마다 정말 이번 달이 빨리 지나갔다고 느끼지만, 이번 달은 유독 추석도 있고 해서 더 빨리 간 것 같다.

그래서 릴리즈 주간도 금새 돌아왔다는 느낌이 들었다. 얼마 전 거의 2년 간 한 프로젝트의 마지막 공식 릴리즈가 있었다. 오픈 후 1년 반 정도 계속해서 릴리즈가 있었다. 다행히(아마도 처음으로?) 별 이슈 없이 지나갔다.

이번 릴리즈에는 여유가 꽤 많이 있었는데, 덕분에 작업의 퀄리티가 훨씬 좋다는 느낌을 과정 속에서 많이 느꼈다. 역시 시간과 마음의 여유가 있을 때 코드도 작업도 잘 된다는 것을 또 깨달으며..

이번에 추가된 내용에서는 라우팅에 대한 내용과 중복 로직 개선 부분이 있었고 각각 깊이 생각해볼 수 있어 좋았다.

하지만 역시나 마지막에 급하게 추가된 스펙이 하나 있었고, 역시 급하게 추가하면 이슈가 많이 생긴다.. 다행히 qa를 빡세게 하면서 잘 진행할 수 있었다.

- 새로운 작업들
    - 스토리북 셋업을 해봤다. 버전이 6으로 오르면서 많이 바뀌어서 이전 버전 코드들 위주로 예제가 많아 그냥 공식 문서 위주로만 보면서 진행했는데 재밌었고 큰 이슈도 없었다. 다만 컴포넌트의 모든 상태를 prop으로 넘기지 않고 최대한 CSS로 컨트롤 하는 방법에 대해 고민중이다.
    - gatsby + netflify 셋업 + 도메인 연결을 해봤다. 항상 해보고 싶었던 작업인데 어느 날 갑자기 꽂혀서 새벽까지 진행했다. gatsby 셋업은 정말 쉽다. 템플릿 중 맘에 드는 걸 찾고 component shadowing을 익히는 부분부터가 조금 어려웠다. 아직 커스터마이징을 본격적으로 시작하진 않았다.
    netflify는 역시 명성에 걸맞게 정말 간편하고 좋았다. 너무 예전이긴 하지만 surge나 next를 사용했던 경험보다 더 편하게 느꼈다. (홈페이지의 UI/UX가 정말 좋다고 느꼈다.)
    무엇보다 처음으로 내 도메인을 사봤다. 가비아를 통해 도메인을 찾아서 샀고(원래 사려던 건 아니었지만..) netflify 네임서버로 교체도 했다.
    component shadowing 하고 커스터마이징 하면서 리액트와 타입스크립트도 아주 조금씩 다시 익혀볼 수 있을 것 같다.
    - observable 노트를 생성해봤다. 근데 정말 삽만 뜬 정도라 얼른 각종 d3 api들을 익혀야 한다.. 11월에는 꼭.. 그리고 observable의 개념적인 부분(cell 등)에 대해서도 알아가야 한다.

아무튼 10월에는 새로운 툴들을 익히고 직접 세팅하면서 재미를 많이 느꼈다.

## 다음 달에 하고 싶은 것

- storybook, css framework 구축
- 머릿속에 있는대로 gatsby 컴포넌트 커스터마이징
- observable로 기본 노트 완료하기