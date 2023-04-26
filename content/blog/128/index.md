---
title: 점의 위치 구하기
date: "2023-03-29T13:20:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120841"
---
### 점의 위치 구하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120841    
    
#### 변수    
정수 배열 dot    
    
#### 제한사항    
dot의 길이 = 2    
dot[0] x좌표, dot[1] y좌표    
-500 ≤ dot의 원소 ≤ 500    
dot의 원소는 0이 오지 않음    
    
#### 풀이    
Y축을 기준으로 dot[0]이 양수인지 음수인지 확인하여 1, 2 사분면을 정한다. 만약 dot[1]이 음수라면 사분면의 값에서 5를 빼고 절대값을 취하면 원하는 사분면을 얻을 수 있기 때문에, 이 과정을 그대로 코드로 옮겼다.    
1. 변수 res 선언하고 dot[0]이 0보다 큰지 확인하여 1 또는 2 할당    
2. dot[1]이 0보다 작은 수인지 확인, 작으면 res에서 5를 빼고 절대값    
3. res를 반환    
    
#### 코드    
변수를 선언하지 않고 조건문을 연달아서 사용하는 방식의 풀이들이 많았다. 알아보기 어려운 코드라고 생각하지만, 사용할 수 있는 방법이기 때문에 직접 작성해봐야겠다.    
```JavaScript
function solution(dot) {
    let res = dot[0] > 0 ? 1 : 2;
    return dot[1] < 0 ? Math.abs(res - 5) : res;
}
```