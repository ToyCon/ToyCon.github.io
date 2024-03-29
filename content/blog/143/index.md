---
title: 배열의 평균값
date: "2023-04-01T22:03:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120817"
---
### 배열의 평균값    
https://school.programmers.co.kr/learn/courses/30/lessons/120817    
    
#### 변수    
정수 배열 numbers    
    
#### 제한사항    
0 ≤ numbers의 원소 ≤ 1,000    
1 ≤ numbers의 길이 ≤ 100    
정답의 소수 부분이 .0 또는 .5인 경우만 주어짐    
    
#### 풀이    
reduce 메서드로 바로 답을 반환했다.    
1. numbers.reduce() 실행    
2. 콜백 함수로 (acc, cur, idx, { length }) => idx === length - 1 ? (acc + cur) / length : acc + cur 실행    
3. 최초값으로 0 할당    
4. 1을 반환    
    
#### 코드    
```JavaScript
function solution(numbers) {
    return numbers.reduce((acc, cur, idx, { length }) => idx === length - 1 ? (acc + cur) / length : acc + cur, 0);
}
```