---
title: TIL24
date: "2023-07-06T19:45:00.000Z"
description: "7월 6일 학습일지"
---
백엔드는 직접 만들어봤기에 오늘은 시간이 조금 걸려도 어려움없이 기능을 구현할 수 있었다. 코드가 지저분하지만 기능 구현에 집중했다.    
1. bcrypt    
   - 비밀번호를 암호화하는 라이브러리    
   - hash(암호화할 변수, 암호화 횟수)    
   - round는 [공식문서](https://www.npmjs.com/package/bcrypt)에 설명, 2GHz CPu 기준으로 최대 10회(~10 hashes/sec)    
2. ID + 비밀번호 회원 기능    
   - mongodb에 별도 폴더 만들어서 저장 가능    
   - CredentialsProvider 함수  가져와서 [...nextauth].js에 적용    
   - 권한 구현, admin은 모든 게시물에 접근하고 삭제할수 있음    
   - 로그인 했을 때 게시물 보여주기 기능    
3. .env    
   - nextjs는 환경변수 사용하는 모듈 내장(react는 dotenv 가져다 썼음)    