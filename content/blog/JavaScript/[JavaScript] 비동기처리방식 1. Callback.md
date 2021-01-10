---
title: '[JavaScript] 비동기처리방식 1. Callback & Callback Hell'
date: 2021-01-03 20:08:51
category: 'JavaScript'
draft: false
---

![](./images/callback.png)
<br/>
<br/>

# 들어가기

콜백 함수란 무엇인가에 대해서 설명하려면 먼저 **[동기(Synchronous)](https://goodenoughyoungyeom.netlify.app/Web%20Development/[Web%20Development]%EB%8F%99%EA%B8%B0%EC%99%80%EB%B9%84%EB%8F%99%EA%B8%B0%EC%B2%98%EB%A6%AC/#%EB%8F%99%EA%B8%B0synchronous)**/**[비동기(Asynchronous)](https://goodenoughyoungyeom.netlify.app/Web%20Development/[Web%20Development]%EB%8F%99%EA%B8%B0%EC%99%80%EB%B9%84%EB%8F%99%EA%B8%B0%EC%B2%98%EB%A6%AC/#%EB%B9%84%EB%8F%99%EA%B8%B0asynchronous)** 란 무엇인가에 대한 이해가 필요하다.
<br/>
<br/>

> 자바스크립트 자체는 **Single-threaded**한 언어이자 **synchronous**이다.

이에따라 자바스크립트에서 이뤄지는 비동기(Asynchronous) 작업은 `web API` 가 담당한다.
<br/>
<br/>

# Callback & Callback Hell

`callback`은 문자그대로 called at the back 이다.
<br/>
<br/>

1. 다른 함수의 인자로써 이용되는 함수이고
2. 어떤 이벤트에 의해 호출되어지는 함수라고도 할 수 있다.

<br/>

그런데 한 로직에 콜백 함수를 여러번 사용하면 이것이 콜백 체인이 되고 지나친 콜백 체인은 `Callback Hell`을 유발할 수 있다.
<br/>
예를들어 웹 서비스를 개발하다 보면 서버에서 데이터를 받아와 화면에 표시하기까지 인코딩, 사용자 인증 등을 처리해야 하는 경우가 있다. 만약 이 모든 과정을 비동기로 처리해야 한다고 하면 콜백 안에 콜백을 계속 무는 형식으로 코딩을 하게된다. 이러한 코드 구조는 가독성도 떨어지고 로직을 변경하기도 어렵다. 이와 같은 코드 구조를 콜백 지옥이라고 한다.
<br/>
<br/>

## Callback Hell 예제

백엔드 서버와 통신하여 로그인을 처리하는 로직을 예시로 가져왔다.(from [Dream Coding](https://www.youtube.com/watch?v=s1vpVCrT8f4&list=PLv2d7VI9OotTVOL4QmPfvJWPJvkmv6h-2&index=11)) 여기서 setTimeout 함수는 실제 데이터와 통신하는 비동기 처리 로직이다.
<br/>
<br/>

![](./images/callbackHellExample.PNG)
![](./images/callbackHellExample_2.PNG)
<br/>

위 코드의 기본적인 flow 는 아래와 같다.

1. id와 pw를 받아옴
2. 서버에 로그인
3. 사용자의 역할을 다시 요청해서 받아옴
4. 사용자의 이름과 역할이 들어있는 객체 출력

콜백 함수 안에서 다른 함수를 호출하고 또 다른 콜백을 전달하고 호출하는 대표적인 `콜백지옥`의 예시를 보여주고 있다.
<br/>

이러한 `콜백 지옥`은 코드를 한눈에 이해하기 어렵다. 따라서 에러 발생으로 인한 디버깅도 어렵다. 또한 유지 보수도 힘들게 만든다.
<br/>
<br/>
<br/>

## 해결법

일반적으로 `콜백 지옥`을 해결하기 위하여

1. 중첩해서 선언했던 콜백 익명 함수를 각각의 함수로 나눠서 구분 선언하거나
2. 자바스크립트에서 제공하는 object인 `Promise`를 사용하거나
3. `Promise`를 동기적으로 실행되는 것처럼 보여주는 API인 `async`,`await` 를 사용할 수 있다.

## 참고

- https://morioh.com/p/bb2f95f40ce3
- https://joshua1988.github.io/web-development/javascript/javascript-asynchronous-operation/
- https://www.youtube.com/channel/UC_4u-bXaba7yrRz_6x6kb_w
- https://satisfactoryplace.tistory.com/18
- https://velog.io/@hayyim0626/TIL-%EB%B9%84%EB%8F%99%EA%B8%B0-%EC%B2%98%EB%A6%AC%EC%99%80-Callback-%ED%95%A8%EC%88%98
