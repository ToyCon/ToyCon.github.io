---
title: TIL18
date: "2023-06-22T22:36:00.000Z"
description: "6월 22일 학습일지"
---
몽고DB 기능때문에 시행착오를 좀 많이 겪었다. 어렵지 않은 해결책이었는데 시간을 많이 쓴것 같다.    
1. 게시판 프로젝트 글 수정 기능 완성    
    - form 태그로 전송할 경우 POST 요청 써야만 정상적으로 전송됨    
    - redirect 문법으로 응답을 줄 경우 단일 url만 사용 가능. detail/title 이런식으로 리다이렉트가 불가능함    
2. 몽고DB 데이터 수정 기능    
    - updateOne() 기능 쓸 경우 $inc 연산자를 쓸 수 있음    