---
title: 분수의 덧셈
date: 2023-03-22 22:56:00 +0900
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120808"
---
### 분수의 덧셈    
https://school.programmers.co.kr/learn/courses/30/lessons/120808    
    
#### 변수    
첫 번째 분수의 분자와 분모를 뜻하는 numer1, denom1    
두 번째 분수의 분자와 분모를 뜻하는 numer2, denom2    
    
#### 제한사항    
0 <numer1, denom1, numer2, denom2 < 1,000    
    
#### 순서    
수의 범위가 크지 않으므로 따로 분모를 일치시키는 과정을 거치지 않고 바로 첫 번째 분수에 denom2를 곱하고, 마찬가지로 두 번째 분수에도 denom1을 곱하는 방식으로 풀었다.    
1. getGCD = (a, b) => (b > 0 ? getGCD(b, a % b) : a); 함수 선언    
2. 변수 numer3 선언하고 numer1 * denom2 + numer2 * denom1 할당    
3. denom3 선언하고 denom1 * denom2 할당    
4. 변수 GCD 선언하고 getGCD(numer3, denom3) 할당    
5. [numer3 / GCD, denom3/GCD] 반환    
    
#### 코드    
```JavaScript
function solution(numer1, denom1, numer2, denom2) {
    const getGCD = (a, b) => (b > 0 ? getGCD(b, a % b) : a);
    let numer3 = numer1 * denom2 + numer2 * denom1;
    let denom3 = denom1 * denom2;
    let GCD = getGCD(numer3, denom3);
    return [numer3 / GCD, denom3/GCD];
}
```
