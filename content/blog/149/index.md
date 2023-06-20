---
title: 문자 반복 출력하기
date: "2023-04-05T22:56:00.000Z"
description: "https://school.programmers.co.kr/learn/courses/30/lessons/120825"
---
### 문자 반복 출력하기    
https://school.programmers.co.kr/learn/courses/30/lessons/120825    
    
#### 변수    
문자열 my_string    
정수 n    
    
#### 제한사항    
2 ≤ my_string 길이 ≤ 5    
2 ≤ n ≤ 10    
"my_string"은 영어 대소문자    
    
#### 풀이    
문자열을 그대로 반복하는게 아니라 글자별로 반복하는 구조다. 배열로 분해한 다음 각 원소를 n번씩 반복해서 합치는 방식으로 풀었다.    
1. my_string을 배열로 변환    
2. map 메서드 실행, 콜백 함수로 e => e = e.repeat(n) 실행    
3. join('') 메서드 실행    
4. my_string 반환    
    
#### 코드    
```JavaScript
function solution(my_string, n) {
    return new Array(...my_string).map(e => e = e.repeat(n)).join('');
}
```