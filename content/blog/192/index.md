---
title: TIL19
date: "2023-06-27T20:30:00.000Z"
description: "6월 27일 학습일지"
---
삭제 기능을 완성하려고 시간을 오래 써도 계속 안되서 힘들었는데 오늘 쉽게 완성이 됐다. 이런 경우가 종종 있다. 부트캠프에서 공부하던 것처럼 기술적 부채로 남겨놓고 다른 기능 먼저 진행해야겠다.    
1. 게시판 프로젝트 글 삭제 기능 완성    
    - fetch('url', {method: CRUD 기능에 맞춰서 적절한 메서드 ''안에, body: 메시지에 포함되어야 하는 내용})    
    - body에 담을 내용이 많으면 객체에 담아서 JSON으로 보내기. 보낼때는 JSON.stringify(전송할 object), 받을때는 JSON.parse(전송받은 object)    
2. 몽고DB 데이터 삭제 기능    
    - deleteOne() 함수. 고유한 값을 가지는 _id로 검색    
    - result로 담아서 출력하면 { acknowledged: true, deletedCount: 1 } 이렇게 뜸    
3. 검색 노출이 중요할 경우 글 제목같은 데이터는 부모 컴포넌트에서 props로 받아오기    
    - useEffect를 써서 렌더링과 동시에 DB에서 데이터를 조회할 경우, 검색엔진이 웹페이지를 방문하면 내용이 없는 html문서를 조회함    
4. 이모지 입력    
    - vscode 익스텐션 :emojisense: 설치함    
    - extension setting에서 edit in settings.json 눌러서 열고 "javascript": true 추가    