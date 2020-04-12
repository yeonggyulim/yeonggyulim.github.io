---
title: React(리액트)란?
categories:
  - React
tags:
  - React
  - 리액트
date: 2020-03-31
updated: 2020-03-31 13:53:00
---
최근 들어 React로 프로젝트를 시작하는 곳도 많아지고 실제 업무에서 React를 도입하면서 React를 공부를 시작하였는데, 적으면서 공부하면 정리하기에도 좋고 복습하기에도 좋을 것 같아 블로그에 작성하기로 하였습니다. 이번 포스팅에서는 리액트를 소개하는 글을 적어보도록 하겠습니다.

## 1. React(리액트)

### [React란?](https://ko.wikipedia.org/wiki/%EB%A6%AC%EC%95%A1%ED%8A%B8_(%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8_%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC))
- 사용자 인터페이스(User Interface)를 만들기 위해 사용하는 자바스크립트 라이브러리

### React는 뷰 계층
리액트는 일반적으로 애플리케이션의 뷰 계층으로 여겨집니다.
![react](/images/react/react.png)
그림과 같이 데이터를 생성하는 애플리케이션 로직이 있고, 이 데이터를 UI 화면에 렌더링 하기 위해 리액트 컴포넌트에 보냅니다. 컴포넌트는 페이지의 HTML 코드를 얻는 작업을 합니다. 

### React 구성
리액트는 프로그래밍 할 때 사용하는 **React Component**와 렌더링할 때 사용하는 **React DOM** 으로 나뉩니다.
<!-- more -->
![react_component](/images/react/react_component.png)
리액트 컴포넌트에서 알아야할 내용은 다음과 같습니다.
- 데이터: 컴포넌트가 렌더링되는 곳 어디든 있는 데이터(컴포넌트가 어디있든 상관없음)
- 생명주기: 컴포넌트 생명주기 내의 변화에 반응하도록 구현한 메서드
- 이벤트: 사용자와 상호 작용하기 위해 작성한 코드
- JSX: UI 구조를 표현하기 위해 사용되는 리액트 컴포넌트의 문법

### React의 추상화
리액트는 여러 플랫폼에서 UI 구조를 구현하는데 사용할 수 있는 추상화 수준과 확장성을 가지고 있습니다.
![react_abstraction](/images/react/react_abstraction.png)

## 2. [JSX란?](https://en.wikipedia.org/wiki/React_(web_framework)#JSX)

### JSX
- Javscript XML의 줄임말로 Javscript 언어 문법의 확장판
- 외관이 HTML과 비슷하여 개발자들에게 친숙한 문법으로 컴포넌트 구조화 가능

```
class App extends React.Component {
  render() {
    return (
      <div>
        <p>Header</p>
        <p>Content</p>
        <p>Footer</p>
      </div>
    );
  }
}
```

### Nested Elements
같은 레벨의 Multiple Elements는 `<div>` element와 같은 하나의 container element로 래핑해줘야합니다.

### Javscript Expressions
Javascript **expressions** (but not **statements**)는 JSX안에 `{}`로 표현할 수 있습니다.

```
<h1>{10+1}</h1>
```

### Conditional Statements
**if-else statements** 대신 **conditional expressions(조건 연산자)**로 대신할 수 있습니다.

```
class App extends React.Component {
  render() {
    const i = 1;
    return (
      <div>
        <h1>{ i === 1 ? 'true' : 'false' }</h1>
      </div>
    );
  }
}
```

**함수**와 **JSX**는 **conditionals(조건문)**에서 사용할 수 있습니다.

```
class App extends React.Component {
  render() {
    const sections = [1, 2, 3];
    return (
      <div>
        {sections.length > 0 && sections.map(n => (
            /* 'key' is used by react to keep track of list items and their changes */
            /* Each 'key' must be unique */
            <div key={"section-" + n}>Section {n}</div>
        ))}
      </div>
    );
  }
}
```

## 3. 참조
- 리액트&리액트 네이티브 통합 교과서
- [위키피디아](https://en.wikipedia.org/wiki/React_(web_framework)#JSX)