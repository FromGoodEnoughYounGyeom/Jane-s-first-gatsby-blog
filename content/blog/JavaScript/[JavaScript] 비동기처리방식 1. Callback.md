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
> <br/> > <br/>

따라서 이러한 자바스크립트의 특성에 따라 코드를 실행할 때 상위 코드의 결과값으로 실행되는 코드가 아님에도 순차적으로 진행되어 때에 따라 원치 않는 결과가 나올 수도 있다.
<br/>
<br/>

_이럴 때 콜백 함수를 사용하면 특정 로직이 끝났을 때만 원하는 동작을 실행시킬 수 있다._
<br/>
<br/>

그런데 이렇게 콜백 함수를 사용하면 이것이 콜백 체인이 되고 지나친 콜백 체인은 **콜백 지옥**을 **유발**할 수 있다.
