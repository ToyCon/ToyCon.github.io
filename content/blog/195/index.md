---
title: TIL21
date: "2023-07-03T20:20:00.000Z"
description: "7월 3일 학습일지"
---
build를 실행하고 난 뒤 npm run dev 명령어로도, build 후 npm run start도 실행해도 404 페이지로 연결되는 상황이 발생했다. 파일들을 하나씩 되돌리면서 실행해도 계속 같은 증상이 나와 어쩔 수 없이 프로젝트를 아예 새로 생성하고 build를 수시로 실행하면서 오류가 나지 않는지 체크하면서 진행했다.    
1. 에러 발생    
    - list 페이지에서 삭제기능 추가하기 위해서 클라이언트 컴포넌트를 하위 컴포넌트로 추가, db에서 불러오는 기능을 이관    
    - 에러 메시지    
    ```
    Warning: Only plain objects can be passed to Client Components from Server Components. Objects with toJSON methods are not supported. Convert it manually to a simple value before passing it to props.
    ```
    - list 페이지에서
    ```JavaScript
    result = result.map((a)=>{
      a._id = a._id.toString()
      return a
    })
    ```
    추가해서 실행
2. 빌드한 뒤 npm run start로 실행했을때 에러 발생    
  - 에러 메시지
  ```
  Unhandled Runtime Error ChunkLoadError: Loading chunk 272 failed.
  (missing: http://localhost:3000/_next/static/chunks/webpack-498aab44f1ab4ab1.js)
  ```
   - 검색결과 기존에 빌드했던 .next 폴더를 지우고 재실행하면 된다고 해서 그대로 해결[링크](http://itpsolver.com/react-next-js-chunkloaderror-loading-chunk-node_modules_next_dist_client_dev_noop_js-failed-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0/)