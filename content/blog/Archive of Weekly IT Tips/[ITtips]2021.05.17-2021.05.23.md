---
title: '[ItTips]2021.05.17 - 2021.05.23'
date: 2021-05-23 22:08:29
category: Archive of Weekly IT Tips
draft: false
---

# 목차

```toc
exclude: Table of Contents
from-heading: 2
to-heading: 6
```

## 📙 블로그

### [개발자를 위한 금융 지식과 핀테크](https://wonit.tistory.com/318?category=813540)

- 개발자를 위한 기초 금융 지식과 핀테크에 대해서 정리해 놓은 블로그이다.
- 기존의 금융업계에 it가 어떤식으로 영향을 미치고 있는지 그속에서 개발자의 역할은 무엇인지에 대해서 넓고 얕게 알아볼 수 있다.

## 🎥 영상

## Switch 컴포넌트 안에서 route의 순서의 중요성

따라서 여기서는 `<Route>` 컴포넌트의 순서가 중요해진다. 그래서 먼저 비교 할 `<Route>` 를 위에 작성해야 한다.
만약에 `/about` 을 `/about/:category` 보다 위에 넣어준다면, `category` 을 입력해주어도 나타나지 않을 것이다.

## 404 NotFound page 생성하기

`<Route>` 컴포넌트를 순서대로 입력 후 제일 마지막으로 path prop이 없는 `<Route>` 컴포넌트를 추가해주면, 이 `<Route>` 는 해당되는 path가 없는 모든 경로에 매치가 가능해진다. 다시말해 사용자가 주소를 잘못입력해서 http://localhost:3000/aboutttttttt 와 같이 없는 path를 요구 할 경우 미리 설정해 둔 `path가 없는 <Route>` 가 실행되고 이 때 `path가 없는 <Route>`에 미리 등록해둔 페이지에 404 NotFound 를 넣어둔다면 잘못된 주소를 입력시 404 NotFound 가 출력되도록 할 수 있다.

## Reference

-

* [Engineering blog by Dale Seo](https://www.daleseo.com/react-router-basic/)
