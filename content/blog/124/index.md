---
title: 중앙값 구하기
date: "2023-03-24T10:23:00.000Z"
cdescription: "https://school.programmers.co.kr/learn/courses/30/lessons/120853"
---
### 중앙값 구하기   
https://school.programmers.co.kr/learn/courses/30/lessons/120853    
    
#### 변수    
정수 배열 array    
    
#### 제한사항    
array의 길이는 홀수    
0 < array의 길이 < 100    
-1,000 < array의 원소 < 1,000    
    
#### 풀이    
배열을 정렬해서 가운데 원소를 바로 반환하는 방식으로 풀었다.        
1. array.sort() 실행    
2. array[Math.trunc(array.length / 2)] 반환    
    
#### 코드    
sort 메서드가 오름차순 정렬을 기본으로 하기에 콜백을 따로 주지 않았는데 테스트케이스를 통과하지 못했다. 어떻게 정렬되는지 다시 확인을 해봐야겠다.    
```JavaScript
function solution(array) {
    array = array.sort((a, b) => a - b);
    return array[Math.trunc(array.length / 2)];
}
```