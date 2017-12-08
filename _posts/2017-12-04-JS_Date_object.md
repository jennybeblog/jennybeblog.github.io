---
layout: post
title: JavaScript Date Object
description: ""
tags:
  - JavaScript
  - Date
# image: '../../assets/images/spa_structure.png'
# comments: true
share: true
# link: 'http://singlepageappbook.com/goal.html'
---

## JavaScript Date Object

- `Date` 객체는 특정 시간을 표현하는 Date 인스턴스를 생성한다.
- **UTC 기준 1970년 1월 1일부터** 해당 시간까지의 millisecond 단위를 기준으로 한다.
- 자바스크립트 `Date` 객체를 생성자로 호출함으로써 인스턴스화 된다. 즉 `new` 연산자 없이 함수로만 사용할 경우 `Date` 객체 대신 문자열이 리턴된다.
- 자바스크립트의 다른 객체와 달리 `Date` 객체는 리터럴 형식으로 사용할 수 없다.

### 1. 파라미터

#### 1) 생성자에 인자가 하나 이상 들어가는 경우
- 만약 생성자에 인자가 하나 이상 들어가는 경우 만약 인자가 논리적인 범위를 넘어가는 경우, 비슷한 값으로 조정된다.
  - eg 1. `new Date(2017, 13, 1)`은 `new Date(2018, 1, 1)`과 같으며 결과는 `2018-02-01`이다. (월은 0부터 시작함)
  - eg 2. `new Date(2017, 11, 1, 0, 70)`은 `new Date(2017, 11, 1, 1, 10)`과 같으며 결과는 `2017-12-01T01:10:00`이다.

- `Date` 객체가 하나 이상의 인자와 함께 실행되는 경우, 그 특정 인자는 로컬 타임을 가리킨다.
- 만약 UTC 기준이 필요한 경우라면 해당 인자를 `new Date(Date.UTC(...))`에 동일하게 넣어야 한다.

- JavaScript Date 객체는 여러 플랫폼에서 동일한 동작을 제공한다. 동일한 시간을 나타내는 날짜를 작성하기 위해 시스템간에 시간 값을 전달할 수 있다. => ?

### 2. Syntax
```javascript
new Date();
new Date(value);
new Date(dateString);
new Date(year, month[, date[, hours[, minutes[, seconds[, milliseconds]]]]]);
```

#### 1) new Date(*value*);
- 인자로 들어가는 정수 값은 `1 January 1970:00:00:00 UTC`부터 지금까지의 밀리초(86,400,000)를 나타낸다.

```javascript
new Date(1000)
// Thu Jan 01 1970 09:00:01 GMT+0900 (KST)
```

#### 2) new Date(*dateString*);
- 인자로 들어가는 문자열 값은 날짜를 나타낸다. 
- 날짜 값은 `Date.parse()` 메서드로도 알아볼 수 있는 인자값이어야 한다.

* `Date` 생성자와 함께 date 문자열을 파싱하는 것은 브라우저 간의 불일치로 인해 권장되지 않는다.
* ISO 8601 형식 지원은 날짜 전용 문자열(예 : "1970-01-01")이 로컬이 아닌 UTC로 처리된다는 차이가 있다.("Support for ISO 8601 formats differs in that date-only strings (e.g. "1970-01-01") are treated as UTC, not local.")

```javascript
Date.parse("Jan 17 2017")
// 1484578800000
Date.parse("2017, 1, 17")
// 1484578800000
Date.parse("2017-01-17")
// 1484611200000
```
#### 3) new Date(*year, month[, date[, hours[, minutes[, seconds[, milliseconds]]]]]*);
###### year
- 0부터 99까지의 정수는 1900년에서 1999년까지로 배치된다.

###### month
- 0부터 11까지의 정수가 1월부터 12월까지 배치된다.

###### date(*optional*)
- 해당 월의 일자를 나타내는 정수

###### hours(*optional*)
- 해당 날짜의 시간을 나타내는 정수

###### minutes(*optional*)
- 해당 시간의 분을 나타내는 정수

###### second(*optional*)
- 해당 시간의 초를 나타내는 정수

###### milliseconds(*optional*)
- 해당 시간의 밀리초를 나타내는 정수(초/1000)

- 만약 인자가 아무 것도 들어오지 않으면 현재 시스템의 날짜와 시간으로 세팅된다.
- 만약 두개 이상의 인자가 들어오면, 비어있는 자리의 인자는 1 혹은 0으로 세팅된다.
- 자바스크립트 Date 객체는 로컬 타임 메서드 뿐 아니라 여러가지 UTC 메서드도 지원한다. 
- 그리니치 표준시 GMT(Greenwich Mean Time)로도 알려져 있는 UTC는 세계 표준 시각에 기반해 세팅되어 있는 시간이다.
- 로컬 타임은 자바스크립트가 실행되는 컴퓨터에 알려진 시간이다.
- Date 함수 호출 시(new 연산자 없이) 현재 날짜와 시간을 나타내는 문자열이 반환된다.
  ```javascript
  Date("2017, 1, 1")
  // "Fri Dec 08 2017 14:02:14 GMT+0900 (KST)"
  ```

### 3. Properties
#### 1) Date.prototype
- Date 객체에 속성을 추가할 수 있는 메서드
#### 2) Date.properties
- Date 객체가 받는 인자의 개수로 항상 7이다.

### 4. Methods
#### 1) Date.now()
- UTC 시간 기준점인 1 January 1970 00:00:00 UTC로부터 현재까지 지난 시간에 맞는 값을 밀리초 단위로 리턴한다.
#### 2) Date.parse()
- 날짜의 문자열 값을 파싱해서 UTC 시간 기준점으로부터 해당 시간까지의 값을 밀리초 단위로 리턴한다.
- *** 브라우저마다 리턴 값이 달라 권장하지 않는 사항**
#### 3) Date.UTC()
- 인자를 2개부터 7개 까지 가장 긴 형태로 동일하게 받으며, UTC 시간 기준점으로부터 해당 시간까지의 값을 밀리초 단위로 반환한다.

### 5. Reference
- [JavaScript - Date](http://devdocs.io/javascript/global_objects/date)
- [자바스크립트 날짜와 표시 형식](http://northpard.tistory.com/214)
