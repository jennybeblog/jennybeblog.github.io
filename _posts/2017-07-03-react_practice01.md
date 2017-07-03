---
layout: post
title: React+Redux | 1. React basic 내용정리
description: "React 만들면서 내용정리하기"
# image: ../../assets/images/react_love.png
tags:
  - react basic
comments: true
# link: 'http://tryhelloworld.co.kr/challenge_codes/126'
---

# 01. Setting

#### 디렉토리 구조

react-practice
├── package.json
├── public            # 서버 public path
│   └── index.html    # 메인 페이지
├── src               # React.js 프로젝트 루트
│   ├── components    # 컴포넌트 폴더
│   │   └── App.js    # App 컴포넌트
│   └── index.js      # Webpack Entry point
└── webpack.config.js # Webpack 설정파일

[velopert 블로그 참조 | [React.JS] 강좌 2편 작업환경 설정하기](https://velopert.com/814)

(추후 내용 추가)

# 02. Basic JSX

###### App.js - 1. Basic of basics

```javascript
import React from 'react'   // ES6 문법.

class App extends React.Component {
  render() {
    return (
      <h1>Hello Jenn!</h1>
    );
  }
}

export default App
```

- line 1
: `var React = require(‘react’)`와 동일
- line 4
: `render() {}` render() 메소드에서 컴포넌트에 렌더링 될 데이터 정의를 `{}` 내부에 `return` 한다. 따옹표(`""`)없이 `()`안에 바로 HTML 태그를 작성한다.

###### App.js - 2. container element

```javascript
import React from 'react'

class App extends React.Component {
  render() {
    return (
      <h1>Hello Jenn!</h1>
      <h2>Welcome</h2>
    );
  }
}

export default App
```

위와 같이 작성하는 경우 여러 개의 엘리먼트가 있어 오류가 난다.
이를 막기 위해 하나의 `container element`를 만들어 줘야 한다.

```javascript
  render() {
    return (
      <div>
        <h1>Hello Jenn!</h1>
        <h2>Welcome</h2>
      </div>
    );
  }
```

다음과 같이 `div` 엘리먼트를 이용해 묶어준다.(wrapper 역할)

###### App.js - 3. JavaScript와 연결하기 `{}`

```javascript
import React from 'react'

class App extends React.Component {
  render() {
    let text = "React is cool."
    return (
      <div>
        <h1>Hello Jenn!</h1>
        <h2>Welcome and {text}</h2>
      </div>
    );
  }
}

export default App
```

JavaScript 표현식: `{}`을 이용해 변수를 렌더링 할 수 있다.

```javascript
import React from 'react'

class App extends React.Component {
  sayHello() {
    alert('환영해요!');
  }
  render() {
    let text = "React is cool."
    return (
      <div>
        <h1>Hello Jenn!</h1>
        <h2>Welcome and {text}</h2>
        <button onClick={this.sayHello}>클릭</button>
      </div>
    );
  }
}

export default App
```

* 메서드 실행하기
: render() 메서드 전에 메서드를 선언하고, 태그의 속성으로 메서드를 설정한다.
: 이때 위에서 변수를 렌더링 할 때 처럼 `{}`를 사용하고, this로 연결한다.
: 함수를 실행하는 `()`는 사용하지 않는다.

# 03. 실습

```javascript
import React from 'react'

class App extends React.Component {
  sayHi() {
    alert('환영해요!')
  }
  render() {
    let name = {
      "first": 'J',
      "second": 'Jen'
    }
    return (
      <div>
        <h1>Hello!</h1>
        <h2>I am {name.first}</h2>
        <h2>I am {name.second}</h2>
        <button onClick={this.sayHi}>click me</button>
      </div>
    );
  }
}

export default App;


```

* [참고: [React.JS]강좌 3편 JSX](https://velopert.com/867)