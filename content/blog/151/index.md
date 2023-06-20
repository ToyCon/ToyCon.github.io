---
title: 양꼬치
date: "2023-04-06T01:31:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120830"
---
### 양꼬치    
https://school.programmers.co.kr/learn/courses/30/lessons/120830    
    
#### 변수    
정수 n, k    
    
#### 제한사항    
0 < n < 1,000    
n / 10 ≤ k < 1,000    
서비스로 받은 음료수는 모두 마심    
    
#### 풀이    
양꼬치의 주문 수가 n이므로 n을 10으로 나눈 몫 만큼 음료수 주문 숫자 k를 차감하면 된다. 별도의 변수 선언 없이 바로 값을 반환했다.    
1. 12000 * n + 2000 * (k - Math.trunc(n / 10))를 반환    
    
#### 코드    
```JavaScript
function solution(n, k) {
    return 12000 * n + 2000 * (k - Math.trunc(n / 10));
}
```