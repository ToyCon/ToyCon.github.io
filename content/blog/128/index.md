---
title: 두 수의 나눗셈
date: 2023-03-22 22:33:00 +0900
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120806"
---
### 두 수의 나눗셈    
https://school.programmers.co.kr/learn/courses/30/lessons/120806    
    
#### 변수    
정수 num1, num2     
    
#### 제한사항    
0 < num1 ≤ 100    
0 < num2 ≤ 100    
    
#### 순서    
반올림을 하기 전에 먼저 1000을 곱해야 한다. 순서를 고려해서 작성했다.    
1. Math.floor(num1 * 1000 / num2) 반환    
    
#### 코드    
floor 대신 trunc 메서드를 다른 사람 풀이를 보면서 알게 됐다. 소수점을 제거하는 기능으로 사용하는 메서드인 만큼, 앞으로는 floor보다는 trunc 메서드를 사용해야겠다.    
```JavaScript
function solution(num1, num2) {
    return Math.floor(num1 * 1000 / num2);
}
```
