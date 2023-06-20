---
title: TIL12
date: "2023-05-18T23:40:00.000Z"
description: "5월 17일 학습일지"
---
Part2로 넘어가기 전에 Part1 강의내용을 복습하고 Part2 강의 내용을 일부 진행했다.
1. NextJS에서 이미지 넣는 방법    
    - 이미지는 public 폴더에 저장    
    - html <img> 태그로 넣기    
    - Nextjs에서 제공하는 <Image> 태그로 넣기 - 최적화, import로 불러오기 필요함    
    - Image 태그는 외부 이미지 불러올 경우 width, height 무조건 지정 + next.config.js에 이미지 경로 추가        
2. Client component와 Server component    
    - Server component: 페이지 로드할 때 빠르지만 html 내부에 JS 사용 불가능함    
    - Client component: html 내부에 JS 사용이 가능하지만 페이지 용량이 늘어나고 로딩속도가 약간 느려짐    
    - hydration: html 문서 불러온 뒤 리액트 문법 적용을 위해 PC가 html을 분석하는 과정    
3. deduplication 기능    
    - 같은 데이터 요청이 여러번 있을 경우 묶어서 1번만 실행    
4. 몽고DB 생성    
    - mongodb.com 가입    
    - freetier로 생성, 관리자를 생성할 때 권한을 atlas admin으로 변경해주기