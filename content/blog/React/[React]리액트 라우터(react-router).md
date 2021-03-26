---
title: '[React] 리액트 라우터(react-router)'
date: 2021-03-26 10:08:29
category: React
draft: false
---

## 목차

```toc
exclude: Table of Contents
from-heading: 2
to-heading: 6
```

## Routing 이란?

URL에 따라서 그에 상응하는 화면을 전송해주는 것을 Routing이라고 한다.

리액트에서 라우팅 기능을 구현하는 것은 쉽지 않지만 React Router는 리액트에서 비교적 쉽게 라우팅이 가능하도록 도와준다.

React Router를 설명하기에 앞서서 React Router 사용하지 않았을 경우 생기는 문제점에 대해서 알아보자.

## react-router-dom을 사용하지 않은 라우팅의 구현과 문제점 

![](./images/react-route.png)

위와같이 `<header>`내에 특정 메뉴 버튼을 클릭하면 그에 상응하는 컴포넌트로 `{comp}` 상태가 바뀌도록 해놓으면 버튼 클릭시 화면에서 `<main/>` 부분이 갱신되어서 특정 버튼에 해당하는 화면으로 전환되어 진다.  
<br/>
하지만 이런 방식으로 라우팅을 구현하게 되면 사용자 입장에서 다음과 같은 문제가 발생한다.

- 특정 페이지 **즐겨찾기 등록불가**, 화면이 전환되어도 브라우저 주소창의 url은 고정되어 있기 때문이다.
- **뒤로 가기 버튼**을 누르면 해당 앱 내에서 이전 페이지로 이동하는 것이 아니라 그 전에 서핑하던 **다른 웹사이트로 이동**해버린다.
- **새로고침 버튼**을 누르면 사용중이던 컴포넌트가 아닌 최초에 렌더링 되었던 **사이트 메인으로 이동**한다. 
- seo(검색 엔진 최적화) 측면에서도 일반 웹사이트들과 차이가 있어서 검색 엔진에 의해 원치않는 방식으로 색인이 될 수 있음.

## React Router 

React Router는 위의 문제점을 해결하기 위해 사용되고 있는 네비게이션 라이브러리이다. React Router를 사용하면 앱에서 발생하는 라우팅이 [location](https://developer.mozilla.org/ko/docs/Web/API/Location)과 [history](https://developer.mozilla.org/ko/docs/Web/API/History) 같은 wep API 와 연동된다.

### React Router 설치

React Router는 1. Web용 2. Native용이 존재한다. Web용을 설치해보자.
```sh
npm i react-router-dom
```
<br/>
<br/>

### React Router component 사용하기

react-router-dom 라이브러리에는 많은 컴포넌트가 존재한다. 그 중 가장 중요한 3가지 컴포넌트에 대해 알아보자.

- Link  : html의 `<a>` 태그와 유사한 기능, to prop을 통해서 이동할 경로를 지정해준다.
```sh
<Link to="/about">About</Link>
```
예를들어서 위의 코드는 브라우저에서 클릭이 가능한 about으로 렌더링되고, about을 클릭하면 주소창의 경로가 <도메인 네임>/about 으로 갱신된다. 

- Route : 현재 주소창의 경로와 매치될 경우 보여줄 컴포넌트를 지정하는데 사용된다. path prop을 통해서 매치시킬 경로를 지정하고 component prop을 통해서 매치되었을 때 보여줄 컴포넌트를 할당한다. 
```sh
<Route path="/about" component={About}>
```
현재 주소창의 경로가 /about 인경우 About 이라는 컴포넌트를 보여준다. 일반적으로 현재 주소창의 URL 경로에 따라 특정 컨텐츠를 보여주거나 숨기기 위해서 사용될 수 있다. 

- Router : `<Route>`와 `<Link>`컴포넌트가 함께 유기적으로 동작하도록 묶어주는데 사용한다. `<Route>`와 `<Link>` 컴포넌트는 DOM 트리 상에서 항상 `<Router>`를 공통 상위 컴포넌트로 가져야한다.

```sh
<Router>

	<Link/>
	<Link/>

	<Router />
	<Router />

</Router>
```

React Router를 사용하는 어플리케이션은 위와 같은 구조를 가지게 된다. 실제 프로젝트에서는 위 컴포넌트들이 여러 파일에 걸쳐서 흩어져 있을 수도 있다.
<br/>
<br/>

### React Router로 라우팅 구현 

글의 도입부분에서 예시로 들었던 리액트 라우팅을 사용하지 않은 라우팅의 구현을 React Router를 이용해서 재구현 해보자. 먼저 핵심 컴포넌트를 import 해줘야 한다.

```sh
import { Link, Route, BrowserRouter as Router } from 'react-router-dom'
```

React Router가 제공하는 `<Router>` 컴포넌트는 여러 종류가 있다. 여기서는 `<BrowserRouter>`를 사용하였다.

```sh
<header>
        <Link to="/">
          <button>Home</button>
        </Link>
        <Link to="/about">
          <button>about</button>         
        </Link>
        <Link to="/users">
         <button>User</button>
        </Link>
</header>
```

Header 부분을 `<Link>` 컴포넌트를 사용해서 리펙토링 한다. to prop에 해당 메뉴 클릭 시 이동해야 할 경로를 지정한다. 

```sh
<main>
        <Route exact path = "/" component={Home} />
        <Route path="/about" component={About} />
        <Route path="/users" component={NotFound} />
</main>
```
main 부분은 `<Route>` 컴포넌트를 사용한다. path prop에 매치 할 때 비교될 경로를 지정하고, component prop에 매치할 때 보여줄 컴포넌트를 할당한다.

여기서 `<Route>` 컴포넌트에만 exact prop이 사용된 이유는 React Router의 디폴트 매칭 규칙 때문이다. React Router는 path prop의 경로와 현재 브라우저 주소창의 url 경로(location.pathname)를 비교한다. 그리고 현재 url 경로 값이 `<Route>`의 path prop 값과 앞부분만 일치해도 같은것으로 간주한다. 따라서 path가 / 일 경우 / 뿐만 아니라 / 로 시작하는 모든 url 경로와 매치가 된다.

따라서 exact prop 이 없으면 home 컴포넌트가 url 경로와 상관없이 항상 보여지게 된다. 하지만 exact prop을 붙여주면 url 경로 값이 `<Route>`의 path 값과 전체가 일치해야 매치가 일어나고 처리를 해준다.

```sh
import React from 'react'
import { Link, Route, BrowserRouter as Router } from 'react-router-dom'
import Home from "./Home";
import About from "./About";
import NotFound from "./NotFound";

function App() {

  return (
    <Router>
      <header>
        <Link to="/">
          <button>Home</button>
        </Link>
        <Link to="/about">
          <button>about</button>         
        </Link>
        <Link to="/users">
         <button>User</button>
        </Link>
      </header>
      <hr/>
      <main>
        <Route exact path = "/" component={Home} />
        <Route path="/about" component={About} />
        <Route path="/users" component={NotFound} />
      </main>
    </Router>
  );
}
export default App;
```

마지막으로 `<Router>` 컴포넌트를 사용해 전체를 감싸준다. 위와같이 App.js 에서 `<Route>`와  `<Link>`전체를 감싸도 되고 
<br/>

index.js 로 가서 `<App />` 전체를 감싸도 된다.

```sh
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import { BrowserRouter } from "react-router-dom";

ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById('root')
);
```

## Reference

- [생활코딩](https://www.youtube.com/watch?v=WLdbsl9UwDc)

- [Engineering blog by Dale Seo](https://www.daleseo.com/react-router-basic/)