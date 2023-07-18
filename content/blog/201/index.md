---
title: TIL27
date: "2023-07-18T19:41:00.000Z"
description: "7월 18일 학습일지"
---
슬슬 기능을 구현하거나 수정하는 데 시간이 오래 걸려서 하루에 한 일을 정리하기가 쉽지 않다. 작업하면서 의문이 들었던 내용을 따로 적어뒀다가 검색해 보면서 학습을 하려고 한다.    
1. useState 추적 변수    
    - 댓글을 작성했을 때 자동으로 불러오도록 별도의 state를 하나 생성하고 버튼 쪽에서 setState로 변경    
```JavaScript
//댓글 작성했는지 여부를 확인하는 state
let [checkNewComment, setCheckNewComment] = useState(false);
//useEffect, 내용은 생략
useEffect(()=>{},[checkNewComment])
//댓글 전송 버튼
  .then((res) => {
  if(res.acknowledged === true) setCheckNewComment(!checkNewComment);
  }).catch((err) => console.log(err))
```
2. createObjectURL    
    - Presigned URL 방식을 사용하면 글을 최종적으로 등록하지 않아도 이미지가 S3에 업로드되서 비효율적    
    - 별도의 변수 선언한뒤 URL.createObjectURL() 담아서 사용하고 사용이 끝나면 revokeObjectURL() 호출해서 지우기     