---
title: '[JavaScript] 비동기처리방식 3. async/await'
date: 2021-01-05 22:21:13
category: 'JavaScript'
draft: false
---

![](./images/asyncAwait.PNG)

# async/await 란?

[Promise](https://goodenoughyoungyeom.netlify.app/JavaScript/[JavaScript]%20%EB%B9%84%EB%8F%99%EA%B8%B0%EC%B2%98%EB%A6%AC%EB%B0%A9%EC%8B%9D%202.%20Promise/#%ED%94%84%EB%A1%9C%EB%AF%B8%EC%8A%A4%EB%9E%80)를 간편하게 동기적으로 실행되는것처럼 보이게 해주는 API이다. 콜백함수와 `Promise`의 단점을 보완하고 개발자가 읽기 좋은 코드를 작성하게 도와준다.

<br/>
<br/>

## 기본문법

```sh
async function 함수명(){
    await 비동기처리_메서드명();
}
```

1. function 앞에 `async`를 붙이고
2. 비동기 작업을 하는 함수에 `await`을 붙이면 된다.

# async

## 1. 기존 Promise 방식으로 처리할 경우

![](./images/async_promise.PNG)

`Promise`를 사용하면 반드시 resolve와 reject를 호출해야 한다.
<br/>
<br/>

## 2. 위 방식을 async 를 사용해서 처리할 경우

![](./images/async.PNG)

`async`를 사용하면 함수의 코드 블록이 자동으로 `Promise`로 변환 되어진다.
<br/>
<br/>

# await

## 1. 기존 Promise 방식으로 처리할 경우

![](./images/await_promise.PNG)

`콜백지옥`이 떠오른다.
<br/>
<br/>

## 2. await을 사용하여 수정했을 경우

![](./images/await.PNG)

자바스크립트는 `await` 를 만나면 프라미스가 처리될 때까지 기다린다. 결과는 그 이후 반환된다. 프라미스가 처리되기를 기다리는 동안에 다른 일(다른 스크립트 실행, 이벤트 처리 등)을 할 수 있기 때문에, CPU 리소스가 낭비되지 않는다.
<br/>

`await`은 `promise.then` 보다 좀 더 세련되게 프라미스의 `result` 값을 얻을 수 있도록 해주는 문법이다. `promise.then` 보다 가독성이 좋고 쓰기도 좋다.
<br/>
<br/>
<br/>

## 참고

- https://github.com/JaeYeopHan/typescript_playground
- https://www.youtube.com/channel/UC_4u-bXaba7yrRz_6x6kb_w
