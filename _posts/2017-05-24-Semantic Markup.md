---
layout: post
title: 시멘틱 마크업(Semantic Markup)
description: "'시멘틱 마크업'이 도대체 뭘까?"
tags:
  - HTML5
  - Semantic Markup
  - 웹문서
comments: true
# link: 'http://tryhelloworld.co.kr/challenge_codes/120'
---

## 0. 시멘틱 마크업

처음 프론트엔드 개발을 공부하면, HTML(Hypertext Markup Language)을 배운다. 웹페이지는 결국 일종의 문서(document)라는 점을 잘 기억하고, 이 문서의 내용과 구조가 HTML에 의해 결정된다는 것까지 떠올리면 HTML이 얼마나 중요한 지 알 수 있다.

마크업은 엄밀히 말해 하나의 언어인데, [`태그 등을 이용하여 문서나 데이터의 구조를 명기하는 언어의 한 가지`](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EC%97%85_%EC%96%B8%EC%96%B4)다. HTML은 이러한 마크업 언어의 일종으로, 웹문서의 `내용`과 `구조`를 특정 
`태그`들로 구성해 **정보를 구조화** 한다.

> 참고: **CSS(Cascading Style Sheet)**는 이 내용과 구조에 스타일링을 입히는(즉 표현의 영역을 담당하는) 언어, **Javascript**는 동적인 표현과 데이터를 다루는 프로그래밍 언어다.

## 1. 구조화 - HTML 태그들

### 1-1. 중첩

HTML 태그들은 '중첩'이라는 속성을 가진다. 즉 태그 안에 태그가 또 들어갈 수 있다. 이러한 중첩을 통해 각 태그에 속하는 내용들이 구조화되고 서로 관계를 형성한다.

### 1-2. 속성

태그 안에 위치한 내용 중 하나로, 해당 태그에 대한 추가적 정보를 제공한다.
글로벌 속성에는 `id`, `class`, `hidden`, `lang`, `style`, `title`, `tabindex` 등이 있다.

## 2. 시멘틱 마크업과 검색엔진최적화(SEO)의 관계

검색엔진최적화(Search Engine Optimization)란, 웹사이트의 HTML 코드에서 정보를 모아 검색 키워드에 맞는 적절한 웹사이트를 보여주기 위한 것이다. 따라서 HTML의 요소들을 가지고 해당 웹페이지의 내용을 파악하고 그것이 검색엔진에 노출될 수 있도록 하기 위해서 시멘틱한 마크업이 필요하다. 

웹페이지에서 같은 모양으로 출력된다고 해도, 실제로 가지고 있는 의미는 서로 다를 수 있다. HTML 태그가 가진 의미에 따라 다르게 해석되기 때문이다. 예를 들어 `<header>`태그를 안쓰고도 제목 모양의 스타일링을 할 수는 있지만 그것은 '표현' 영역에 해당하고 내용-구조를 담당하는 HTML의 역할을 다 했다고 하기 어려운 것이다.

```html
<font size="6"><b>Hello</b></font>
<h1>Hello</h1>
```

위의 예시 코드에서 'Hello'는 같은 모양으로 출력되지만 의미는 다르다. 첫번째 Hello는 사실상 아무 의미도 가지지 않는다. 

즉 시멘틱 웹(Semantic Web)에서는 `웹 문서의 내용-구조를 파악하기 위해` 시멘틱 마크업이 중요하다.

## 3. 시멘틱 요소(semantic element)&비시멘틱 요소(non-semantic element)

non-semantic 
element
: div, span 등이 있으며 이들 태그는 content에 대하여 어떤 설명도 하지 않는다.

semantic element
: form, table, img 등이 있으며 이들 태그는 content의 의미를 명확히 설명한다,


* HTML5에서 추가된 시맨틱 태그

| tag	| Description |
|:-----:|:-----|
|header	|헤더를 의미한다|
|nav	|네비게이션을 의미한다|
|aside	|사이드에 위치하는 공간을 의미한다|
|section	|본문의 여러 내용(article)을 포함하는 공간을 의미한다|
|article	|분문의 주내용이 들어가는 공간을 의미한다|
|footer	|푸터를 의미한다|

## 참고

* [1.1 HTML5 Syntax Web page의 내용과 구조를 담당하는 HyperText Markup Language](http://poiemaweb.com/html5-syntax)

* [웹 문서를 만드는 언어, HTML과 CSS](http://www.beautifulcss.com/archives/791)