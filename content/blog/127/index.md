---
title: 직사각형 넓이 구하기
date: "2023-03-28T16:13:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120860"
---
### 직사각형 넓이 구하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120860    
    
#### 변수    
배열 dots    
    
#### 제한사항    
dots의 길이 = 4    
dots의 원소의 길이 = 2    
-256 < dots[i]의 원소 < 256    
잘못된 입력 없음    
    
#### 풀이    
문제에서 변이 축과 평행한 직사각형이라고 조건을 줘서 계산이 쉬웠다. 예시 2에서 각 꼭짓점이 순서대로 주어지지 않았기 때문에 dots를 정렬하는 방식을 고민했다.    
1. 변수 x, y를 선언하고 0 할당    
2. dots에 sort((a, b) => a[0] === b[0] || a - b) 실행    
3. x에 dots[0][0] - dots[2][0]의 절대값 할당    
4. y에 dots[0][1] - dots[1][1]의 절대값 할당    
5. x * y 반환    
    
#### 코드    
다른 사람들의 풀이가 매우 다채로웠다. 대체로 변의 길이를 구해서 푸는 방식은 비슷했는데 그 과정을 알아보기 힘든 몇개의 풀이가 있었다. 이 답변들을 살펴봐야겠다.    
```JavaScript
function solution(dots) {
    let x, y = 0;
    dots.sort((a, b) => a[0] === b[0] || a - b);
    x = Math.abs(dots[0][0] - dots[2][0]);
    y = Math.abs(dots[0][1] - dots[1][1]);
    return x * y;
}
```