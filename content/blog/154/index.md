---
title: 합성수 찾기
date: "2023-04-25T10:15:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120846"
---
### 합성수 찾기    
https://school.programmers.co.kr/learn/courses/30/lessons/120846    
    
#### 변수    
자연수 n    
    
#### 제한사항    
1 ≤ n ≤ 100    
    
#### 풀이    
약수의 갯수를 구하는 방법을 어떻게 할지에 시간을 정말 많이 썼다. 4 이상의 짝수는 무조건 합성수다. 홀수의 경우가 문제인데, 홀수 x 홀수가 나오는 경우가 생각보다 많지 않았다(결국 검색을 해서 소수를 제외하면 9 이상의 홀수도 모두 합성수라는 사실을 알았다). 조금 무식한 방법이지만 n의 범위가 1에서 100 사이로 넓지 않기 때문에, n의 범위 안에 있는 소수를 검색해서 소수의 갯수를 제외한 n의 값을 반환하는 방식으로 풀었다.    
1. 변수 res 선언하고 n 할당    
2. 상수 primeNumber 선언하고 1에서 97까지 소수를 담은 배열 할당    
3. for (i = 1; i <= n; i++) 반복문 진입    
4. primeNumber.includes(i) 확인, 맞으면 res--    
5. res 반환    
    
#### 코드    
문제의 조건에 맞춰서 풀긴 했지만 만족하기 어려운 풀이였다. 더 넓은 범위에도 적용할 수 있는 방식을 다른 사람들 풀이를 보면서 연구해봐야겠다.    
```JavaScript
function solution(n) {
    let res = n;
    const primeNumber = [1, 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97];
    for(i = 1; i <= n; i++) if(primeNumber.includes(i)) res--;
    return res;
}
```