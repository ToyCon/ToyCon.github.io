---
title: 'Error: Failed to collect page data for'
date: "2023-06-30T15:16:00.000Z"
description: "nextjs 'Build error occured'"
---
엊그제 npm run build 명령어로 배포 빌드 생성시 발생했던 오류와 해결 방법을 기록해둔다.
```
info  - Creating an optimized production build .ReferenceError: options is not defined
    at 3599 (/home/hyeondeok/refresh/.next/server/app/edit/[postId]/page.js:334:75)
    at __webpack_require__ (/home/hyeondeok/refresh/.next/server/webpack-runtime.js:25:42)
    at 4218 (/home/hyeondeok/refresh/.next/server/app/edit/[postId]/page.js:250:72)
    at Function.__webpack_require__ (/home/hyeondeok/refresh/.next/server/webpack-runtime.js:25:42)
    at process.processTicksAndRejections (node:internal/process/task_queues:95:5)
    at async collectGenerateParams (/home/hyeondeok/refresh/node_modules/next/dist/build/utils.js:741:17)

> Build error occurred
Error: Failed to collect page data for /edit/[postId]
    at /home/hyeondeok/refresh/node_modules/next/dist/build/utils.js:1055:15
    at process.processTicksAndRejections (node:internal/process/task_queues:95:5) {
  type: 'Error'
}
```
이런 오류 메시지가 뜨면서 빌드 중간에 멈추는 현상이 발생했다. 계속 검색을 하다가 답을 찾았다.
https://github.com/vercel/next.js/discussions/34249
이게 정답이었다. next.config.json 파일에 설정을 추가해주니 해결됐다.
```JavaScript
const nextConfig = {
  experimental: {
    appDir: true,
  },
  //>>아래 코드 추가했음
  pageExtensions: ['page.tsx', 'page.ts', 'page.jsx', 'page.js']
}
```
위의 깃허브 포럼에서 공식 문서 링크(https://nextjs.org/docs/pages/api-reference/next-config-js/pageExtensions#including-non-page-files-in-the-pages-directory
)를 연결해줬다. 테스트 관련 설정같은데 읽어보고 이 포스트에 내용을 추가하거나 새로 포스트를 작성해서 정리해둬야겠다.