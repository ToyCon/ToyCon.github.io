---
title: 모음 제거
date: "2023-04-28T21:16:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120849"
---
### 모음 제거    
https://school.programmers.co.kr/learn/courses/30/lessons/120849    
    
#### 변수    
문자열 my_string    
    
#### 제한사항    
my_string은 소문자와 공백으로 이루어져 있음    
1 ≤ my_string의 길이 ≤ 1,000    
    
#### 풀이    
1. my_string.replaceAll(/a|e|i|o|u/g,'') 실행 후 반환    
    
#### 코드    
| 연산자 대신 []로 묶는 정규식이 더 깔끔했다. 정규식에 더 익숙해져야겠다.    
```JavaScript
function solution(my_string) {
    return my_string.replaceAll(/a|e|i|o|u/g,'');
}
```