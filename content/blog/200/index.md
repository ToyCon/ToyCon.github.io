---
title: TIL26
date: "2023-07-14T23:42:00.000Z"
description: "7월 14일 학습일지"
---
몽고db id에서 document가 작성된 시간을 확인하는 것은 성공했다. 그런데 그게 복잡하지 않은 과정이더라도 그 수가 늘어나면 매번 서버도 시간을 계산해야 하고 클라이언트도 시간을 계산하는 과정이 실행되서 비효율적이라는 것을 깨달았다. 그냥 몽고db에 작성 시간을 별도로 입력하면 간편하게 처리가 가능하기 때문에 작성 시간을 추가로 저장하기로 했다.    
1. 시간 꺼내는 코드    
```JavaScript
export default function getKST(postId){
  return new Date(parseInt(postId.substring(0, 8), 16) * 1000);
}
```
2. 몽고db document에서 시간 다루기    
    - 클라이언트 or 서버에서 new Date로 시간을 생성해서 몽고디비로 보내도 자동으로 ISODate 형식으로 저장    
    - 줄루 타임이므로 +9시간 해주는 과정은 거쳐야 함    
3. loading.js, error.js, not-found.js    
   - 로딩 인터페이스 넣을 때 loading.js, 같은 폴더 안에 넣으면 자동으로 적용    
   - 클라이언트 컴포넌트로 만들어야 함    
   - app 폴더 바로 아래에 넣어주면 모든 페이지에 적용 가능, error.js, not-found.js도 동일