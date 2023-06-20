---
title: 소인수분해
date: "2023-05-01T17:25:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120852"
---
### 소인수분해    
https://school.programmers.co.kr/learn/courses/30/lessons/120852    
    
#### 변수    
자연수 n    
    
#### 제한    
2 ≤ n ≤ 10,000    
    
#### 풀이    
짝수 여부를 확인한 뒤, 2로 나눈 수를 홀수로 나눠서 검사하는 방식으로 풀었다.    
1. 상수 res 선언하고 빈 배열 할당    
2. n % 2 === 0 이면 res에 2 추가    
3. 위의 if문 내부에서 while (n % 2 === 0) n /= 2 실행    
4. for(i = 3; i * i <= n; i+=2) 반복문 진입    
5. n % i === 0 이면 res에 i 추가    
6. 5번 if문 내부에서 while(n % i === 0) n /= i 실행    
7. n > 2일 경우 res에 추가    
8. res.length가 0보다 큰지 확인, 크면 res, 그렇지 않으면 [n]을 반환    
    
#### 코드    
문제 풀이에 오늘 하루를 거의 다 보냈다. 소수를 구하는 공식에서 에러가 나서 시간을 많이 잡아먹었고, 에러를 해결했는데도 테스트케이스를 통과하지 못해서 또 많이 고민해야했다. 공부해야할 다른 내용들이 많지만 굉장히 기본적인 것을 놓친 기분이 들어서 이 문제를 풀면서 생긴 의문들을 해소할때까지 다른 내용을 미뤄두고 우선 공부해볼 생각이다.    
```JavaScript
function solution(n) {
    let res = [];
    if(n % 2 === 0) {
        res.push(2);
        while(n % 2 === 0) n/=2;
    }
    for(i = 3; i * i <= n; i += 2) {
        if(n % i === 0){
            res.push(i);
            while(n % i === 0) n/=i;
        } 
    }
    if(n > 2) res.push(n);
    return res.length > 0 ? res : [n];
}
```