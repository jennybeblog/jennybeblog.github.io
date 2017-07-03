---
layout: post
title: React+Redux | 2. React basic - Components, props, state
description: "React 만들면서 내용정리하기"
# image: ../../assets/images/react_love.png
tags:
  - react basic
  - component
  - modulize
  - props
  - state
comments: true
# link: 'http://tryhelloworld.co.kr/challenge_codes/126'
---

# 01. Component 모듈화 기본

## 1) App.js 파일 업데이트 하기

#### 디렉토리 구조
```bash
react-practice
├── package.json
├── public            # 서버 public path
│   └── index.html    # 메인 페이지
├── src               # React.js 프로젝트 루트
│   ├── components    # 컴포넌트 폴더
│   │   └── Header.js  # Header 컴포넌트
│   │   └── Content.js # Content 컴포넌트
│   │   └── App.js    # App 컴포넌트
│   └── index.js
└── webpack.config.js
```

한 파일엔 여러 개의 컴포넌트가 함께 조합되어 나타난다.

```javascript
import React from 'react'

class App extends React.Component {
  render() {
    return (
      <div>
        <Header />
        <Content />
      </div>
    );
  }
}

class Header extends React.Component {
  render() {
    return (
      <header>
        <h1>HEADER</h1>
      </header>
    )
  }
}

class Content extends React.Component {
  render() {
    return (
      <div>
        <h2> CONTENT </h2>
        <p> Content 내용을 보여주는 p 태그 자리</p>
      </div>
    )
  }
}
export default App
```

* `React.Component`를 상속해서 새로운 Component들을 만든다.
* 이때 App만 export 해줘도 된다.

## 2) Component 모듈화 하기.

**Components** 폴더에 `Header.js`, `Main.js`를 각각 만든 뒤 위에서 작성한 내용을 가져다 붙인다.

> 이때 둘 다 React를 import 해주고 각 컴포넌트를 export 해준다.

###### Header.js

```javascript
import React from 'react'

class Header extends React.Component {
  render() {
    return (
      <header>
        <h1>HEADER</h1>
      </header>
    )
  }
}

export default Header
```

* [참고: ES6의 export](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/export)

App.js에는 각각의 component들을 import 해준다.

## 3) 실습

```javascript
import React from 'react'
import Header from './Header'
import Main from './Main'

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
        <Header />
        <Main />
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

# 02. props

* **변동되지 않는** 데이터를 다루기 위해 사용한다.
* **단방향**으로 데이터를 전달한다. 부모 => 자식으로만 전달한다.

## 1) 변하지 않는(immutable) 데이터가 필요한 컴포넌트의 경우

`render()` 내부에 `{this.props.*propsName*}` 형식으로 집어 넣고, 컴포넌트 사용 시 엘리먼트 태그 안에 `*propsName="value"*`를 넣어 값을 설정한다.

###### Header.js

```javascript
import React from 'react'

class Header extends React.Component {
  render() {
    return (
      <h1>{ this.props.title } </h1>
    );
  }
}

export default Header
```

###### App.js : props 사용하기

```javascript
import React from 'react'
import Header from './Header'

class App extends React.Component {
  render() {
    return (
      <div>
        <Header title={this.props.headerTitle}/>
      </div>
    )
  }
}

export default App
```

###### index.js

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import App from './components/App'

const rootElement = document.getElementById('root')
ReactDOM.render(
  <App headerTitle = "Welcome!"
       contentTitle = "Stranger,"
       contentBody = "Welcome to example app"
  />, rootElement
)
```

## 2) props 기본 값 설정하기

컴포넌트 클래스 하단에 `*className*.defaultProps={ propName: value }` 삽입

###### App.js

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import Header from './Header'
import Content from './Content'

class App extends React.Component {
  render() {
    return (
      <div>
        <Header title = { this.props.headerTitle } />
        <Content title = { this.props.contentTitle }
                 body = { this.props.contentBody } />
      </div>
    );
  }
}

App.defaultProps = {
  headerTitle: 'Default Header',
  contentTitle: 'Default Content Title',
  contenteBody: 'Defualt Content Body'
}

export default App
```

위와 같이 defaultProps를 사용해 기본 값을 object 형식으로 할당한다.
이제 `index.js`가 다시 간단해진다.

###### index.js

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import App from './components/App'

const rootElement = document.getElementById('root')
ReactDOM.render(
  <App />, rootElement
)
```

## 3) 실습

#### App.js

```javascript
import React from 'react'
import Header from './Header'
import Main from './Main'

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
        <Header title={this.props.headerPara}/>
        <Main body={this.props.maincontentPara} />
        <br />
        <h1>Hello!</h1>
        <h2>I am {name.first}</h2>
        <h2>I am {name.second}</h2>
        <button onClick={this.sayHi}>click me</button>
      </div>
    );
  }
}

App.defaultProps= {
  headerPara: "This is headerPara from props",
  maincontentPara: "여기 나오는 내용은 App.defaultProps로 전달한 props 내용이에요."
}

export default App;
```

여기서 헷갈린 부분은 App.js에서 `title`, `body`로 불러온 props를 하위 컴포넌트에서 props 이름으로 정했던 것이다.

#### Header.js

```javascript
import React from 'react'

class Header extends React.Component {
  render() {
    return (
      <header>
        <h1>HEADER component</h1>
        <p> { this.props.title } </p>
      </header>
    )
  }
}

export default Header
```

즉, 여기서 `<p> { this.props.headerPara } </p>` 같은 식으로 할당한 것.
헷갈리지 않으려면 흐름을 잘 파악해야 할 것이다.

#### Main.js

```javascript
import React from 'react'

class Main extends React.Component {
  render() {
    return (
      <div>
        <h2> CONTENT </h2>
        <p> { this.props.body }</p>
      </div>
    )
  }
}

export default Main
```

# 03. state

* **유동적인** 데이터를 다룰 때 사용한다.

###### StateExample.js

```javascript
import React from 'react';

class StateExample extends React.Component {
  constructor(props) {
    super(props)            // super 함수: 부모의 constructor 메소드를 실행
    this.state = {
      header: "Header initial state",
      content: "Content initial state"
    };
  }

  updateHeader(text) {
    this.setState({
      header: "Header has changed"
    });
  }

  render() {
    return (
      <div>
        <h1> { this.state.header } </h1>
        <h2> { this.state.content } </h2>
        <button onClick={ this.updateHeader.bind(this)}>Update</button>
      </div>
    );
  }
}

export default StateExample
```

* 초기값 설정 : constructor(생성자) 메서드를 사용해서 `this.state = {}`로 설정
* state 렌더링 : render 메서드 내부의 엘리먼트에서 `{ this.state.*stateName* }`을 사용
* state 업데이트 : `this.setState()` 메소드 사용 (이를 render 시 직접 사용할 때는 this를 bind 해주어야 함수/객체에 접근할 수 있다.)

> state를 변경하는 메서드를 정의할 때 `this.setState()`를 사용한다는 것을 잊지 말기!

> state 기본값 설정은 constructor() { super(props) // this.state = { // 내용}}

## 3) 실습

###### RandomNum.js

다음 예제는 메서드를 props의 일부로 받아오는 방법을 보여준다.

```javascript
import React from 'react'
import ReactDOM from 'react-dom'

class RandomNum extends React.Component {
  // 1. 메서드 선언
  updateNumber() {
    let value = Math.round(Manth.random()*100)
    this.props.onUpdate(value);
  }
  // 2. constructor 메서드로 props를 받아오고
  // 3. updateNumber가 this context를 사용할 수 있도록 bind 한다.
  constructor(props) {
    super(props)
    this.updateNumber = this.updateNumber.bind(this)
  }
  render() {
    return (
      <div>
        <h1> RANDOM NUMBER: {this.props.number }</h1>
        <button onClick={this.updateNumber}>랜덤넘버 추출</button>
      </div>
    )
  }
}

export default RandomNum
```

###### App.js

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
// ...
import RandomNum from './RandomNum'

class App extends React.Component {
  constructor(props) {
    super(props)
      this.state = {
        value = ""
      }
      this.updateValue = this.updateValue.bind(this)
      // 아래 updateValue 메서드가 this.setState에 접근할 수 있도록 bind 해주는 것
  }
  // * 메서드로 state를 변경하는 부분? - 그럼 메서드를 통해 state 변경시에는 항상 this.setState가 method 내부에 들어가야 하나?
  updateValue(randomValue) {
    this.setState({
      value: randomValue
    })
  }

  // ...

  render() {
    // immutable data ....
    return (
      <div>
        <!-- .... -->
        <RandomNum number={this.state.value}
                   onUpdate={this.updateValue} />
      </div>
    )
  }
}

// ... immutable data things

export default App
```

#### 질문거리

1. onUpdate => updateValue (App.js) 가 어떻게 RandomNum.js의 updateNumber 메서드와 연결되는 걸까?

2. App.js에서도, 하위 컴포넌트들에서도 생성자 메서드를 써서 props를 받아오는 이유는? React.Component의 props를 받아오기 때문?

cf. 원래는 App => RandomNum 으로 데이터를 준다면 RandomNum 에서만 쓰면 되는 거라고 생각함

3. 실행 순서 헷갈림. 예를 들어 App.js에서 `<RandomNum number={this.state.value} onUpdate={this.updateValue}/>`가 먼저 실행되고 나서 Random.js 내부적으로 연결되어 실행되는 건지? (그러면 다시 1번 질문으로 올라감.)

---

* [참고: 컴포넌트의 State 와 Props 사용하기](https://velopert.com/921)

