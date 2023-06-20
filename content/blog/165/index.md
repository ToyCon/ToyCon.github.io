---
title: 최댓값 만들기 (1)
date: "2023-04-26T16:06:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120847"
---
### 최댓값 만들기 (1)    
https://school.programmers.co.kr/learn/courses/30/lessons/120847    
    
#### 변수    
정수 배열 numbers    
    
#### 제한사항    
0 ≤ numbers의 원소 ≤ 10,000    
2 ≤ numbers의 길이 ≤ 100    
    
#### 풀이    
numbers를 정렬한 다음 가장 큰 두개의 값만 남겨서 곱을 바로 반환했다.    
1. numbers 내림차순 정렬    
2. numbers의 원소를 앞의 두 개만 남기고 모두 삭제    
3. 두 원소의 곱을 반환    
    
#### 코드    
reduce 메서드를 이용해 slice 과정을 생략한 풀이가 있었다. reduce에 전달되는 인자로 인덱스가 존재한다는 사실을 자꾸 까먹는것 같다. 답안을 잘 기억해두고 MDN 문서도 다시 봐야겠다.    
```JavaScript
function solution(numbers) {
    return numbers.sort((a, b) => b - a).slice(0, 2).reduce((acc, cur) => acc * cur, 1);
}
```