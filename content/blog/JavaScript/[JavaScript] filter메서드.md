---
title: '[JavaScript] filter() 메서드'
date: 2021-04-08 14:08:29
category: 'JavaScript'
draft: false
---

# 목차

```toc
exclude: Table of Contents
from-heading: 2
to-heading: 6
```

## filter

`filter()` 는 배열 각 요소에 결과값이 true인 요소만을 모아서 새로운 배열을 반환하는 메서드이다. map이 내부 함수의 리턴값으로 다양한 타입(숫자,문자,배열 등)을 받는것과 다르게 filter는 오직 boolean 타입만 반환한다. 요소들을 특정조건에 걸러지게 만드는 것이 목적이다.
<br/>

## filter method의 3가지 매개변수

현재요소로 쓰일 value를 제외하고 나머지는 필수입력 사항이 아니다.

- value : 현재요소
- index : 배열 내 현재 값의 인덱스
- array : filter()을 호출한 배열
  <br/>

## 예시

### 기본형

```sh
const animals = ['rabbit','crocodile','squirrel','fox','elephant']
const animalsFilter = animals.filter(word => word.length > 6);

console.log(animalsFilter)
```

`문자의 길이가 6 초과인 단어만 추출`하도록 animals에 `filter 함수`를 추가하여 새로운 animalsFilter 함수를 만들었다. 해당 함수를 console.log 해보자.

```
['crocodile','squirrel','elephant']
```

문자의 길이가 6 초과인 단어만 추출되어 배열로 만들어 진 것을 볼 수 있다.
<br/>

### 빈 배열

```
var arr = [4, 377, 1024];
var arrFilter = arr.filter(function (n) {
    return n % 5 == 0;
});
console.log(arrFilter);
```

위와같이 만족하는 요소가 없는 filter 메서드를 실행한다면

```
[]
```

빈 배열이 반환된다. 보통 도메인을 해결하기 위해서 Array 메소드를 여러개 연결하여 사용하는데 이때 만약 빈 배열이 반환되지 않는다면 에러가 날 수도 있다.

<br/>

<br/>

## Reference

- [JS map, filter, reduce 함수 톺아보기](https://brunch.co.kr/@swimjiy/15)

- [code Scalper, Javascript - map,filter,reduce](https://www.youtube.com/watch?v=vqdzVZxoRtM)

- [비비로그, 자바스크립트의 유용한 배열 메소드 사용하기](https://bblog.tistory.com/300)
