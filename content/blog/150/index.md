---
title: 특정 문자 제거하기
date: "2023-04-05T23:06:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120826"
---
### 특정 문자 제거하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120826    
    
#### 변수    
문자열 my_string    
문자 letter    
    
#### 제한사항    
1 ≤ my_string의 길이 ≤ 100    
letter은 길이 1인 영문자    
my_string과 letter은 알파벳 대소문자 구성    
대문자와 소문자를 구분    
    
#### 풀이    
replaceAll 메서드로 letter에 해당하는 모든 문자를 모두 바로 변환했다.    
1. my_string.replaceAll(letter, '')를 반환    
    
#### 코드    
```JavaScript
function solution(my_string, letter) {
    return my_string.replaceAll(letter, '');
}
```