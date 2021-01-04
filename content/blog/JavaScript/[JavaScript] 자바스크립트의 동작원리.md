---
title: '[JavaScript] 자바스크립트의 동작원리와 주요개념'
date: 2021-01-04 16:58:13
category: 'JavaScript'
draft: false
---

![](./images/javascript.png)

# 주요개념

![](./images/thread.png)

## 스레드(thread)

프로세스의 특정한 수행 경로이다. 프로세스가 할당받은 자원을 이용하는 실행의 단위이기도 하다.
<br/>

![](./images/process.png)

## 프로세스(process)

운영체제로부터 시스템 자원을 할당받는 작업의 단위이다. 동적인 개념으로는 실행된 프로그램을 의미한다. 기본적으로 프로세스당 최소 1개의 스레드를 가지고 있다. 프로세스는 각각 독립된 메모리 영역(Code, Data, Stack, Heap의 구조)을 할당받는다.
