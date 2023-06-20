---
title: 팩토리얼
date: "2023-04-27T20:25:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120848"
---
### 팩토리얼    
https://school.programmers.co.kr/learn/courses/30/lessons/120848    
    
#### 변수    
정수 n    
    
#### 제한사항    
i! ≤ n    
0 < n ≤ 3,628,800    
    
#### 풀이    
1. 변수 res, fac 선언하고 1 할당    
2. while(fac <= n) 반복문 진입    
3. fac *= res; res++ 실행    
4. res - 2 반환    
    
#### 코드    
res가 계속 크게 나와서 2를 뺀 값을 return했더니 모든 테스트를 통과해서 당황했다. 내 풀이처럼 두 변수를 놓고 계산 결과를 반영하면서 반복문으로 해결한 다른 풀이를 보니 마찬가지로 -1을 한 풀이가 있었는데 접근 자체는 옳은 방향이었던것 같다. 이해를 위해 검색을 해봐야겠다.    
```JavaScript
function solution(n) {
    let res = 1;
    let fac = 1;
    while (fac <= n) {
        fac *= res;
        res++;     
    }
    return res - 2;
}
```