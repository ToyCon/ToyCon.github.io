---
title: TIL25
date: "2023-07-13T23:55:00.000Z"
description: "7월 13일 학습일지"
---
한 주동안 손을 못대서 강의를 돌려보고 댓글 기능 구현을 위해서 필요한 내용을 검색했다.    
1. Date
   - Date 함수로 날짜 불러오기, 대한민국 표준시로 맞추기(https://codechacha.com/ko/javascript-add-time-to-date/)    
2. 몽고DB id에서 시간 꺼내오기    
   - _id를 BSON 해석해서 시간으로 변환 가능(https://domdom.tistory.com/393)
   - 몽고DB는 그리니치 표준시(UTC+0) 일괄 적용    
   - 몽고DB 자체에서 일관성있게 UTC+0 쓰기 때문에, id에서 시간을 불러와서 9시간 추가해주면 한국 시간으로 표시할 수 있음