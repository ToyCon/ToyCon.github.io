---
title: 짝수의 합
date: "2023-04-12T09:35:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120831"
---
### 짝수의 합    
https://school.programmers.co.kr/learn/courses/30/lessons/120831    
    
#### 변수    
정수 n    
    
#### 제한사항    
0 < n ≤ 1000    
    
#### 풀이    
조건을 만족하는 수의 합은 보통 공식이 있어서 이 문제도 공식이 있지 않을까 했는데, 혼자서 찾는 것은 쉽지 않았다. 공식은 나중에 찾아보기로 하고 반복문으로 합을 구했다.    
1. 변수 res 선언하고 0 할당    
2. for(i = 2; i <= n; i += 2) 반복문 진입    
3. res += i 실행    
4. res 반환    
    
#### 코드    
다른 사람들의 풀이를 보니 역시 공식이 있었다. 원리를 찾아봐야겠다.    
```JavaScript
function solution(n) {
    let res = 0;
    for(i = 2; i <= n; i += 2) res += i;
    return res;
}
```