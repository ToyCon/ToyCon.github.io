---
title: TIL28
date: "2023-07-20T20:20:00.000Z"
description: "7월 20일 학습일지"
---
이미지 관련 기능을 구현하는데 계속 에러가 났다. 컴파일 단계에서 에러가 나서 정상적으로 실행이 불가능해서 일단 에러 코드만 기록해놓고 다른 기능을 구현하고 있다. db쪽을 업데이트했는데 mongosh로 update 함수로 값을 업데이트하는 과정도 정상적으로 작동하지 않아서 이것도 힘들다.    
1. 몽고db updateOne() 작동을 안함
    - 글을 완전히 db에서 삭제하지 않고 isDeleted라는 항목을 별도로 생성, 서버에서 메시지를 받으면 해당 값을 true로 바꾸는 코드를 작성했으나 해당 기능이 작동하지 않음    
```JavaScript
const db = (await connectDB).db("board");
let result = await db.collection('post').deleteOne({_id: new ObjectId(_id)});
// deletedCheck 항목으로 업데이트가 안되서 일단 스킵(7/20/15:40)
// let result = await db.collection('post').
//   updateOne({_id: new ObjectId(req.body._id)}, {$set: {deleteCheck: 1}});
// console.log(result);
```
2. <input> 태그에 이미지 삽입 기능 구현했을때 발생한 컴파일 에러 기록
```
wait  - compiling /write/page (client and server)...
error - ./node_modules/@mapbox/node-pre-gyp/lib/clean.js:8:0
Module not found: Can't resolve 'fs'

https://nextjs.org/docs/messages/module-not-found

Import trace for requested module:
./node_modules/@mapbox/node-pre-gyp/lib/ sync ^\.\/.*$
./node_modules/@mapbox/node-pre-gyp/lib/node-pre-gyp.js
./node_modules/bcrypt/bcrypt.js
./pages/api/auth/[...nextauth].js
./app/write/page.js
```