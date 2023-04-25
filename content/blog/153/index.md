---
title: 주사위의 개수
date: "2023-04-25T09:55:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120845"
---
### 주사위의 개수    
https://school.programmers.co.kr/learn/courses/30/lessons/120845    
    
#### 변수    
배열 box    
주사위 모서리의 길이 정수 n    
    
#### 제한사항    
box의 길이는 3
box[0] = 상자의 가로 길이    
box[1] = 상자의 세로 길이    
box[2] = 상자의 높이 길이    
1 ≤ box의 원소 ≤ 100    
1 ≤ n ≤ 50    
n ≤ box의 원소    
주사위는 상자와 평행하게 넣음    
    
#### 풀이    
1. box[i]/n 의 정수 부분을 곱한 값을 반환    
    
#### 코드    
box에 reduce 메서드를 적용한 풀이들이 있었다. 배열이 나오면 항상 배열에 적용하는 메서드 적용이 가능한지 생각해봐야겠다.    
```JavaScript
function solution(box, n) {
    return Math.trunc(box[0]/n) * Math.trunc(box[1]/n) * Math.trunc(box[2]/n);
}
```