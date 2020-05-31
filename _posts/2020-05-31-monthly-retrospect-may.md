---
layout: post
title: Monthly Retrospect - 2020.MAY
description: "2020년 5월 정리"
tags:
  - Retrospect
# image: '../../assets/images/spa_structure.png'
# comments: true
share: true
---

# Summary

## 공부 및 작업

- 5월 정리를 하려고 한 달간 매일 적었던 업무 저널을 돌아보니 생각보다 정말 다양한 이슈들을 해결했구나 싶다. 아주 익숙한 프론트엔드 간단한 버그들부터 인프라(사소한 부분이지만)이슈, GA, CORS, CDN 연결, git, 커뮤니케이션과 프로세스 개선, 이슈는 아니지만 SSR이나 모듈 시스템 등에 대해서도 이야기를 많이 했고 찾아보고 했다. 아직 부분 함수 작성이나 에러핸들링등에 대해서는 잘 모르겠다. 그런데 이런 것들을 내 것으로 잘 남기려면 어떻게 해야 할까? 물론 경험으로 남은 것들은 다음 번에 시작할 때 큰 힘이 되긴 하지만 지식적인 부분들은 좀 더 많은 시간을 할애해서 공부할 필요가 있다.
- 사내 프론트엔드 플랫폼에서 계속 함께 하기로 한 프론트엔드 dojo 시간을 푸시해서 드디어 진행하기로 했다. 최근에는 Vue로 application 작성하는 방식에 대해서 이야기를 많이 하고 있다. 웹 프론트엔드를 더 모듈화히면서 어떻게 간단하고 쉽게 작성할 수 있을지에 대한 내용들인데 제대로 체화하기 위해 현재 진행하고 있는 리팩토링에 적용해보고 있다. 그후에 포스팅 등으로 정리해봐야 할 것 같다.
- 7월에 나가야 하는 작업들이 생각보다 빨리 끝나서 리팩토링을 진행 중이다. 리팩토링은 위에서 이야기 한 Vue application + 새로운 구조의 atomic component 적용을 통해 진행 중인데 쉽지가 않다. 아직은 주요 로직을 바꾸는 일에 집중하고 있다. 가장 복잡했던 컴포넌트를 번경하고 있어서 좀 더 그런 것 같다.
- 드디어(?) 내가 좀 더 주도권을 가지고 일을 진행한 점이 이번 달의 잘 한 점이다. 그동안에는 '나는 아직 주니어라..', '나는 아직 부족해서..' 등의 생각이 앞섰던 거 같다. 그렇게 수동적으로 하기 보다는 스스로 이것저것 시도하면서 결과적으론 좋았다. 좀 더 성장해서 더 많은 것들을 주도적으로 해보고 싶다. 아무튼 결국 내가 할 수 있는 일이 있으면 그냥 스스로 해야 한다는 생각을 더 하게 됐다.
- 데이터 시각화를 조금씩 만들어보려고 하고 있다.

## 일의 메타

### 릴리즈 전후 컨디션 조절하기

릴리즈 주간에 일에 집중이 잘 안된다. 물론 버그가 나왔을 때는 집중이 잘되는데 그 이외의 시간에서는 집중력이 많이 떨어지곤 했다. 시간이 나면 진득히 문서도 보고 공부도 하고 코드 정리도 하고 뭐 그런 거 상상했지만 잘 안되어서 스스로 좀 웃겼다. 당시에는 큰 이슈로 느껴졌으나 곧 잘 해결되긴 했다. 릴리즈 주간 바로 다음 주인 5월 2주차 쯤 부턴 괜찮았던 거 같다. 너무 항상 자신의 수행 그 자체에 집중하면 오히려 효율이 떨어질 수 있어서 노력하는데도 늘 나는 쉽지가 않다. 아무튼 꾸준한 컨디션을 유지하기 위해서는 아주 제너럴한 요건들 즉 평소의 컨디션 및 스트레스 관리, 일감 및 일정 관리 등을 잘 해야겠으나, 가장 중요한 건 어느 정도는 재미를 느끼는 혹은 하고 싶은 일을 하는 것이 아닐까 싶기도 하다.

### 자료 읽기

- 읽기 자료를 종종 킵해두는데, 그날 추가한 건 그날 바로 읽어야 할 거 같다.원래는 주 1회라도 몰아서 보려고 하는데 그것보다는 그날 읽고 나서 또 일주일 뒤에 한 번 더 보고 그래야 더 잘 남을 것 같다.

## 책

### Engineering

- < 코어 자바스크립트 >

  - 연휴 동안 많이 봤다.

- < IT에 몸담은 이들을 위한 지적생산기술 >

  - 찔끔찔금 보고 있다. 전체적으로 그냥 몇 번 스케밍 하고 넣어두려고 한다.

- < 손에 잡히는 10분 SQL >

  - 마찬가지로 조금씩 보고 있다.

- < Interactive Data Visualization for the Web >

  - 최근에 Observablehq에 있는 자료와 함께 좀 더 보면서 그래프를 하나 그렸다.

### 그 외

- < 우리가 빛의 속도로 갈 수 없다면 >, 김초엽
- < 내 일을 쓰는 여자 >, 샐리 헬게슨, 마셜 골드스미스(정태희, 윤혜리 옮김)

  - SF 문학 한 권, 비문학 한권 읽었다. 후자는 좋은 내용도 있고 애매한 내용도 있다. 적당히 두세시간 정도면 대략 읽을 수 있다.

- [Rest of World](https://restofworld.org)

  - Sophie Schmidt(아버지는 전 구글 회장 Eric Schmidt)가 파운더인 글로벌 잡지가 드디어 live 됐다. 영미권을 제외한 곳들에서 기술이 어떤 영향을 만들고 있는지에 대해 알린다고. 실리콘 밸리의 중심에서 자란 사람이 그 밖의 이야기를 들어야 한다고, 들려주겠다고 하는 게 참 대단하게 느껴진다. 자신이 가진 리소스와 능력으로 이런 걸 만들다니 정말 멋지고.. 테크 업계에서 지낸 뒤 이런 선택을 한 것부터 역시 밀레니얼 여성이라 할 수 있는 기획이라는 생각이 든다. 아래는 창립자의 말.

> “Our mission is to document what happens when technology and human experience collide in places that are often overlooked and underestimated. We’re here to connect the dots: Across languages and tech sectors, between common problems and shareable solutions.”

> “As software began to eat the world, the world began to bite back. Because it turns out that the so-called “universal values” hard-coded into technology platforms built in California aren’t that universal after all.”

> “In the US, tech outlets tend to focus on the domestic giants, missing how these companies influence global outcomes (by their presence or their absence). And even in thriving hubs like Nairobi and Bangkok, tech reporting is largely preoccupied with funding rounds, CEOs and unicorns. While billions of people suddenly had access to the world’s information — seeing their lives change virtually overnight — there was little questioning about what this all meant. Instead, more stories about Jack Dorsey’s fasting regime. (Sorry, Jack.) This information gap is why I started Rest of World.”

## 다음 달에 해보고 싶은 것

### 회사

- 리팩토링 완벽하지 않아도 어느 정도는 잘 마무리 하기

### 기타

- 에러 핸들링 코드와 로직 정리하기 등
- 시각화 작업
- You don't know JS 읽기