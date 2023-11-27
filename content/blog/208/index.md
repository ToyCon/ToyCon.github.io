---
title: 윈도우 환경에서 vscode 셋팅(작성중)
date: "2023-11-24T23:33:00.000Z"
description: vscode 환경설정
---
프론트 코스를 하나 새로 신청해서 수강하면서 윈도우 환경에서 개발 환경을 처음부터 새로 설정했다. vscode도 강의에 맞춰 한글 언어팩을 설치하고 기존에 건드리지 않았던 셋팅을 건드려서 정리해둔다.    
1. extension : korean Language pack 설치 / Microsoft 제작    
2. 기본으로 불러오는 양식을 수정하기    
    - ctrl+shift+p(모든 명령 표시) → User setting 검색(한국어 사용자 설정 열기) → setting.json → "emmet.variables": { "lang": "ko" } 추가    
3. 들여쓰기 정렬    
    - 정리할 구간 선택하고 우클릭 '선택 영역 서식' or ctrl+KF    
    - 2칸 기준으로 정렬하기: setting.json → "editor.tabSize": 2 추가    
4. 태그 한번에 수정하기    
    - extension Auto Rename Tag 설치    
5. html 문서를 웹으로 바로 열기    
    - extension Live Server 설치(와이파이 마크)    
    - 닫고 싶으면 문서에서 우클릭 → Stop Live Server 또는 하단 상태표시줄에서 Stop 누르기