---
title: 문자열 뒤집기
date: "2023-04-05T21:50:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120822"
---
### 문자열 뒤집기    
https://school.programmers.co.kr/learn/courses/30/lessons/120822    
    
#### 변수    
문자열 my_string    
    
#### 제한사항    
1 ≤ my_string의 길이 ≤ 1,000    
    
#### 풀이    
바로 전 문제에서 배열을 뒤집는 방식을 사용했다. 배열로 분해한 다음 뒤집어서 합치는 방식으로 풀었다.    
1. my_string.split('') 실행    
2. reverse 메서드로 반전    
3. join('') 메서드 실행    
4. my_string 반환    
    
#### 코드    
다른 사람들의 풀이 중에 Array 생성자를 써서 split 메서드를 대신 사용하는 풀이가 있었다. 앞으로 문자열을 분해할 때는 Array 생성자를 써야겠다.    
```JavaScript
function solution(my_string) {
    return my_string.split('').reverse().join('');
}
```