---
title: TIL22
date: "2023-07-05T01:39:00.000Z"
description: "7월 4일 학습일지"
---
1. 렌더링 전환
    ```JavaScript
    export const dynamic = 'force-dynamic'
    // 다이나믹 렌더링 페이지
    ```
    - 반대의 경우 'force-static', 'auto'는 자동으로 판단    
2. fetch 함수로 캐싱    
    - fetch('url', { cache: 'force-cache' })    
    - fetch('/URL', { next: { revalidate: 60 } }) : 캐싱 결과를 60초간 보관    
    - fetch('/URL', { cache: 'no-store' }) : 캐싱 기능 사용 안함    
    - next.js에서만 사용 가능한 문법임    
    - 서버 컴포넌트에서만 사용 가능    
3. revalidate    
    - 페이지 단위로 캐싱 가능, 초단위로 설정    
    ```JavaScript
    export const revalidate = 60;
    //60초동안 캐싱된 페이지를 보관
    ```