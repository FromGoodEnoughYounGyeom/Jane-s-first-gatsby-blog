---
title: '[JavaScript] 비동기처리방식 1. Callback & Callback Hell'
date: 2021-01-03 20:08:51
category: 'JavaScript'
draft: false
---

![](./images/callback.png)

# 들어가기

콜백 함수란 무엇인가에 대해서 설명하려면 먼저 **[동기(Synchronous)](https://goodenoughyoungyeom.netlify.app/Web%20Development/[Web%20Development]%EB%8F%99%EA%B8%B0%EC%99%80%EB%B9%84%EB%8F%99%EA%B8%B0%EC%B2%98%EB%A6%AC/#%EB%8F%99%EA%B8%B0synchronous)**/**[비동기(Asynchronous)](https://goodenoughyoungyeom.netlify.app/Web%20Development/[Web%20Development]%EB%8F%99%EA%B8%B0%EC%99%80%EB%B9%84%EB%8F%99%EA%B8%B0%EC%B2%98%EB%A6%AC/#%EB%B9%84%EB%8F%99%EA%B8%B0asynchronous)** 란 무엇인가에 대한 이해가 필요하다.
<br/>
<br/>

> 자바스크립트는 Single-threaded한 언어이자 synchronous이다.
