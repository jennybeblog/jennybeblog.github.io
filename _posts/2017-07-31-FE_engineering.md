---
layout: post
title: FE | Interview Questions
description: "프론트엔드 개발자가 답해야 할 질문들"
tags:
  - Front-end interview questions
  - Front-end
  - 프론트엔드
# image: '../../assets/images/semantic_web.jpg'
comments: true
share: true
# link: 'http://tryhelloworld.co.kr/challenge_codes/120'
---

* 프론트엔드 엔지니어 인터뷰 질문들 - 출처

## HTML에 관련된 질문들:

* doctype이 무엇을 하는 것이고, 몇 번 지정할 수 있나요?

  * "문서 형식 선언"(DTD: Document Type Declaration)
  * 마크업 언어에서 문서 형식을 정의하는 것으로, 문서들을 일정한 규칙을 정하여 통합하고, 다양한 문서간의 표준을 제시하기 위해 쓰인다.
  * 문서 형식은 페이지를 렌더링을 하기 전에 브라우저가 가장 먼저 확인하는 내용으로, 제대로 적혀있지 않으면 다음 질문의 답변에 적혀있는 것과 같은 문제가 생긴다.
  * 유효성 검사 시 검사 도구들 역시 문서 형식을 확인하기 위해 doctype을 확인한다. 따라서 제대로 명시하지 않았을 경우 유효성 검사에 문제가 생긴다.
  * 문서 상단에서 1회만 지정한다.
  * [참고](http://www.blooberry.com/indexdot/html/tagpages/d/doctype.htm)
  * `<meta http-equiv="Content-type" content="text/html; charset=utf-8" />` - [출처](http://webdir.tistory.com/40)

* 표준모드(standards mode)와 쿽스모드(quirks mode)의 다른 점은 무엇인가요?

  * 쿼크 모드(Quirks mode, 쿽스 모드): 오래된 웹 브라우저를 위하여 디자인된 웹 페이지의 하위 호환성을 유지하기 위해 W3C나 IETF의 표준을 엄격히 준수하는 표준 모드(Standards Mode)를 대신하여 쓰이는 웹 브라우저 기술을 가리킨다. 같은 코드라도 웹 브라우저마다 서로 다르게 해석하므로 전혀 다른 결과물을 보여주게 된다.
  * 쿼크 모드의 발생 원인: DOCTYPE 선언이 존재하지 않거나 잘못 적혀있을 경우, 웹 브라우저는 문서를 쿼크 모드로 해석한다. DOCTYPE 선언 내의 URL이 생략된 경우, 웹 브라우저는 문서를 쿼크 모드로 해석한다. 인터넷 익스플로러의 경우, DOCTYPE 선언 윗쪽에 주석이나 다른 문자가 들어갔을때에 문서를 쿼크 모드로 해석한다.
  * 만약 잘 작성된 문서형을 찾는다면 웹 브라우저들은 페이지 레이아웃을 그리려 할 때 “표준 모드”라고 불리는 렌더링을 사용한다. 표준모드에서, 브라우저들은 일반적으로 CSS 사양에 따라서 페이지를 렌더링 하려고 노력한다.
  * Quirks Mode는 흔히 비표준 모드라고 이야기하는 것이다. IE의 Quirks Mode는 w3c의 박스 모델을 사용하지 않기 때문에 서로 다른 렌더링 결과를 보여준다. **즉, 크로스 브라우징에 문제가 생긴다.**
  * [참고](http://www.clearboth.org/14_choosing_the_right_doctype_for_your_html_documents/)

* XML과 XHTML의 다른 점은 무엇인가요

두 가지 모두 하나의 웹 문서 규격이지만,

  * XHTML은 기존에 사용되던 HTML 규격이 가진 문제점을 극복하고, 보다 다양한 분야에 응용될 수 있도록 해주는 여러가지 확장된 기능을 포함하고 있습니다.
  * [참고](http://ukjin.tistory.com/57)

* XHTML을 이용한 페이지의 한계점은 무엇이 있나요?

* application/xhtml+xml으로 지정한 페이지에 어떠한 문제가 있나요?

* 다국어가 포함된 페이지는 어떤 방식으로 제공하나요?
* 다국어 페이지를 제공하는 여러 방법에 대해 설명해주세요.

  * 최상의 방법은 모든 페이지를 UTF-8 형식으로 제공하는 것입니다.
  * 그리고 양식 페이지가 UTF-8 형식으로 되어 있다는 사실을 브라우저가 인식할 수 있게 해야 합니다. 페이지의 인코딩 방식을 브라우저에 알려야 합니다.
  * 양식 데이터를 수신하는 스크립트가 실제 반환된 데이터가 UTF-8을 사용하는지 확인하는 것이 바람직합니다(잘못된 경우 사용자가 인코딩 변경). UTF-8은 다른 인코딩에는 나타나지 않는 매우 특별한 바이트 패턴을 갖기 때문에 이러한 확인이 가능합니다. 비UTF-8 데이터가 수신되면 오류 메시지를 전송해야 합니다.

* data-속성은 무엇을 하는 것인가요? 사용했을때 이점은 무엇인가요?

  * 사용자 정의 속성(Custom data attribute)
  * HTML5에 추가된 중요한 시멘틱요소 중 하나로, 불필요하게 id나 class를 이용해(스타일과 상관없으므로) 식별하고자 했던 데이터 문제를 해결할 수 있게 되었다.
  * 기존의 id/class 사용은 css 해석 속도도 떨어트리고 개발자들에게도 무슨 데이터를 어떻게 다룰지에 대한 명확한 표현이 부족했다.
  * HTML5의 Custom Data Attributes를 이용하면 마치 XML을 표현하듯 HTML 문서에 특정 엘리먼트의 설명을 구체적으로 할 수 있다. HTML의 의미있는 표현도 가능하고 이 의미로 만들어진 element에 identifier나 style class가 아닌 **데이터의 표현과 관리**가 가능해진 것이다.
  * CSS에서 스타일링을 하는 경우에는 각괄호 `[]`안에 넣어 스타일링 할 요소를 선택할 수 있다. `[data-item]{ color: red }` - [참고](http://blog.saltfactory.net/using-html5-custom-data-attributes/)

* HTML5를 오픈웹플랫폼(open web platform)으로 생각해본다면, 어떤 것들로 구성돼 있을까요?
  * HTML5, CSS3 (선택자, 미디어쿼리, 텍스트, 백그라운드와 보더, 색깔, 2D/3D 변형, Transitions, Animations, 다중 컬럼 모듈)와 같은 웹 표준, CSS Namespaces, SVG, WAI-ARIA 1.0, ECMAScript, WebGL, Web Storage, Indexed Database API, Web Workers, WebSocket Protocol/API, Geolocation API, Server-Sent Events, Element Traversal, DOM Level 3 Events, Media Fragments, XMLHttpRequest, Selectors API, CSSOM View Module, Cross-Origin Resource Sharing, File API, RDFa, WOFF, HTTP 1.1 (part 1-7), TLS 1.2, and IRI.

* 쿠키(Cookies)와 세션저장소(sessionStorage)와 로컬저장소(localStorage)의 차이점을 설명해주세요.

  * 웹 페이지에서 데이터를 저장하는 방식들
  * 쿠키: 서버가 유저를 기억하는 수단으로 전통적으로 사용되어 왔다. HTML header에서 서버와 통신을 한다. 만료 기한이 있는 키-값 저장소다. `document.cookie`로 쿠키 정보를 볼 수 있다.
    * HTTP 요청은 상태를 가지고 있지 않으므로 브라우저가 요청을 보낼 때 서버가 해당 요청만으로는 누가 요청을 보내는 지 알 수 없다.

  ```javascript
  // 쿠키를 저장하고, 불러오려면 자바스크립트에서 getCookie(), setCookie() 함수를 선언해 사용합니다.

  function setCookie(cname, cvalue, exdays) {
    var d = new Date();
    d.setTime(d.getTime() + (exdays*24*60*60*1000));
    var expires = "expires="+d.toUTCString();
    document.cookie = cname + "=" + cvalue + "; " + expires;
  }
  function getCookie(cname) {
    var name = cname + "=";
    var ca = document.cookie.split(';');
    for(var i=0; i<ca.length; i++) {
        var c = ca[i];
        while (c.charAt(0)==' ') c = c.substring(1);
        if (c.indexOf(name) != -1) return c.substring(name.length,c.length);
    }
    return "";
  }
  // 출처: http://nubiz.tistory.com/540 [Life is an egg.]
  ```

  * 세션 스토리지/로컬 스토리지(key-value)는 모두 웹 스토리지로 window 객체 안에 들어있으며 HTML5에서 표준으로 지정되었다. 쿠키에 비해 큰 데이터를 저장할 수 있으며 서버로 전송되지 않으므로 서버를 간단하게 설계할 수 있다는 장점을 가진다. 하지만 로컬 스토리지는 데이터에 유효기간이 없고(하드 디스크 등에 저장하므로), 세션 스토리지는 창을 닫으면 데이터가 초기화된다.
    * 로컬 스토리지: `window.localStorage`에 위치한다. 값으로 문자열, 불린, 숫자, null, undefined 모두 저장 가능하지만 문자열로 변환된다(객체가 toString 메서도가 호출된 형태로 저장되기 째문). 객체를 통체로 저장하려면 `JSON.stringfy`를 사용하고 받을 때는 `JSON.parse`를 사용하면 된다.
    > 메소드: `localStorage.setItem(키, 값)`으로 로컬스토리지에 저장한 후, `localStorage.getItem(키)`로 조회하면 됩니다. `localStorage.removeItem(키)`하면 해당 키가 지워지고, `localStorage.clear()`하면 스토리지 전체가 비워집니다.
    * 세션 스토리지: `window.sessionStorage`에 위치한다. 메소드는 모두 같다. 로컬 스토리지와 달리 데이터의 영구보관만이 불가능하다.
  * 굳이 서버로 전송할 필요없는 데이터는 웹 스토리지에 저장하는 것이 좋다.

* <script>, <script async>와 <script defer>의 차이점에 대해 설명해주세요.
  * 먼저, 인라인 스크립트와 async 또는 defer 속성이 없는 스크립트는 **브라우저가 페이지의 파싱을 진행하기전에** 즉시 내려받고 실행된다.
  * `async`: 스크립트의 비동기적 실행을 가리킨다. 내려받는 즉시 바로 실행된다. 즉 순서대로 다운로드가 시작된 스크립트라도 순서대로 실행되지는 않는다. 따라서 DOM을 수정하는 스크립트의 경우에는 async를 사용하지 않는 게 좋다. 인라인 스크립트에는 효과가 없다.
  * `defer`: 문서가 파싱 된후에 스크립트가 실행되어야 한다는 것을 가리킨다. 아직 모든 주요 브라우저에서 구현되지는 않았기 때문에 조심해야 한다.
  * async 혹은 defer 된 스크립트는 모두 외부 스크립트의 다운로드가 페이지 파싱이나 다른 스크립트의 다운로드 프로세스와 동시에 진행된다. 문서 parsing 작업의 중단 없이 동시에 내려받게 되며, 선택적으로 onload handler를 지정해서 일반적인 초기화 작업도 진행할 수 있다.
  * 둘의 차이를 결정짓는 중요한 것은 바로 **스크립트가 실행되는 시점**이 서로 다르다는 것인데, async script는 window의 load event 전 내려받는 즉시 바로 실행되는 데 반해 defer script는 문서의 parsing 작업이 끝난 후 DOMContentLoaded event 전에 문서에 삽입된 순서에 따라 실행된다.
  * 일반적인 스크립트 태그 같은 경우에는  html 파싱(Parsing) 중, 스크립트 태그를 읽게 되면 잠시 파싱을 멈추고 스크립트를 다운받아 실행한 후에 다시 파싱 작업을 이어간다. 이 경우에, html 태그의  앞부분에 스크립트 태그를 배치하게되면(특히나 헤드 태그 내에) 페이지 렌더링이 시작되기도 전에(페이지 렌더링은 body 태그의 시작과 함께 시작된다) 스크립트를 다운로드하고 실행하는데 시간을 할애하게 된다. 사용자의 입장에서 생각해봤을 때, 당신의 웹 페이지를 보는 사용자는 스크립트가 다운로드 되는 동안 텅빈 하얀 페이지를 보고만 있어야 한다. 물론 짧은 스크립트일 때는 이 시간은 극히 짧으니 그리 신경 쓸 필요가 없다, 그렇지만 만약에 인터넷 커넥션이 느리거나 사이즈가 큰 스크립트를 다운받는다면 아마 사용자는 긴 시간동안 페이지 로딩을 기다려야 할 것이다.

+ CORS(HTTP 접근 제어 access control): Cross-origin HTTP Request
  > 처음 전송되는 리소스의 도메인과 다른 도메인으로부터 리소스가 요청될 경우 리소스는 cross-origin HTTP 요청에 의해 요청된다.

* CSS<link>를 <head></head>사이에 쓰는것과 JS<script>를 <body></body>뒤에 사용하는것은 좋은 사용법일까요? 어디에 배치하는게 좋을까요?
  * <script>는 어디든 배치될 수 있지만 위에서 아래로 HTML 문서를 읽는 브라우저 특성상, head 태그에 외부 스크립트가 배치 될 경우, 페이지 렌더링이 시작되기 전에 스크립트가 먼저 다운로드된다. 그 후 파싱 -> 실행이 일어난다. 따라서 이런 경우 만약 스크립트 파일이 크다면 body 렌더링이 시작되기 전에 스크립트를 실행하는 데 많은 시간을 할애할 수 있다. 하지만 만약 body 태그의 마지막에 배치하게 되면 HTML 페이지의 내용이 전부 렌더링 된 후에 스크립트를 다운받으므로 사용자 입장에서는 페이지 로딩시간이 줄어든다.

* progressive rendering이란 무엇인가요?

  * 가능한 한 빠른 표시를 목적으로 내용을 렌더링하는 데 사용되는 기술을 가리킨다.
    * 1. `Lazy Loading`: 페이지 로드 시 자바스크립트가 모든 이미지를 로드하는 대신 브라우저 뷰포트에 들어올 때 이미지를 로드하는 위치를 파악해서 지연 로드하는 것을 뜻함.
    * 2. 가장 먼저 렌더링 되어 브라우저에 보여져야 할 최소한의 CSS/내용/script에 우선순위를 부여해서 렌더링 하는 것. (domready, load)

* SPA란?
  * 모바일 웹(모바일 환경에 맞춰진 웹 페이지)에 대한 니즈가 폭발적으로 증가하면서 성능 이슈가 생기면서 SPA 기법이 등장했다.
  * SPA는 브라우저에 로드되고 난 뒤에 페이지 전체를 서버에 요청하는 것이 아니라 최초 한 번 페이지를 전체 로딩한 후 데이터만 변경해 사용할 수 있는 웹 애플리케이션을 의미한다. 전통적인 웹 방식은 SPA 방식에 비해 요청 시마다 새로고침이 일어나서 렌더링 해야 하므로 성능 문제가 생겼다.
  * 서버의 역할은 JSON 파일만 보내주는 역할을 하고, HTML을 그리는 역할은 클라이언트 측에서 자바스크립트가 수행하게 되었다. `클라이언트 사이드 렌더링` (Angular, backbone 같이 SPA를 만들기 쉬운 JS 프레임웍의 등장.)
  * 클라이언트 사이드가 무거워지자 View 관리를 위해 React가 등장했다.
  * `클라이언트 사이드 렌더링`
    * 1. HTML 다운로드
    * **2. JavaScript 다운로드**
    * **3. JavaScript 해석**
    * **4. Fetch Data from API**
    * 5. 유저가 내용을 볼 수 있게 됨.
      * 장점: 사용자의 행동에 따라 필요한 부분만 다시 읽어들이므로 서버 측에서 렌더링해서 전체 페이지를 다시 읽어들이는 것보다 빠른 인터렉션을 기대할 수 있다.
      * 단점:
        * 1~3 까지의 과정을 모두 마친 뒤에야 콘텐츠가 보여지므로 초기 구동 속도가 느리다. (초기 구동 이후의 인터렉션에서는 빠르지만)
        * SEO(검색 엔진 최적화) 문제가 존재한다. 대부분의 웹 크롤러/봇들이 JavaScript 파일을 실행시키지 못하기 때문에 HTML에서만 콘텐츠를 수집하고 클라이언트 사이드 렌더링 페이지는 빈 페이지로 인식한다.
        * 보안 문제도 발생한다.
  * `서버 사이드 렌더링`
    * 1. HTML 다운로드
    * 2. 유저가 내용을 봄.

+ 모바일 웹: `m.`으로 시작하는 웹 사이트들. 풀 브라우징 방식으로 페이지를 이동하여 앱 실행 속도가 느리다.
+ 웹 앱: 웹을 기반으로 작동하며 모바일 웹과 근본적인 차이는 없으나 표현 및 구동 방식을 앱처럼 만들어 놓아 다른 UX를 제공한다. native app보다 성능이 떨어진다.
+ 네이티브 앱: 일반적인 어플. 성능/기능이 우월하지만 개발기간이 길고 비용이 많이 든다. 노출이 어렵고 사용자에 대한 진입장벽이 웹에 비교해 높다.
+ 하이브리드 앱: 웹과 네이티브 앱이 합쳐진 것으로 앱처럼 만들어 놓은 뒤 작동은 웹 서버를 동일하게 사용하는 것을 뜻한다. 성능상에 아직 문제가 존재한다.
+ 프로그레시브 웹 엡(PWD): 웹의 장점인 접근성을 살리면서 디바이스의 캐싱을 이용한다. 설치 전에는 검색에 노출되는 웹 사이트(모바일 웹)이지만, 주로 방문하는 웹 서비스를 앱처럼 설치할 수 있다. 모바일 환경에 대응하기 위해 고안된 웹의 전략이라고 볼 수 있다. 애플리케이션 쉘 아키텍처를 사용하는 PWD는 모바일 웹의 느린 속도를 보완한다. 디바이스에 설치되면 독립적인 앱으로 작동되고 브라우저 기반으로 작동하지 않는다. [참고](http://asfirstalways.tistory.com/262)

* HTML templating language를 사용해 본 경험이 있나요?

## CSS 관련 질문들:

* class와 id의 차이점에 대해서 설명해주세요.

  * 공통점: 어떤 태그든 그 내용이 갖는 의미와 역할을 통해 요소를 구분해서 나타낼 수 있음.
  * 차이점: 한 페이지 내에서 여러 번 반복될 필요가 있는 스타일은 클래스 선택자를 사용하고, 단 한번 유일하게 적용될 스타일은 ID선택자를 사용하는 것이 좋다. 왜냐면 class 속성은 *어떤 분류 안에 포함된* 요소의 특성을 정의하는 데 사용되고, id 속성은 어떤 요소에 대해 유일한 특성을 정의하기 때문이다. class 속성은 속성값을 두 개 이상 가질 수 있다. 그래서 클래스 선택자를 사용하면 한 태그 내에서도 여러종류의 스타일 규칙을 적용할 수 있다.
  * 그래서 클래스 선택자는 글자색이나 글자 굵기 등 나중에 다른 곳에도 적용할 수 있는 스타일을 지정하고, ID선택자는 웹 문서 안에서 요소의 배치 방법을 지정할 때 자주 사용한다.
  * id 선택자의 우선순위 > 클래스 선택자의 우선순위 : 따라서 우선적으로 적용되어야 할 스타일을 id 선택자를 사용해 정의하는 것이 좋다.

+ 하위 선택자와 자식 선택자
  * 하위 선택자 : `section ul`
  * 자식 선택자 : `section > ul`
  * 하위 선택자는 부모 요소에 포함된 '모든' 하위 요소에 스타일을 적용하고, 자식 선택자는 부모의 바로 아래 자식 요소에만 적용한다.

+ 인접 형제 선택자와 일반 형제 선택자
  * 인접 형제 선택자 : `h1 + ul`
  * 일반 형제 선택자 : `h1 ~ ul`
  * 같은 부모 요소를 가지는 요소들을 형제 관계라고 부른다. 인접 형제 선택자는 형제 중 *첫번째 동생 요소*가 조건을 충족시킬 때만 스타일링을 적용하고, 일반 형제 선택자는 *조건을 충족하는 모든 동생 요소*에 스타일링을 적용한다.

+ 속성 선택자
  * E[attr^="val"]형식은 "val"으로 시작하는 속성값을 선택합니다. 예를 들어 웹 문서에서 외부로 연결되는 링크가 있을 경우 http://로 시작하는지 확인하기 위해 이 선택자를 쓸 수 있습니다. 반대로 E[attr$="val"]형식은 "val"으로 끝나는 속성값을 선택합니다. 이 선택자는 예제6에 나온 것 처럼 어떤 파일이 링크될 경우, 그 파일의 확장자를 확인하기 위해 쓸 수 있습니다.

  ```html
  /* CSS */
  /* E[attr]형식 */
  a[href] { background: yellowgreen; color: black; }

  /* E[attr="val"]형식 */
  input[type="text"] { width: 150px; border: 1px solid  #000; }

  /* E[attr$="val"]형식 */
  a[href$=".xls"] { background: darkgreen; }

  <!-- HTML -->
  <a href="one.html">E[attr]형식</a>
  <input type="text" name="name">
  <a href="one.xls">E[attr$="val"]형식</a>
  ```

* "reset" CSS가 무엇인지, 어떻게 유용한지 설명 해주세요.

  *

* Floats가 어떻게 동작하는지 설명해주세요.

  * `float: left | right | none | inherit`
  * `float` 속성은 요소를 페이지의 한 쪽으로 밀어주는 역할을 하는데, 바깥에 글자들이 있다면 주변을 감싼다. 잘 사용하면 레이아웃을 형성할 수 있다.
  * 만약 플로트된 요소의 크기가 바뀌면, 텍스트 주변의 흐름이 바뀌면서 새로운 사이즈에 맞게 바뀐다.
  * 어떤 이미지에 `float: left;`를 적용하면, 이미지는 다른 블록 레벨 요소의 마진, 패딩, 보더 속성에 닿을 때까지 왼쪽으로 이동한다. 다른 요소들은 오른쪽으로 흐릅니다.
  * [참고 - CSS tricks](https://css-tricks.com/all-about-floats/)

+ clear 속성

  * float 속성을 가지고 있는 요소 주위의 요소에 clear를 하면, float 속성으로 인해 생겼던 흐름이 사라진다.
  * `clear: left`를 설정하면, 요소가 플로트 요소 아래로 떨어진다. 즉 흐름이 사라지는 것이다.
  * 따라서 float를 설정한 요소 주위에 다른 요소들이 오지 못하게 할 때 쓴다.

+ position 속성

  * `absolute`: 원하는 위치에 정확히 배치 가능하다. 부모의 요소를 기준으로 설정된다. 부모가 없는 경우 페이지 자체에 상대적으로 배치한다.

  * `relative`: 자기 자신 요소 자체를 기준으로 상대적 위치를 지정한다.

  * `fixed`: 뷰포트나 브라우저 창 자체를 기준으로 배치된다. 뷰포트는 변동이 없으므로 아무리 스크롤 해도 fixed 요소는 그 자리에 그대로 배치된다.

  * `static`: 문서의 일반적인 흐름에 맞게 배치된다.

* z-index에 대해 설명해주세요.
 * `z-index: auto | number | initial`
 * 요소의 z축 위치에 대한 속성으로 숫자가 낮을 수록 뒤에, 높을 수록 앞에 배치된다. 음수도 가능하다.
 * **z-index는 position 속성이 적용된 요소에서만 작동한다.**
 * floating 요소들은 position이 지정된 블록과 지정되지 않은 블록 사이에 쌓인다. - [참고 - MDN](https://developer.mozilla.org/ko/docs/Web/CSS/Understanding_z-index/Stacking_and_float)

+ text-indent 속성

  *

* BFC(Block Formatting Context)에 대해 설명해주세요

  * 블록 서식 문맥은 웹 페이지의 블록 레벨 요소를 렌더링하는데 사용되는 CSS의 비주얼 서식 모델이다. 블록박스의 레이아웃이 결정되고 float끼리 영향을 서로 미친다.
  * float의 위치 선정 및 해제(clear) 규칙은 동일한 블록 서식 문맥에 있는 것들에만 적용된다. 즉 다른 블록 서식 문맥의 레이아웃에는 영향을 주지 않으며, clear는 동일한 블록 서식 문맥 내의 이전 플로트만 해제한다.

* 클리어링(Clearing) 기술에는 어떤 것들이 있으며, 어떠한 경우에 어떻게 사용하는 것이 적절한지 설명하세요.

  * `float` 속성이 부여된 엘리먼트는 부모 엘리먼트의 높이에 영향을 주지 않으며, 레이아웃의 좌/우로 배치되면서 주변 콘텐츠의 배치에도 영향을 미친다.
  * clearing 기술은 이 float 속성이 주변 엘리먼트의 배치에 더 이상 영향을 미치지 않도록 **해제**시키는 속성이다.
  * `부모에도 float`: 자식 엘리먼트의 높이를 부모에도 반영하는 방법으로는 부모에게도 float 속성을 부여하는 것이 있다. 하지만 부모의 너비가 자식의 너비를 담을 수 있을 정도로만 줄어들기 때문에 브라우저 크기에 따라 너비가 가변적이어야 할 경우, 또 여러 번 중첩된 경우 계속 모든 조상에게 float를 적용해야 하므로 문제가 된다.
  * `부모에 overflow`: 자식 엘리먼튼의 높이를 부모에도 반영하는 방법으로 부모 엘리먼트에  `overflow: auto` 또는 `overflow: hidden` 속성을 부여하는 방법이 있다. 하지만 자식의 너비가 넘치는 경우 스크롤바가 생기거나 넘치는 부분이 잘리는 문제가 생긴다.
  * `clear`: 빈 엘리먼트에 `clear: both;` 속성을 부여해 부모가 자식의 높이를 인식하도록 한다. 하지만 의미 없는 빈 엘리먼트를 이용하므로 시멘틱상 바람직하지 않다.
  * `:after`: 가상 선택자 중 가상 엘리먼트 `:after`를 사용해서 부모 컨테이너에 `#container:after {content: ''; display: block; clear: both;}`를 적용한다.
  * 부모 요소에 `display: inline-block` 속성을 추가한다. inline-block을 가진 요소는 float된 자식의 높이만큼 늘어나기 때문이다. 하지만 박스가 끝나는 지점에 4px의 공백이 생긴다.

* CSS 스프라이트(CSS Sprites)를 설명하고, 페이지나 사이트를 어떻게 향상시키는지 설명하시오.

  * 작은 이미지들을 여러 개 사용해야 할 경우, 작은 이미지들이 들어있는 하나의 커다란 이미지를 만들고 해당 이미지를 쓰는 경우에 해당 position을 적용해주는 방식. 렌더링할 리소스가 줄어드므로 성능이 향상된다.

* Image Replacement를 사용해야 할 때, 선호하는 기술과 언제 사용하는지를 설명 해주세요.

  * 이미지 대체는 시각장애인들이 이미지 요소의 정보를 얻을 수 있도록 하기 위해 screen reader 기가 읽을 수 있도록 넣는 속성, 또 어떤 이유로 이미지가 로드 되지 않았을 때 이미지 대신 볼 수 있는 텍스트를 제공하는 것이다.
  * <image>태그의 경우 `alt` 속성 및 `attr` 속성을 쓴다.
  * background-image의 경우 대체가능한 태그로 이미지에 대한 설명을 쓰고 background-image에 대한 태그를 숨긴다.

* 브라우저 스펙차이에 따른 이슈는 어떤것들이 있는지 설명해주세요.

  * 같은 CSS 속성을 넣어도 다른 디자인으로 표현되거나 레이아웃이 깨질 수 있다.

* IE box model과 W3C box model의 차이점을 설명헤주세요.
  * W3C 박스 모델의 경우, width, height를 정하는 기준으로 `box-sizing` 속성의 기본값은 content-box이다. (content, padding, border, margin에서 content기준)
  * border-box는 border까지로 범위를 넓히는 것이 W3C 기본 정의이다. 그러나 IE에서는 border-box가 `box-sizing`의 기본이 된다.

* 시각적으로 보이지 않게 만드는 방법에 대해 설명해주세요.
  * `display: none | invisible;` : 위치를 아예 없에는 방식
  * `visibility: `: 보이는 것만 숨김.
  * `width`, `height` 값을 0으로 설정한 뒤, `overflow: hidden;`을 설정한다.
  * `position: absolute;`, `right/left` 값을 -1000 등으로 설정해서 바깥으로 내보내 버린다.
  * `text-indent: -9999`

* 컨텐츠를 안보이게 하는 기술들의 차이점을 설명하시오.(그리고 스크린 리더(Screen readers)에서 접근이 가능한 방법은?)

  * `display` vs `visibility`
  * `display: none`은 요소를 레이아웃 흐름에서 제거하고 닫른 엘리먼트들이 채울 수 있다. SR이 내용을 읽지 못한다.
  > "will make the element not participate in the flow/layout
can (depending on the used browser) kill Flash movies and iframes (which will restart/reload upon showing again), although you can prevent this from happening with iframes. the element won't take up any space. for layout purposes it's like it does not exist
will make some browsers/devices (like the iPad) directly take back memory used by that element, causing small hickups if you switch between none and an other value during animations"
  * `visibility: hidden`은 렌더되므로 기본 레이아웃 흐름에 존재하지만 눈에 보이지 않는다. 국내의 SR이 인식한다.
  > "the element won't be painted AND don't recieve click/touch events, but the space it takes is still occupied. because it's still there for layout purposes, you can measure it without it being visible. changing content will still cost time reflow/layouting the page. **visibility is inherited, so this means you can make subchildren visible by giving them visibility: visible;** - [참고](https://stackoverflow.com/questions/3475119/css-properties-display-vs-visibility)
  * `overflow: hidden;`은 어디서든 읽을 수 있따.

* CSS 요소핵(CSS property hacks)을 조건부적으로 .css파일안에 넣으시나요 혹은 다른 방식이 있나요?

  *

* 기능이 제약된 브라우저를 위해서 어떤 방식으로 페이지를 만드나요? 어떠한 기술과 절차를 거치는지 설명하시오.

  * 브라우저별 벤더 프리픽스, 폴리필

* 그리드 시스템(Grid system)을 사용한 적이 있나요? 있다면 어떠한 것을 선호하나요?

  * 전체 너비 pX을 고정한 뒤 12 column으로 row/col class를 만들어서 고정해놓고 보면서 레이아웃을 만들 수 있다.

* 미디어 쿼리(media queries)를 사용한 적이 있나요? 혹은 모바일에 맞는 layout과 CSS를 사용한 적이 있나요?

  *

* SVG를 스타일링 하기 위한 편한 방법이 있나요?
* 인쇄를 하기 위해 웹페이지를 어떻게 최적화 하나요?

  * 미디어 쿼리 `@media print`를 사용한다.

* 효율적인 CSS를 작성하기 위한 "비법(gotchas)"은 어떤 게 있나요?

  * CSS preprocessor(sass, scss)등을 사용해 모듈화 해서 중복, 과도한 중첩(상속)을 피하고 재사용을 강화한다.
  * jQuery에만 있는 선택자들은 최대한 피한다.
  * ID 선택자, class 선택자를 구분해서 사용한다.

* CSS 전처리(CSS preprocessors)를 사용해보셨나요? 그렇다면, 사용 경험에 기반해 좋았던 점과 나빴던 점을 설명해주세요.

  * sass/scss를 사용해봤다. 모듈화/변수 설정을 통해 자주 사용하는 값을 재사용 할 수 있고 유지보수가 편리하다는 점이 좋았다. mixin 등을 통해 값을 반응형을 만들기도 편리하다.
  * 구조적으로 만들기 위해서 설계에 대해 잘 알아야 한다.

* 페이지에서 표준 폰트가 아닌 폰트 디자인을 사용할 때 어떤 방식으로 처리하시나요?(웹폰트를 제외하고)

  *

* CSS Selector가 어떠한 원리로 동작하는지 설명해주세요.

  1. 브라우저가 HTML/CSS를 DOM으로 변환한다.
  2. DOM에서 Document의 내용과 Style을 결합한다.
  3. 브라우저가 DOM의 내용을 보여준다.

* pseudo-elements에 대해서 설명주세요.

  * 가상 요소는 가상 클래스와 함께 가상 선택자의 한 종류다. 상태 기술 대신 문서의 특정 부분을 스타일링 할 때 쓰인다.
  > ::after, ::befor, ::first-letter, ::first-line, ::selection, ::backdrop 등

* box model에 대해 설명하고 브라우저에서 어떻게 동작하는지 설명해주세요.

  * CSS Box Model은 패딩과 마진을 포함해 배치되는 CSS 모듈이다.
  > 박스 내 콘텐츠 흐름 제어 속성(box-sizing/overflow)
  > 박스 크기 제어 속성(height/width + min/max)
  > 박스 마진/패딩 제어 속성(margin/padding + top/bottom/left/right)
  > 기타 box-shadow, visibility 속성

* * { box-sizing: border-box; }은 무엇이고 사용했을때 이점은 무엇인가요?

  * `box-sizing` 속성은 요소의 너비와 높이를 계산할 때 사용되는 기본적인 CSS box model을 대체할 때 사용된다. 기본 값은 content-box로, 박스 내부에 있는 내용에 맞게 박스의 크기(너비/높이)를 지정한다는 뜻이다. 즉 박스 외부의 padding, margin, border를 포함하지 않는다.
  * border-box로 값을 변경할 경우 지정한 크기 속성이 border를 포함한 것으로 바뀐다. IE에서 문서가 쿽스 모드일 때 사용된다. padding과 border가 박스 안에 존재한다.

  * border-box 속성을 사용하면 반응형웹을 구현하는 데에 용이하다. border, padding에 의해 계속 바뀌면 반응형 웹을 구현하기 위해 설정해야 하는 값들의 변수가 너무나 많아지기 때문이다. 콘텐츠 양이 달라지더라도 가로 세로 너비 변형이 없게 하려면 box-sizing을 이용하면 전체 박스의 너비를 고정시킬 수 있다. - [참조](http://ccuram.tistory.com/27)

* inline과 inline-block의 차이점은 무엇인가요?

   * 원래 inline 요소는 width/height 값을 가질 수 없지만 inline-block은 가질 수 있다. IE8+

* relative, fixed, absolute, 그리고 정적 포지션 엘리멘트의 차이점은 무엇인가요?

  *

* cascading에 대해서 설명해주세요. 또 cascading system의 장점은 무엇인가요?

  * CSS의 첫 머리글자를 뜻하는 Cascading은 원래 '폭포수처럼 떨어지다'라는 의미를 가진다.
  * 이는 CSS가 '우선순위'를 가지고 있기 때문에 붙여진 이름이다.
    * 1. 원천 소스 중 스타일 시트가 우선함
      * 스타일 시트 우선순위: 사용자 !important > 작성자 !important > 작성자 스타일 > 사용자 스타일 > User Agent(브라우저 자체 선언)
    * 2. 선택자 우선순위
    * 3. 마지막에 지정된 스타일 우선 적용
  * 참고: `@media print { ... }`의 경우와 같이 `@`로 시작하는 문장은 Rule Set이 아닌 At-Rule이기 때문에 위 문장에서의 중괄호 전 부분은 선택자가 아님.

* CSS framework를 사용해본적이 있으신가요? 실무에서 사용해보았다면 어떤 이점이 있었나요?

  * Bootstrap, Bulma, SemanticUI, materialize
  * Bulma(Flexbox 기반), Bootstrap를 이용해서 클래스로 빠르게 레이아웃, 스타일링을 잡을 수 있었다.
  * 그 외에 vue로 작업할 때 vue-material을 이용해서 빠른 목업을 진행했따.
  * 재사용 가능한 컴포넌트들을 만들 수 있으며, 레이아웃, 타이포, 폼 디자인, 버튼 등 웹 디자인 요소를 간단히 지정 가능하다.
  * customizing은 불편하다.

* 반응형 디자인은 adaptive 디자인과 어떤 차이점이 있나요?

  * ‘적응형 웹’은 **서버**에서 웹에 접근한 디바이스를 체크하여 그 **디바이스에 최적화된 마크업을 호출**하고, '반응형 웹'은 전적으로 **클라이언트**에서 변화를 처리한다. 적응형 웹의 특징으론 기존의 사이트를 재구축할 필요가 없고 다양한 디바이스에 최적의 성능을 가져올 수 있습니다. 반면 ‘반응형 웹’은 미디어 쿼리를 사용하여 화면의 크기를 확인하고 유연한 이미지와 그리드로 화면 크기의 변화에 따라 그에 맞은 크기가 됩니다. 모든 디바이스에 대한 정보를 가지고 있으며 사용 여부에 따라 다운로드되어 사용됩니다.
  * ‘적응형 웹’과 ‘반응형 웹’의 가장 주된 차이는 적응형 웹은 클라이언트 쪽이 아닌 서버측에서 사용자의 디바이스를 확인하고 그 디바이스를 기초로 하여 HTML 및 CSS코드의 다른 배치를 제공한다는 점이다. - [참고](http://studio-jt.co.kr/%EB%B0%98%EC%9D%91%ED%98%95-%EC%9B%B9-%EA%B7%B8%EB%A6%AC%EA%B3%A0-%EC%A0%81%EC%9D%91%ED%98%95-%EC%9B%B9/)

* 레티나 그래픽 환경에서 작업해 보신적이 있나요? 하셨다면 어떤 기술을 사용하셨나요?

+ margin-top, margin-bottom은 인라인 요소에 영향을 미치나요?
  * No.
+ padding-top, padding-bottom은 인라인 요소에 영향을 미치나요?
  * No.
  * 인라인 요소들의 경우 left/right 속성들만 영향을 미친다.
+ rem을 쓰면 텍스트가 유저가 브라우저 윈도우를 크기를 바꾸거나 드래그를 할 때 반응형으로 바뀌나요?
  * No.
  * rem/em/px - Which one would you prefer among px, em % or pt and why?
    > `px`은 세밀한 제어, 정렬 유지에 좋다. cascade가 아니다(?)
    > `em`은 상대적인 크기를 나타낸다. 반응형에 쓴다. 1em은 현재 글꼴 크기를 가리킨다. 만약 기본 글꼴 크기를 16px로 잡으면, 1em = 16px이다.
    > `%`는 본문의 글꼴 크기를 기준으로 font-size를 설정한다. 사용하기 편리하고 cascade 하다.

+ HTML문서에서, 가상요소 `:root`는 언제나 `<html>`을 가리키나요?
  * True

+ `<b>`요소와 `<strong>` 요소의 차이
  * 기능은 글자를 **굵게**한다는 점에서 같다.
  * 하지만 웹접근성을 높이기 위해서는 즉 웹표준을 이해하고 준수하고자 한다면 <b>요소보다는 <strong>요소가 좋다.
  * <strong> 요소에는 `강조`라는 의미가 존재하기 때문이다. 표현상으로 두 요소의 차이는 없지만, 스크린리더와 같이 요소 의미를 해석해서 내용을 읽어주는 경우 <strong>요소가 적용된 텍스트를 강조해서 읽어줄 수 있다.
  * 하지만 만약 강조해야 하는 단어가 많을 경우, <strong>태그는 용량이 과해진다는 문제가 생길 수 있다.

+ `<table>` 요소에서 접근성을 높이는 방법

기본 형태
```html
<table>
    <tr>
        <td>내용</td>
        <td>내용</td>
        <td>내용</td>
    </tr>
</table>
```

  * <caption></caption>: caption 요소는 테이블의 제목을 나타냅니다. 대부분의 브라우저들은 테이블과 같은 너비의 폭을 차지하면서 중앙에 정렬되게끔 캡션을 표시할 것입니다. 물론 CSS를 사용해서 방식을 바꿀 수 있습니다.
  * <th></th>: th 요소는 테이블의 각 열에 대해서 제목을 설명합니다. 이렇게 하면 내용의 기능에 대해 의미를 더하는 것 뿐만 아니라, 다양한 브라우저와 장치들에서 좀 더 정확하게 표현되게끔 할 수 있습니다.

  * 추가
  ```html
    <table summary="북서 태평양의 화산들의 최근 활동 요약">
      <caption>북서 태평양의 화산들의 최근 활동</caption>
      <thead>
          <tr>
              <th scope="col">화산 이름</th>
              <th scope="col">이름</th>
              <th scope="col">최근 분출</th>
              <th scope="col">분출 종류</th>
          </tr>
      </thead>
      <tfoot>
          <tr>
              <td colspan="4">Compiled in 2008 by Ms Jen</td>
          </tr>
      </tfoot>
      <tbody>
          <tr>
              <th scope="row">Mt. Lassen</th>
              <td>California</td>
              <td>1914-17</td>
              <td>Explosive Eruption</td>
          </tr>
          <tr>
              <th scope="row">Mt. Hood</th>
              <td>Oregon</td>
              <td>1790s</td>
              <td>Pyroclastic flows and Mudflows</td>
          </tr>
          <tr>
              <th scope="row">Mt. St. Helens</th>
              <td>Washington</td>
              <td>1980</td>
              <td>Explosive Eruption</td>
          </tr>
      </tbody>
  </table>
  ```

  * summary 속성: 이 속성은 테이블 내용의 요약을 정의하기 위해 사용되며, 스크린 리더 사용자를 위한 것입니다(화면에는 표시되지 않았습니다). 오래된 W3C 권고인 WCAG 1.0과 HTML 4.0 에서는, summary 요소를 위와 같이 사용할 수 있다고 이야기하고 있습니만, 최근의 명세에서는 summary 요소가 언급되어 있지 않습니다. 이 속성에 관해서는 완전히 결정되지 않은 것으로 보이므로, 우리의 웹 표준 커리큘럼에서는 이것을 사용하는 것이 낫겠다는 결론을 내렸습니다. 무엇보다도, 이 속성을 추가함으로서 잘못되는 것은 없으며, 접근성 측면에서 더 낫기 때문입니다.
  * scope 속성: th 요소들에 scope 속성이 포함된 것을 보았을 것입니다. 이 속성은 th 요소에 사용되어서, th의 내용이 어떤 열과 행에 적용되는 것인지 설명하는 역할을 합니다. 이 속성은 th 요소에서만 사용될 수 있습니다.

## Javascript에 관련된 질문들:

* event delegation에 대해 설명해주세요.
* this는 javascript에서 어떻게 작동하는지 설명해주세요.
* prototype 기반 상속은 어떻게 하는지 설명해주세요.
* AMD와 CommonJS는 무엇이고, 이것들에 대해 어떻게 생각하시나요?
* null과 unedefined 그리고 undeclared의 차이점은 무엇인가요?
* 두개를 구분하기 위해서는 어떻게 하면 될까요?
* 클로져(Closure)는 무엇이며, 어떻게/왜 사용하는지 설명해주세요.
* 클로져를 만들 때 선호하는 패턴은 무엇인가요? argyle (IIFEs에만 적용할 수 있다)
* 익명함수(anonymous functions)는 주로 어떤 상황에서 사용하나요?
* "Javascript 모듈 패턴(Javascript module pattern)"이 무엇인지 설명을 해주시고, 언제 사용하는지도 말씀해주시기 바랍니다.
* "네임스페이스(namespacing)"에 대해서 언급을 하면, 보너스 포인트가 있습니다.
* 당신의 모듈이 네임스페이스가 없는 상황이라면?
* 당신의 코드를 어떻게 구성하는지?(모듈 패턴, Class기반 상속?)
* 호스트 객체(Host Objects)와 네이티브 객체(Native Objects)의 차이점은 무엇인가요?
* 다음 코드의 차이점은 무엇인가요?
* function Person(){} var person = Person() var person = new Person()
* .call과 .apply의 차이점은 무엇인가요?
* Function.prototype.bind을 설명 하시오
* document.write()는 언제 사용하나요?
* 코드 최적화를 하는 시점은 언제인가요?
* Javascript에서 어떻게 상속을 하는지 설명할 수 있나요?
* "누구도 할 수 없어요" 같은 재밌는 대답 시에 보너스 포인트가 있습니다.
* 안되는 이유에 대해서 설명을 시도한다면, 더 많은 점수를 주세요.
* document.write()를 언제 사용하시나요?
* 정답 : 1999년 - 초보개발자를 걸러내기 위한 시절
* UA문자열을 이용하여 기능 검출(feature detection)과 기능 추론(feature inference)의 차이점을 설명 하시오.
* AJAX에 관해 가능한 자세히 설명하세요.
* AJAX를 사용했을때의 장점과 단점에 대해 설명해주세요.
* JSONP가 어떻게 동작 되는지 설명하세요.(그리고,실제 AJAX와 어떻게 다른지 설명하세요.)
* 기존에 Javascript 템플릿을 사용한 적이 있나요? 만약에 있다면, 어떠한 방식으로 사용했는지 말씀해주세요.
* "호이스팅(Hoisting)"에 대해서 설명 하시오.
* 이벤트 버블링(Event Bubbling)에 대해서 설명하세요.
* "속성(Attribute)"와 "요소(property)"의 차이가 무엇인가요?
* Javascript 객체를 확장하는 것이 좋지 않은 이유는 무엇인가요?
* docuemnt load event와 DOMContentLoaded event의 차이점은 무엇인가요?
* ==와 ===의 차이점은 무엇인가요?
* Javascript의 "동일출처정책(the same-origin policy)"에 대해서 설명하세요.
* Javascript의 상속패턴(inheritance patterns)에 대해서 설명하세요.
* 다음 코드를 동작하게 만드세요.
* [1,2,3,4,5].duplicator(); // [1,2,3,4,5,1,2,3,4,5]
* Javascript에서 메모이제이션(memoization, 중복 계산 방지)에 대한 전략을 설명해주세요.
* 삼항식(Ternary statement)을 사용하는 이유는 무엇이고, 그것을 표현하기 위한 연산자 단어는 무엇인가요?
* use strict;은 무엇이고, 사용했을때 장단점에 대해서 설명해주세요.
* 100번 반복되는 반복문이 있습니다. 3의 배수일때는 fizz, 5의 배수일때는 buzz, 3과 5의 공배수일때는 fizzbuzz가 출력되는 코드를 작성해보세요.
* 전역 scope를 사용했을 때 장단점에 대해 설명해주세요.
* 때때로 load event를 사용하는 이유에 대해 설명해주세요. 또 단점이 있다면 대안책에 대해서도 설명해주세요.
* SPA에서 SEO에 유리하도록 만들기 위한 방법에 대해 설명해주세요.
* Promise란 무엇인가요? 또 polyfills이란 무엇인가요?
* Promise를 사용방법과 사용했을 때 이점에 대해 설명해주세요.
* javascript의 작동방식의 장단점에 대해 설명해주세요.
* javascrpt를 디버깅할때 사용하는 툴이 있으면 설명해주세요.
* object properties와 array items를 순회할 때 사용하는 문법에 대해 설명해주세요.
* mutable object와 immutable object에 대해 설명해주세요.
* 동기방식과 비동기방식에 대해 설명해주세요.
* event loop란 무엇인가요?
* call stack과 task queue에 대해 설명해주세요.

## 일반적인 질문들:

* 어제/이번주에 무엇을 공부하셨나요?
* 코딩을 할때 당신을 흥분시키거나 흥미를 끄는 것들은 무엇은가요?
* 최근에 당신이 경험한 기술적인 문제는 무엇이고 그것을 어떻게 해결했나요?
* 웹 어플리케이션이나 사이트를 만들때 고려해야할 UI, Security, Performance, SEO, Maintainability에 대해서 설명해주세요.
* 선호하는 개발 환경에 대해 자유롭게 이야기해 주세요.

* 버전 관리 시스템은 어떤 것들을 사용해보셨습니까?
  * git

* 당신이 웹 페이지를 만들 때의 과정을 설명 해주실 수 있을까요?

* 당신에게 5가지 다른 stylesheets들이 있습니다. 어떤 방법으로 사이트에 제공하는게 가장 효과적일까요?


* 점진적 향상법(progressive enhancement)과 우아한 성능저하법(graceful degradation)의 차이를 설명하실 수 있습니까?

  * 점진적 향상법 - 테스트를 통해 최신 기능을 빠르게 받아들이고 향상시키는 것
  * 우아한 성능저하 - 하위 호환을// 유지하고 기능의 수준을 모든 기기/사용자에게 맞추기 위해 별도 버전을 두는 것
  * "누구도 성공하지 못합니다" 라고 말하면 보너스 포인트를 주세요.
  * 각 특색을 설명을 한다면, 더 높은 보너스 포인트를 주세요.

* 웹사이트에서 assets/resources를 최적화 하는 방법에 대해 설명해주세요.
* 여러 도메인을 이용하여 서버 사이트 데이터를 제공하는 것이 더 나은 이유는 무엇인가요?

  * 병렬로 데이터를 불러오는 것과 같다. 타 도메인에서 데이터를 받는 시간이 DNS가 도메인을 해석하는 것보다 시간이 덜 걸린다. 따라서 적절한 양의 도메인에서 분산적으로 데이터를 호출하는 것이 보다 효과적이다.

* 브라우저가 한 번에 1개의 도메인에서 다운로드 받는 리소스는 몇 개 인가요?
* 파일의 연결법을 찾아내세요.
* Build system을 이용한 결합없이, @import를 사용하면 점수를 깎으세요.
* 당신이 프로젝트에 합류했습니다. 근데 그들은 Tab을 이용하고, 당신은 Space를 사용했습니다. 어떻게 하실건가요?
  * `:retab!`
  * vim에서 `:retab`을 이용해 단일화 한다.
* 간단한 Slideshow 페이지를 만들어보세요.
* Javascript를 사용하지 않고 만들었다면, 보너스 점수가 있습니다.
* 만약 당신이 올해 기술적 책임자가 되었다면 무엇을 먼저 하시겠습니까?
* 표준의 중요성에 대해 설명해주세요.
* Flash of Unstyled Content에 대해 설명해주세요. 또 FOUC를 피하기 위해선 어떻게 해야 하나요?
* ARIA와 screenreader에 대해 설명해주세요 또 사능한 웹사이트를 어떻게 만드는지에 대해도 설명해주세요.
* CSS 애니메이션과 Javascript 애니메이션의 차이점에 대해 설명해주세요.
* CORS 표준에 대해 도메인과 연관지어서 설명해주세요.

## Javascript 코드 예제:

`>~~3.14`
* 문제: 위 상황의 결과 값은?
  * 답:

`"i'm a lasagna hog".split("").reverse().join("");`
* 문제: 위 상황의 결과 값은?
* 답:

`( window.foo || ( window.foo = "bar" ) );`
* 문제: window.foo의 값은 무엇인가요?
  * 답:

```javascript
// 처음에 window.foo는 false, undefined 혹은 0등의 값을 가지고 있다.

var foo = "Hello"; (function() { var bar = " World"; alert(foo + bar); })(); alert(foo + bar);
```
* 문제: 어떠한 두 가지의 알럿이 나올까요?
  * 답:

## jQuery에 연관된 질문들:

* "체이닝(Chaining)"에 대해서 설명 하세요.
* .end()는 무엇을 하는 것입니까?
* 이벤트 핸들러 선언 시, 언제 그리고 왜 namespace를 부여하는지를 설명해주세요.
* 이펙트 큐(queue)라는 것은 무엇인가요?
* .get(),[] 그리고 .eq()의 차이점이 무엇인가요?
* .bind(),.live()그리고 .delegate()의 차이점이 무엇인가요?
* $과 $.fn 차이점이 무엇인지 설명 해주시오. 혹은, $.fn가 무엇인지 설명해주세요.
* 다음 Selector를 최적화 해주세요.:
* $(".foo div#bar:eq(0)")

## 테스트 관련 질문들:

* test code를 작성하면서 개발하는 방식의 장점과 단점에 대해 설명해주세요.
* test code를 테스트하는 툴을 사용해보신 경험이 있나요?
* 유닛 테스트와 함수테스트의 차이점은 무엇인가요?
* code style linting tool을 사용했을때 장점은 무엇인가요?

## 성능 관련 질문들:

* 성능관련 이슈들을 발견하기 위해서 사용하는 방법은 무엇인가요?
* 웹사이트 scrolling 성능을 향상시키기 위한 몇가지 방법에 대해 설명해보세요.
* 브라우저의 layout, painting, compositing에 대해 설명해보세요.
* 네트워크 질문들:

* 전통적으로, 웹사이트의 assets을 여러 도메인으로 서빙했을 때 장점은 무엇인가요?
* URL로 접속했을 때 어떤 플로우로 화면에 웹사이트가 그려지는지 네트워크 관점에서 설명해주세요.
* Long-Polling과 Websocket, Server-Sent Event에 대해 설명해주세요.
* 다음 request header들에 대해 설명해주세요.
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
  * HTTP와 HTTPS에 대해 설명해주세요.
  * HTTP Method들에 대해 설명해주세요.

## 그 외 흥미로운 질문들:

* 당신이 작성한 코드 중 어떤 것을 가장 멋지고, 자랑스럽게 여기나요?
* HTML5 gang sign에 대해서 아시나요?
* 배를 타본 적이 있으세요?
* Firebug와 Webkit Inspector에서 좋아하는 부분을 말씀해주세요.
* 당신 스스로 하는 프로젝트가 있나요? 어떤 종류인가요?
* "유니콘화(cornify)"의 의미를 설명해주세요.
* 한장의 종이 위에, A B C D E를 차례대로 내려 쓰시오. 그다음, 코드로 작성하지 말고, 역순으로 재배치 해보세요.
* 종이를 위아래를 뒤집어낼 때 까지 기다리세요.
* 이것은 인터뷰의 끝에 긴장감을 풀어주고 웃음을 줄 수 있는 좋은 방법이 입니다.
* 해적입니까? 닌자입니까?
* 만약에 둘 다 이며, 좋은 이유를 댄다면 보너스 점수를 주세요.(좀비 몽키 해적 닌자인 경우엔 +2)
* 만약에 웹개발을 안했다면, 무엇을 했었을까요?
* Carmen Sandiego는 세상의 어디에 있을가요?(힌트 : 그들의 답은 항상 틀릴겁니다.)
* Internet Explorer의 당신이 좋아하는 기능은 무엇입니까?
* 다음 문장을 완성하세요 : Brendan Eich 와 Doug Crockford 는 Javascript의 __________ 이다.
* jQuery: 훌륭한 라이브러리인가요? 최고로 좋은 라이브러리인가요? 토론하세요.

+ 좋은 코드: 가독성을 위해 coding convention이 맞추어져 있는 것, naming 규칙을 적용해 메소드명/변수명/클래스명에 일관성이 있는 것, 확장성을 고려한 코드, 예외 처리가 잘 되어있는 코드. 보다 객체지향적인 코드(?), 재설계 시간을 단축시킬 수 있는 코드 등. TDD와 연관되어 있다.

+ SCM(Source Code Management): 소스코드 형상관리 시스템. 소스코드의 개정과 백업 절차를 자동화해서 오류 수정 괒어을 도와주고, 여러 사람이 협업하는 경우 각자 수정한 부분을 팀원 전체가 자동으로 동기화 할 수 있는 시스템.
  > SVN, git

+ 작성된 자바스크립트는 Babel로 컴파일되고 Webpack으로 번들화됩니다. css를 포함한 각종 리소스들 역시 Webpack을 통해 처리됩니다. 자동화는 npm과 Webpack으로 수행합니다.

* [참고 자료](http://asfirstalways.tistory.com/303)

+ React

관심사의 분리/선언적인 API
MV* 패턴에서 뷰 레이어만을 담당.

 * 인터페이스 내에서 계속해서 데이터가 요청-업데이트-뷰 변경이 일어난다. ("지속적으로 데이터가 변화")
  > 뷰 로직을 개별적으로 계속 다시 짜는 것이 어렵다.
  > 모델 데이터를 변경하는 모델 로직과 뷰 로직을 분류(관심사의 분리)를 보다 쉽게 처리하기 위해

 * 선언적인 API : JSX를 통해 어떤 형태로 뷰 데이터가 보여져야 하는 지 선언적으로 기술한다. 중간 과정이 아닌 결과물을 기술한다.

 * 컴포넌트를 통한 뷰 작성 : React는 단방향 데이터 흐름을 가지며, Reactive하다. Reactive 하다는 것은 상태(state)가 바뀌면 상태에 의존하는 뷰도 함께 업데이트 된다는 것이다. 단방향 데이터 흐름이라는 것은 데이터가 상위 컴포넌트(Parent)에서 하위 컴포넌트(Children)로 흐르게 되어 있다는 점이다. 이 데이터는 `prop`으로 지칭되며 JSX에서는 HTML의 속성처럼 작성된다.

  * Virtual DOM: HTML요소들을 가상 돔을 이용해 표현한다. VM은 가상의 HTML 요소들을 가지고 있다가, 렌더링하면 필요한 부분만 업데이트(DOM 조작)하는 방식으로 작동한다. `key`, `prop` 등과 연관이 된다.

  * React가 VM을 만든 이유: **업데이트 할 때마다 항상 다시 렌더링한다**는 정책을 가지고 있기 때문. 선언적으로 결과물을 작성하기 때문에 일부 요소만 선택해서 업데이트 하는 방식(jQuery 등)과 달리 일부가 아닌 해당 영역을 모두 새로 그리는 게 낫다.

  즉 Virtual DOM 트리를 비교해 필요한 부분만 업데이트한다. 이를 Reconciliation(비교 조정)이라고 한다. - [참고](https://calendar.perfplanet.com/2013/diff/)

  이러한 React renderer의 최적화, 가상화 덕분에 뷰 업데이트 로직은 거의 신경쓰지 않고 모델의 데이터 관리와 결과물의 모양만 기술하면 된다. 뿐만 아니라 **DOM 가상화 덕분에 브라우저의 구현에 코드가 의존**한다는 것을 넘어선다는 의미이므로(?) 디테일 차이들을 덜 신경써도 된다.

 * Flux : 클라이언트 사이드 웹 앱을 만들기 위한 어플리케이션 아키텍쳐. 단방향 데이터 흐름을 사용해 리엑트의 조합가능한 뷰 컴포넌트를 보완한다.
  * dispatcher, store, view(React Component)
    > MVC와는 다름.

 * JSX : 템플릿 언어 아님. JSX는 ECMAScript로 치환되는 간단한 치환/확장 언어다. React 컴포넌트와 React.DOM 가상 엘리먼트 생성자들은 Babel과 같은 트랜스파일러를 통해 `React.createElement` 함수 호출식으로 치환된다.

 ```javascript
 <div foo={0} bar={'baz'} />
 // 치환 후
 React.createElement('div', {foo: 0, bar: 'baz'})
 ```
JSX는 자체적인 if-else, loop, conditional presenation block 등의 제어 구조를 가지고 있지 않고 ECMAScript 표현식들을 `{}`안에 써준다는 정도에 그치므로 제대로 된 템플릿 언어로 볼 수 없다.

* `setState(nextState, callback)` : 비동기 배치 업데이트 함수. 비동기 함수이므로 콜백이 존재한다.

* `Props`: parent로부터 받는 데이터이며 값이 고정된, 불변성 데이터다.

* [참고](https://www.slideshare.net/floydophone/react-preso-v2)