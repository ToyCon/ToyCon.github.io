---
title: 아이스 아메리카노
date: "2023-03-31T16:40:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120819"
---
### 아이스 아메리카노    
https://school.programmers.co.kr/learn/courses/30/lessons/120819    
    
#### 변수    
돈 money    
    
#### 제한사항    
0 < money ≤ 1,000,000    
    
#### 풀이    
배열 내부에서 필요한 값을 계산해서 바로 반환했다.    
1. money를 5500으로 나눈 값의 소수점을 버린 값을 배열에 추가    
2. money를 5500으로 나눈 값의 나머지를 배열에 추가    
3. 배열을 반환    
    
#### 코드    
```JavaScript
function solution(money) {
    return [Math.trunc(money / 5500), money % 5500];
}
```