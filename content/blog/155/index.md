---
title: 배열 자르기
date: "2023-04-17T10:40:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120833"
---
### 배열 자르기    
https://school.programmers.co.kr/learn/courses/30/lessons/120833    
    
#### 변수    
정수 배열 numbers    
정수 num1, num2    
    
#### 제한사항    
2 ≤ numbers의 길이 ≤ 30    
0 ≤ numbers의 원소 ≤ 1,000    
0 ≤num1 < num2 < numbers의 길이    
    
#### 풀이    
메서드를 사용해서 바로 배열을 반환했다.    
1. numbers.slice(num1, num2 + 1) 반환    
    
#### 코드    
```JavaScript
function solution(numbers, num1, num2) {
    return numbers.slice(num1, num2 + 1);
}
```