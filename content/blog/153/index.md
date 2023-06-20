---
title: 숨어있는 숫자의 덧셈 (2)
date: "2023-04-08T23:52:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120864"
---
### 숨어있는 숫자의 덧셈 (2)    
https://school.programmers.co.kr/learn/courses/30/lessons/120864    
    
#### 변수    
문자열 my_string    
    
#### 제한사항    
1 ≤ my_string의 길이 ≤ 1,000    
1 ≤ my_string 안의 자연수 ≤ 1000    
연속된 수는 하나의 숫자로 간주    
0이 선행하는 경우 없음    
문자열에 자연수가 없는 경우 0을 return    
    
#### 풀이    
split 메서드로 나눠서 숫자 여부를 확인할 수 있다. 빈 문자열로 나누는 대신 정규표현식을 써서 알파벳에 해당하면 모두 빈 문자열로 치환하고, 숫자만 남은 배열을 하나의 값으로 합쳐서 바로 반환했다.    
1. my_string.split(/\D/) 실행    
2. filter 메서드로 원소의 길이가 0보다 큰 원소만 남김    
3. reduce 메서드로 초기값 0, 나머지 원소의 Number tpye을 모두 합쳐서 반환    
    
#### 코드    
다른 풀이를 보니 나와 비슷하게 접근했는데 정규식의 뒤에 +를 붙이고 filter를 생략한 풀이가 있었다. 저런 활용법은 생각하지 못했다. 정규표현식 응용 방법을 많이 검색해봐야겠다.    
```JavaScript
function solution(my_string) {
    return my_string.split(/\D/).filter(e => e.length > 0).reduce((acc, cur) => Number(acc) + Number(cur), 0);
}
```