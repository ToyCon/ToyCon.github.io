---
title: TIL16
date: "2023-06-20T22:54:00.000Z"
description: "6월 20일 학습일지"
---
1. Nextjs - useRouter    
    - client component에서 사용할 수 있음    
    - useRouter를 불러올 때 'next/navigation'에서 import(router 아님)    
    - useRouter에서 쓸수 있는 기능들은 공식문서에 설명 있음(https://nextjs.org/docs/pages/api-reference/functions/use-router)    
    - useRouter 기능중에 prefetch를 통해 링크 문서를 미리 받아놓을 수 있는데, Link 태그가 prefetch 기능을 포함하고 있음. Link 태그로 많은 링크를 불러올 경우 prefetch={false} 지정해서 prefetch 막을 수 있음    
2. Nextjs 서버 생성    
    - /app/api/ 폴더 또는 루트 경로에서 /pages/api/ 폴더 하위에 JS 파일 생성    
    - req.method 유형에 따라서 if문으로 응답을 보내주면 됨. express와 똑같다    
3. 과거 블로그 포스트 복구    
    - 2022.8.4 windows10 diskpart 포스트부터 복구, 양식 정리는 천천히 진행