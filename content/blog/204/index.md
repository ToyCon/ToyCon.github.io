---
title: TIL30
date: "2023-07-24T20:54:00.000Z"
description: "7월 22일 학습일지"
---
다크모드를 구현하는데 쿠키가 의도한 값이 아닐때 걸러줄 조건을 ||로 작성해서 한참 해맸다. 이미지 업로드, 미들웨어 기능은 이번에 만든 연습 프로젝트에서는 사용하지 않고 다음에 본격적으로 혼자서 만들 프로젝트에 적용하려고 한다.    
1. 쿠키 생성하거나 수정하기    
    - document.cookie = '이름=값;추가로 설정할 속성'    
2. 미들웨어 기능 사용    
- 프로젝트 루트 경로에 middleware.js 생성    
```JavaScript
import { NextResponse } from "next/server";
export function middleware(request) {//default 안붙음
//실행할 코드, 서버 기능보다 먼저 실행됨
}
```
- 서버에 오는 요청을 모니터링하거나 로그 기록, 불량 유저 접속 차단, 보안 코드, 쿠키 관리 등 할 수 있는 일이 많음