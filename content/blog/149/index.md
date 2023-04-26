---
title: 가위 바위 보
date: "2023-04-20T20:18:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120839"
---
### 가위 바위 보    
https://school.programmers.co.kr/learn/courses/30/lessons/120839    
    
#### 변수    
문자열 rsp    
    
#### 제한사항    
가위는 2 바위는 0 보는 5로 표현    
0 < rsp의 길이 ≤ 100    
rsp와 길이가 같은 문자열을 return    
rsp는 숫자 0, 2, 5로 이루어져 있음    
    
#### 풀이    
replaceAll 메서드를 생각했는데 바꾼 답이 바꾸지 않은 답과 중복될 경우 그 다음번 변환에서 반드시 바뀌어서 쓸 수 없었다. 배열로 받아서 모두 바꾸는 방식으로 풀었다.    
1. 구조분해 할당으로 rsp 분해    
2. map 메서드 적용, 콜백 함수로 삼항연산자 ? 사용해서 "2", 아닐 경우 "0" 여부를 확인    
3. 가위 바위 보에 이기는 답을 반환    
4. join('') 메서드 실행한 3을 반환    
    
#### 코드    
문자열을 분해해서 변환하는 접근 방식은 대부분 동일했다. 더 좋은 방식이 있는지 찾아봐야겠다.    
```JavaScript
function solution(rsp) {
    return [...rsp].map(e => e === '2' ? '0' : e === '0' ? '5' : '2').join('');
}
```