---
title: 짝수 홀수 개수
date: "2023-04-04T17:15:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120824"
---
### 짝수 홀수 개수    
https://school.programmers.co.kr/learn/courses/30/lessons/120824    
    
#### 변수    
정수 배열 num_list    
    
#### 제한사항    
1 ≤ num_list의 길이 ≤ 100    
0 ≤ num_list의 원소 ≤ 1,000    
    
#### 풀이    
다른 문제의 풀이를 보면서 reduce 메서드를 통해 하나의 배열로 묶어서 반환하는 방식을 봤는데 직접 시도해보니 잘 되지 않았다. 별도의 배열을 선언해서 풀었다.    
1. 상수 res 선언하고 [0, 0] 할당    
2. num_list에 forEach 적용, 콜백 함수로 각 원소에 대해서 짝수, 홀수 여부를 확인    
3. 짝수면 res[0] + 1, 홀수면 res[1] + 1    
4. res 반환    
    
#### 코드    
접근방법이 굉장히 다양했다. 짝수 홀수 검사를 하지 않고 2로 나눈 나머지를 바로 반환할 배열의 순서로 활용한 답이 많은 추천을 받았는데 나중에 사용할 수 있는 방법인 것 같다. 기억해야겠다.    
```JavaScript
function solution(num_list) {
    let res = [0, 0];
    num_list.forEach(e => e % 2 === 0 ? res[0] += 1 : res[1] += 1);
    return res;
}
```