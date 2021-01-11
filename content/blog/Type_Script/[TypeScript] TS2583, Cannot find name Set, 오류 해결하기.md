---
title: '[TypeScript] TS2583, Cannot find name Set, 오류 해결하기'
date: 2021-01-11 12:08:51
category: 'Type_Script'
draft: false
---

# error TS2583

> error `TS2583` : Cannot find name 'Set'. Do ynd name 'Set'. Do you need to change your target library? Try changing the lib compiler option to 'es2015' or later.

타입스크립트를 다운받고 `tsc`(typescript compiler) 명령어를 사용해서 `.ts` 파일을 `.js` 파일로 변환하려고 시도하던 중에 에러를 받았다.
<br/>
<br/>

![](./images/typescript_error_TS2583.png)

자꾸만 `TS2583` 오류가 났다.
<br/>

설정에 나도 몰랐던 오류가 있나 싶어서 [JaeYeopHan](https://jbee.io/) 님의 [typescript_playground](https://github.com/JaeYeopHan/typescript_playground)를 참고하여 npm과 설정파일을 작성했다.
<br/>
<br/>

![](./images/typescript_error_answer_1-1.png)

transpiler를 태울 webpack이 필요한데 그 config파일과 TypeScript 설정파일인 `tsconfig.json`파일을 생성해준다.
<br/>
<br/>

![](./images/typescript_error_answer_2.png)
![](./images/typescript_error_answer_4.png)
<br/>

위와같이 필요한 npm 모듈들을 설치한다.
<br/>
<br/>

![](./images/typescript_error_TS2583_solved.png)
<br/>

성공적으로 해결했다. &#128517;
<br/>
<br/>
<br/>

## 참고

- https://github.com/JaeYeopHan/typescript_playground
