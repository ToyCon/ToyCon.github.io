---
title: 배열 회전시키기
date: "2023-04-24T21:57:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120844"
---
### 배열 회전시키기    
https://school.programmers.co.kr/learn/courses/30/lessons/120844    
    
#### 변수    
정수가 담긴 배열 numbers    
문자열 direction    
    
#### 제한사항    
3 ≤ numbers의 길이 ≤ 20    
direction은 "left" 와 "right" 둘 중 하나    
    
#### 풀이    
변수를 최대한 줄여서 간략하게 문제를 풀어보려고 했으나 코드를 간결하게 만들기 어려웠다. 변수를 선언하고 direction에 맞춰서 배열을 조합해서 반환하는 방식으로 풀었다.    
1. 변수 left 선언하고 numbers.shift() 할당    
2. 변수 right 선언하고 numbers.pop() 할당    
3. 삼항연산자 조건으로 direction === 'left' 확인    
4. 만족하면 numbers.concat([right, left])    
5. 아니면 [right, left].concat(numbers)    
6. 5를 반환    
    
#### 코드    
unshift(numbers.pop()), push(numbers.shift())로 바로 집어넣는 방식을 전혀 떠올리지 못했다. 다른 풀이를 보니 대부분 이런 식으로 풀었다. 복잡하지 않은 문제에 시간을 많이 쓴 것 같다. 메소드를 응용하는 방법을 계속 고민해봐야겠다.    
```JavaScript
function solution(numbers, direction) {
    let left = numbers.shift();
    let right = numbers.pop();
    return direction === 'left' ? numbers.concat([right, left]) : [right, left].concat(numbers);    
}
```