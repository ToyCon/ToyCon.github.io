---
title: 배열 원소의 길이
date: "2023-03-30T14:15:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120854"
---
### 배열 원소의 길이    
https://school.programmers.co.kr/learn/courses/30/lessons/120854    
    
#### 변수    
문자열 배열 strlist    
    
#### 제한사항    
1 ≤ strlist 원소의 길이 ≤ 100    
strlist는 알파벳 소문자, 대문자, 특수문자로 구성    
    
#### 풀이    
길이는 메서드를 통해 바로 받을 수 있기 때문에, 별도의 변수 없이 바로 변환해서 반환했다.    
1. strlist에 map 메서드 적용, e => e = e.length 콜백함수 실행 후 반환    
    
#### 코드    
```JavaScript
function solution(strlist) {
    return strlist.map(e => e = e.length);
}
```