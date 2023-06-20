---
title: TIL13
date: "2023-05-18T23:45:00.000Z"
description: "5월 18일 학습일지"
---
1. 몽고DB 연동
    - nextjs project 폴더에서 mongodb 라이브러리 설치
    ```
    npm install mongodb
    ```
    - db와 연동을 담당하는 js 파일 하나 생성해서 아래 코드 실행    
    ```
    import { MongoClient } from 'mongodb'
    const url = 'DB접속URL~~'
    const options = { useNewUrlParser: true }
    let connectDB

    if (process.env.NODE_ENV === 'development') {
      if (!global._mongo) {
         global._mongo = new MongoClient(url, options).connect()
       }
       connectDB = global._mongo
    } else {
       connectDB = new MongoClient(url, options).connect()
    }
    export { connectDB }
    ```   
    - db에서 받아온 데이터를 실제로 활용할 페이지에서 connectDB 함수 호출해서 사용    
    ```
    import { connectDB } from "/util/database.js"
    
    function () {
       let client = await connectDB;
       const db = client.db('forum');
       let result = await db.collection('post').find().toArray();
       console.log(result);       
    }
    ```