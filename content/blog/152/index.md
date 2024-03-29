---
title: 순서쌍의 개수
date: "2023-04-07T16:12:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120836"
---
### 순서쌍의 개수    
https://school.programmers.co.kr/learn/courses/30/lessons/120836    
    
#### 변수    
자연수 n    
    
#### 제한사항    
1 ≤ n ≤ 1,000,000    
    
#### 풀이    
순서쌍의 갯수를 물어보는 문제이므로 반복문을 통해 순서쌍이 성립되는 경우만 별도의 변수에 합산했다.    
1. 변수 res 선언하고 0 할당    
2. for(i = 1; i <= n / 2; i++) 반복문 진입    
3. n % i === 0 확인, 맞으면 res++    
4. res + 1을 반환    
    
#### 코드    
제곱근을 이용한 방식이 아직도 헷갈린다. 제곱근 방식을 사용한 다른 사람들의 풀이를 연구해봐야겠다.    
```JavaScript
function solution(n) {
    let res = 0;    
    for(i = 1; i <= n / 2; i++) if(n % i === 0) res++;
    return res + 1;
}
```