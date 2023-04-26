---
title: 개미 군단
date: "2023-04-01T21:40:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120837"
---
### 개미 군단    
https://school.programmers.co.kr/learn/courses/30/lessons/120837    
    
#### 변수    
사냥감의 체력 hp    
    
#### 제한사항    
hp는 자연수    
0 ≤ hp ≤ 1000    
    
#### 풀이    
복잡한 계산이 필요하지 않아서 답을 담을 변수를 선언하고 사칙 연산으로 풀었다.    
1. 변수 res 선언하고 Math.trunc(hp / 5) 할당    
2. hp = hp % 5 할당    
3. res = res + hp Math.trunc(hp / 3) 할당    
4. hp = hp % 3 할당    
5. res + hp를 반환    
    
#### 코드    
```JavaScript
function solution(hp) {
    let res = Math.trunc(hp / 5);
    hp %= 5;
    res += Math.trunc(hp / 3);
    hp %= 3;
    return res + hp;
}
```