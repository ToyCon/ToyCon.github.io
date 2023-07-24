---
title: TIL29
date: "2023-07-22T21:22:00.000Z"
description: "7월 22일 학습일지"
---
prefers-color-scheme을 검색하면서 미디어 쿼리를 처음으로 알게됐다. 부트캠프 당시에 프론트 쪽 내용에 너무 관심을 두지 않았던 것 같아서 부끄럽다. 앞으로 만들 프로젝트를 하면서 같이 공부해야겠다.    
1. prefers-color-scheme    
    - 라이트 모드 / 다크 모드를 선택    
    - CSS 파일에 라이트 모드 / 다크 모드에 적용할 스타일을 각각 작성(사용법은 [MDN 공식문서](https://developer.mozilla.org/ko/docs/Web/CSS/@media/prefers-color-scheme)에 잘 나와있음)    

2. nextjs에서 쿠키 다루기
    - 서버 컴포넌트에서 쉽게 다룰 수 있음    
```JavaScript
import { cookies } from 'next/headers'

export default function DarkBtn() {
    //코드 생략, 쿠키 불러오기
    let colorCheck = cookies().get(setColor);
    { colorCheck === 'light' ? : }
}
```