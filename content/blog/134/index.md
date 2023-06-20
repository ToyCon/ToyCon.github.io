---
title: 최빈값 구하기
date: "2023-03-25T21:21:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120812"
---
### 최빈값 구하기   
https://school.programmers.co.kr/learn/courses/30/lessons/120812    
    
#### 변수    
정수 배열 array    
    
#### 제한사항    
0 < array의 길이 < 100    
0 ≤ array의 원소 < 1000    
    
#### 풀이    
원소의 범위가 0에서 999사이의 정수이므로 큰 계산을 요구하지 않는다. 길이 1000의 별도의 배열을 선언하고 매개변수로 넘겨받은 array에 해당하는 배열[e]의 값을 1 더하는 과정을 통해 최대로 등장한 원소의 길이를 반환하는 방식으로 풀었다.    
1. 상수 count 선언하고 Array 생성자로 길이 1000의 배열 생성, 모두 0으로 할당    
2. 변수 maxNum 선언하고 0 할당    
3. array 모든 원소에 대해서 콜백 함수로 e => count[e]++ 실행    
4. maxNum에 array에서 가장 큰 값을 구조분해 할당으로 찾아서 할당    
5. count.indexOf(maxNum) === count.lastIndexOf(maxNum) 여부를 확인, 맞으면 count.indexOf(maxNum) 반환, 틀리면 -1 반환    

#### 코드    
처음에 객체로 풀면 좋겠다는 생각을 했었는데, 아무리 생각해도 지나치게 많은 과정을 거치는 것 같아 시간을 두고 고민을 해서 풀이 과정을 줄일 수 있었다. 다른 사람들의 풀이를 보니 굉장히 다양한 방법으로 문제를 풀었다. 직관적으로 이해가 쉽지 않은 풀이도 많았는데 이해할 수 있도록 꼼꼼히 살펴봐야겠다.    
```JavaScript
function solution(array) {
    const count = new Array(1000).fill(0);
    let maxNum = 0;
    array.forEach(e => count[e]++);
    maxNum = Math.max(...count);
    return count.indexOf(maxNum) === count.lastIndexOf(maxNum) ? count.indexOf(maxNum) : -1;
}
```