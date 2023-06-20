---
title: 숫자 비교하기
date: 2023-03-22 22:37:00 +0900
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120807"
---
### 숫자 비교하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120807    
    
#### 변수    
정수 num1, num2     
    
#### 제한사항    
0 ≤ num1 ≤ 10,000    
0 ≤ num2 ≤ 10,000    
    
#### 순서    
1. num1, num2가 같은 값인지 확인, 맞으면 1 반환    
2. 1을 만족하지 않으면 -1 반환    
    
#### 코드    
```JavaScript
function solution(num1, num2) {
    return num1 === num2 ? 1 : -1;
}
```
