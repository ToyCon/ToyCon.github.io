---
title: 배열 뒤집기
date: "2023-04-05T21:41:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120821"
---
### 배열 뒤집기    
https://school.programmers.co.kr/learn/courses/30/lessons/120821    
    
#### 변수    
정수 배열 num_list    
    
#### 제한사항    
1 ≤ num_list의 길이 ≤ 1,000    
0 ≤ num_list의 원소 ≤ 1,000    
    
#### 풀이    
반복문을 통해 배열을 역으로 순환하는 방식으로 풀었다.    
1. 상수 res 선언하고 빈 배열 할당    
2. for(i = num_list.length - 1; i >= 0; i--) 반복문 실행    
3. res.push(num_list[i]) 실행    
4. res 반환    
    
#### 코드    
배열을 뒤집는 메서드가 없다고 생각했는데, reverse라는 메서드가 있었다. 앞으로는 특별한 경우가 아니면 reverse 메서드를 써야겠다.    
```JavaScript
function solution(num_list) {
    const res = [];
    for(i = num_list.length - 1; i >= 0; i--) res.push(num_list[i]);
    return res;
}
```