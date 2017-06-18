---
layout: post
title: Page | 웹페이지 빌드하기 0. 환경 세팅하기
description: "package.json과 npm ~이 더이상 두렵지 않도록"
tags:
  - webpage build
  - modern javascript
  - npm
  - package.json
  - webpack
image: '../../assets/images/sadbeemo.png'
comments: true
share: true
# link: 'http://tryhelloworld.co.kr/challenge_codes/120'
---

# webpage 혼자서 빌드하기

## 들어가기 전에

![beemo_plugin](https://media.giphy.com/media/ggVHdG7R3IRy0/giphy.gif){: .center-image}

몇 달 전만 해도 `package.json`이 뭔지, `npm`은 뭘 하는 건지 알 길이 없었다. 그냥 따라서 치기만 할 뿐...

일단 터미널 화면만 봐도 두려움이 앞섰는데, 저런 복잡해 보이는 파일들을 내가 직접 만들고 조작할 수 있을 지 모르겠다는 생각이 컸다.

시간이 지나고 조금씩 커맨드라인 명령어도, git도(눈물의 실패들이 많았고 아직도 충분히 사용하고 있는 지 모르겠지만), npm install도 조금은 덜 두려우지기 시작했다.

SPA 페이지를 만들 일이 생긴 이번을 기회로, 처음부터 스스로 해보기로 했다.

* 완벽한 가이드가 아니고, 만들어 가면서 저 역시 학습하기 위함이니 잘못된 내용이 있으면 알려주세요! <jennybe0117@gmail.com>

* 컴퓨터에 npm이 설치되어있지 않은 경우 [npm 1.0 사용하기](https://blog.outsider.ne.kr/638)를 먼저 참고하는 게 좋습니다. 그 밖에 간단한 사용법들도 잘 정리되어 있습니다.

## 1. 작업 공간 만들기

하나의 작업을 위해 두개의 작업 공간을 만든다. 로컬 폴더와 github repository를 판다.

로컬 폴더를 github repository와 연동해두면 로컬에서 작업한 내용을 git을 통해 관리할 수 있다. 나중에 다른 포스트에서 적겠지만, 간단히 말해 git은 형상 관리 도구(Configuration Management Tool), 분산 관리 시스템이다.

즉, 프로그램 소스코드의 변경 이력을 확인하기 쉽고, 협업에 용이하며, 백업이 편하다. [[참고]](https://tuwlab.com/ece/22202)

* 로컬 폴더 만들기

```bash
$ mkdir biyn_sample
```

* github repo 만들기
> github에 계정을 생성한 뒤 New repository -> 각종 설정

## 2. `npm init`

해당 폴더에 들어간 뒤 `npm init`을 하면 각종 설정 내용들이 생긴다.

```bash
$ cd biyn_sample
$ npm init
```

Enter키를 누르면서 설정 내용을 작성한다. git repository 주소를 적는 란도 있다. 위에서 만든 repository 주소를 복사해서 붙여넣는다.

이 내용들이 곧 `package.json`에 담긴다. `package.json`은 개발환경을 설정해 주는 데이터들이 담긴 기본 파일이라고 생각하면 된다.

```bash
{
  "name": "biyn_sample",
  "version": "1.0.0",
  "description": "biyn new webpage sample",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/jennybehan/biyn.git"
  },
  "author": "Jennybe Han",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/jennybehan/biyn/issues"
  },
  "homepage": "https://github.com/jennybehan/biyn#readme"
}
```

## 3. `npm install`

이번에는 node 환경을 만들기 위해 `npm install`을 시행한다. 다양한 모듈들이 설치된다. (dependecy와도 관련된다.)

```bash
$ npm install --save
```

나의 경우 로컬 영역에만 설정하기 위해(해당 폴더에서만 특정 환경을 구축하기 위해) `--save`를 추가했다.

`ls`를 쳐서 폴더 안에 어떤 파일들이 있는 지 파일 리스트를 확인해보면, `node_modules`와 `package.json`이 만들어져 있음을 확인할 수 있다.

## 4. github repository와 연결하기

github에서 새로운 레포지토리를 만들면 제공하는 기본 설정을 따라하면 된다.

```bash
$ echo '# BIYN webpage sample' > README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git remote add origin https://github.com/jennybehan/biyn.git
$ git push -u origin master
```
## 5. webpack과 babel 설치하기

```bash
$ npm install --save-dev webpack
```
* [webpack](https://www.npmjs.com/package/webpack)

webpack을 설치한 뒤 webpack config 파일을 만든다. 모듈 번들링에 관한 다양한 설정들이 들어간다.

```bash
$ touch webpack.config.js
```

sass, babel 로더들을 설치한다

```bash
$ npm install babel-core babel-loader babel-preset-es2015 --save-dev
$ npm install css-loader style-loader sass-loader node-sass --save-dev
```

(* webpack.config.js 파일 관련 내용은 추후 추가)

## 6. 필요한 패키지들을 설치한다(예시)

* 실시간 리로딩하는 webpack dev server 설치(개발과정에서만 쓰인다)

```bash
$ npm install webpack-dev-server --save-dev
```

* jQuery 설치

```bash
$ npm install jquery --save-dev
```

## 7. 실행 명령어 추가

`package.json`에 명령어를 추가한다.

```bash
"scripts": {
  "start": "node ./node_modules/webpack-dev-server/bin/webpack-dev-server.js",
  "test": "mocha --compilers js:babel-core/register --require ./test/test_helper.js --recursive ./test",
  "test:watch": "npm run test -- --watch"
},
```

예를 들어, command line에 `npm start`를 치면 로컬 서버를 구동시킬 수 있다. 브라우저에서 `localhost:8080`을 통해 실시간으로 프로그램을 확인하면서 개발할 수 있다.

## 8. `.gitignore` 생성하기

`.gitignore` 파일은 개발시에만 필요한 파일들을 git에 올리지 않도록 설정하는 파일이다. 즉 버전관리에서 제외해도 되는 파일들을 올리지 않는 것이다. 보통 `.`으로 시작하는 파일들은 숨김파일로, 디렉토리에서 보이지 않는 파일이다. 터미널에서 `ls -al`를 사용하면 숨김파일까지 전부 볼 수 있다.

## 참고

* npm은 'Node Packaged Modules'의 약자다. Node.js로 만들어진 모듈을 인터넷을 통해 받아 설치해주는 `패키지 매니저`. [[참고]](http://pyrasis.com/nodejs/nodejs-HOWTO#npm)
* `package.json`은 항상 최상위 디렉터리에 위치한다.
* [Node.js modules](http://theeye.pe.kr/archives/1667)
* [[모두 알지만 모두 모르는 package.json]](http://programmingsummaries.tistory.com/385)
* [[Webpack2와 모듈번들링을 위한 초보자 가이드]](https://github.com/FEDevelopers/tech.description/wiki/Webpack2%EC%99%80-%EB%AA%A8%EB%93%88%EB%B2%88%EB%93%A4%EB%A7%81%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%B4%88%EB%B3%B4%EC%9E%90-%EA%B0%80%EC%9D%B4%EB%93%9C)
* [[.gitignore]](https://xho95.github.io/git/github/xcode/swift/2016/07/15/Making-a-.gitignore-file.html)