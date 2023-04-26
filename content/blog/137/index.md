---
title: 나이 출력
date: "2023-04-05T20:23:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120820"
---
### 나이 출력    
https://school.programmers.co.kr/learn/courses/30/lessons/120820    
    
#### 변수    
나이 age    
    
#### 제한사항    
0 < age ≤ 120    
나이는 태어난 연도에 1살이며 1년마다 1씩 증가    
    
#### 풀이    
간단한 사칙연산이라 바로 답을 반환했다.    
1. 2022 - age + 1 반환    
    
#### 코드    
```JavaScript
function solution(age) {
    return 2022 - age + 1;
}
```